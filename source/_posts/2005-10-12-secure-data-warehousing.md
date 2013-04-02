---
title: Secure Data Warehousing
author: jeff
layout: post
permalink: /2005/10/12/secure-data-warehousing/
categories:
  - Development
  - FreeMED
---
# 

My newest project with [FreeMED][1] has been to implement a way to securely warehouse medical data offsite. This relates to [Dr Gnu’s article][2] about disaster recovery. I have been using SSL [WebDAV][3] with a slim C client built on [neon][4] to push [gnupg][5]-encrypted SQL dumps (both incremental and full) to the archive server, which is perhaps temporarily residing at [https://archive.freemedsoftare.net/][6]. In this way, whoever is hosting the archive cannot read the medical data without the gnupg keys held only by the provider who “owns” the medical records. [HIPAA compliance][7], here we are …

 [1]: http://freemedsoftware.org/
 [2]: http://drgnu.blogspot.com/2005/10/disaster-planning.html
 [3]: http://www.webdav.org/
 [4]: http://www.webdav.org/neon/
 [5]: http://www.gnupg.org/
 [6]: https://archive.freemedsoftware.net/
 [7]: http://www.aapsonline.org/confiden/survcomm.htm