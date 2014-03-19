---
title: A few observations about Android
author: jeff
layout: post
permalink: /2009/09/29/a-few-observations-about-android/
categories:
  - Android Development
---

I’ve been in the process of teaching myself the Google Android platform over the last few weeks, as my work has had a contest devoted to creating a mobile phone app, with a prize attached. I’m the only entrant who doesn’t work in the Engineering department, so this is a bit of a professional stretch for me as far as my job is concerned.

I have found quite a few caveats in the development process which are worth noting, as I have spent a fair amount of time researching them to figure them out. (I should also note at this point that this is in no way downplaying the important role Android plays in the future of mobile phone platforms, and is definitely \*not\* advocating either WinMo, which is a horrible abortion of a platform, or iPhone, which is not only locked to a single vendor, but \*requires\* purchasing a Crapitosh for development as well as a minimum 99$ development license to get going …)

1) **Camera Access** – It took some digging to find that you have to allow permission android.permission.CAMERA, or else it’ll throw out of memory errors and crash the app. I think it’s a running bug that in Android 1.6 it isn’t throwing a proper “PermissionDeniedException” or whatever else they feel like calling it. Otherwise the Camera API is pretty powerful.

2) **Getting your own phone number** – This is very interesting, as Android just moved to using something called “TelephonyManager” to deal with all of this. Unfortunately documentation hasn’t quite caught up to it. An example:

    TelephonyManager mTelephonyMgr = (TelephonyManager)context.getSystemService(Context.TELEPHONY_SERVICE); 
    String imei = mTelephonyMgr.getDeviceId(); 
    String phoneNumber=mTelephonyMgr.getLine1Number(); 
    String country = mTelephonyMgr.getNetworkCountryISO(); 

3) **Saving state** – If you want to save state for your app, it makes no sense to go any further than SharedPreferences. It keeps you from having to create a content provider to deal with keeping that information stored somewhere else …

4) **AppWidgets are awesome** — The idea of a “home screen” applet is really easy to implement simply by extending AppWidgetProvider and add a  XML element to the AndroidManifest.xml file corresponding with the class.

5) **Opening an intent from a menu item** – The documentation says to use \*a\* Context, but doesn’t mention that you should be passing the Activity subclass that you’re coding to use as the Context.
