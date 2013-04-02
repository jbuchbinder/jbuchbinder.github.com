---
title: Designing applications for clustering
author: jeff
layout: post
permalink: /2010/05/21/designing-applications-for-clustering/
categories:
  - Development
  - FreeMED
---
# 

I have been recently been trying to redesign [FreeMED][1] (my opensource GPL’d EMR/PM system) in order to work in a “clustered” environment, so that I could support scenarios where multiple application servers were load-balanced to handle larger quantities of traffic. The latest piece of this has been to move filesystem-based storage into the database layer so that I don’t have to mess around with clustered file storage and replication. Some of the highlights of this have been:

 [1]: http://freemedsoftware.org

*   **Database-based session handling** – At least when dealing with stateless applications like FreeMED, session information has a bad habit of being confined to the local filesystem. We ended up using PEAR’s HTTP_Session2 to support database-backed sessions. I can’t help but think this would be so much easier using JAAS … 
*   **API abstraction** – Don’t write this one off too quickly. A good API layer means that whenever you have to make these sweeping changes, you’re only playing with a few files of source code, as opposed to completely rewriting a good chunk of your codebase. Without the few layers of API which I had been using, I would not have been able to implement the database backed information store which I just completed.
*   **Database backed file store** – This was the part I had just finished up. Storing files locally and relying on filesystem-based replication from some of the new clustering filesystems may \*seem\* like a good idea, but it’s not. Database gives you a single authoritative source, and unless we’re looking at multi-gigabyte files, there should not be an appreciable toll. Besides, you indexed your tables properly, right … ?
*   **Design for concurrency** – That record locking may seem like a pain, but two people working on the same object can be catastrophic. Take the time to add a locking field if you have to.
*   **Singletons** – Take “singleton” processes into account, so you’re only running a single iteration of something which can only be run once.

Those are the major bullet points, although I’m sure that upon review of this, I’ll think of some other design paradigms I had to play with to get this to function properly. Off to enjoy the weekend …