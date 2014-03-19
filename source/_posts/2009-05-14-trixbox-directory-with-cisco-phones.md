---
title: Trixbox directory with Cisco Phones
author: jeff
layout: post
permalink: /2009/05/14/trixbox-directory-with-cisco-phones/
categories:
  - Hacks
---

In case anyone may want to use Trixbox with Cisco 79xx phones and wants to use a directory with it, I have put together a hack to deal with the directory services, which nominally require SugarCRM, so that they report simple extensions back in the appropriate format.

1) In the Endpoint manager, make sure that the services URL and directory URL are in the default configuration for Cisco phones, and restart any phones which are running to activate the configuration.

2) In `/var/www/html/cisco/services`, make sure that index_cisco.php is symlinked to index.php

3) In `/var/www/html/cisco/services/DBConnect.inc`, change the default username and password to something with access to the asterisk database, and change the database name to `asterisk`.

4) Make `PhoneDirectory.php` in that directory contain:

    < ?php
    
    ##########################################
    # Config section
    
    $Server = "http://$SERVER_ADDR/cisco/services";   # don't add a trailing slash!
    $LongDistanceExtension = ""; # change this to match your config
    
    ##########################################
    #
    # Set content type
    header("Content-Type: text/xml");
    
    # This is the include file that establishes the connection to the MySQL database
    require ("DBConnect.inc"); 
    
    # This sets the offset for the LIMIT portion of the query
    $NextStartingRow = $NextSet*30;
    
    # Connect to the database
    $ConnectionSuccess = db_connect();
    if (!$ConnectionSuccess) exit;
    
    # If the variable "ID" is passed in through the GET string, then display 
    # extension, phone number and cell phone number for that record with the dial
    # key functionality
    if ($ID) {
            $PersonDirectoryListing = "n";
    
            //$Query  = "SELECT id, first_name, last_name, phone_home, phone_work, phone_mobile, phone_other ";
            //$Query .= "FROM contacts WHERE id = '$ID' ";
            //$Query .= "ORDER BY last_name "; 
            $Query  = "SELECT id,description FROM devices WHERE ( tech = 'sip' OR tech = 'iax' ) AND id = '".addslashes($ID)."' ";
    
            $SelectPersonInfo = mysql_query($Query,$ConnectionSuccess);
    
            while ($row = mysql_fetch_array($SelectPersonInfo)) {
                    $WorkPhone = ereg_replace("[ ()-] ", "", $row['id']);
    
                    $PersonDirectoryListing .= "n";
                    $PersonDirectoryListing .= "Extension:n";
                    //$PersonDirectoryListing .= "$LongDistanceExtension$WorkPhonen";
                    $PersonDirectoryListing .= "$WorkPhonen";
                    $PersonDirectoryListing .= "n";
            }
    
            $PersonDirectoryListing .= "n";
    
            echo "$PersonDirectoryListing";
    
    # If the variable ID is not passed in on the GET string, then do the 
    # entire company directory, unless last is passed in. If so then we
    # will be using a LIKE filter in our SQL query
    } else {
            $PersonNameList = "n";
            $PersonNameList .= "n";
            $PersonNameList .= "Please select onen";
    
            $Query  = "SELECT id,description FROM devices WHERE ( tech = 'sip' OR tech = 'iax' ) ";
            //$Query  = "SELECT id, first_name, last_name, phone_home, phone_work, phone_mobile, phone_other ";
            //$Query .= "FROM contacts WHERE deleted = 0 ";
    
            # If we are searching by last name the add this filter to the query
            if ($LastName) { $Query .= "and description like '%$LastName%' ";  }
            $Query .= "ORDER BY id ASC";
    
            # If this is the first page of the company directory then we will display the first 30
            if (!$NextSet) {
                    $Query .= " Limit 0,30";
            # Now for each subsiquent call we get the next 30 records.
            } else {
                    $Query .= " Limit $NextStartingRow,30";
            }
    
            # Execute the query
            //echo $Query;
            $SelectNameList = mysql_query($Query,$ConnectionSuccess);
    
            # Count the number of rows returned. This is important because if a full 30 are returned
            # we will display a more option
    
            $NumberOfRows = mysql_num_rows($SelectNameList);
    
            if ($NumberOfRows >= 30) {
                    $NextSetValue = $NextSet 1;
            }
    
            # Parse through the query and set up the menu items.
            while ($row = mysql_fetch_array($SelectNameList)) {
                    $PersonNameList .= "n";
                            $PersonNameList .= "";
                                    $PersonNameList .= $row["description"];
                                    if ($row["first_name"]) $PersonNameList .= ", " . $row["first_name"];
                            $PersonNameList .= "n";
                            $PersonNameList .= "";
                                    $PersonNameList .= "$Server/PhoneDirectory.php?";
                                    $PersonNameList .= "ID=";
                                    $PersonNameList .= $row["id"];
                                    $PersonNameList .= "n";
                    $PersonNameList .= "n";
            }
    
            # If we set NextSetValue above then we will display the more option. Which sets NextSet
            if ($NextSetValue) {
                    $PersonNameList .= "n";
                            $PersonNameList .= "MOREn";
                            $PersonNameList .= "$Server/PhoneDirectory.php?NextSet=$NextSetValuen";
                    $PersonNameList .= "n";
            }
            $PersonNameList .= "";
            echo "$PersonNameList";
    }
    ?>
