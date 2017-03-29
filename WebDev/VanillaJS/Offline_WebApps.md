## The need

* We need to be considering offline approach for the following reasons:
  * to be able to use apps even with flaky connection (cell network in a train)
  * to be able to work without network connection (on an airplane)
  * to boost the performance
  
## Standards?

* Google is defining concept called [Progressive Web Apps](https://developers.google.com/web/progressive-web-apps)
* They have come up with a simple checklist which is exhaustive. [Link](https://developers.google.com/web/progressive-web-apps/checklist)
* Tool to test your app for performance. [LightHouse](https://developers.google.com/web/tools/lighthouse/)

> Lighthouse is an open-source, automated tool for improving the quality of web pages. You can run it against any page on the web. It has audits for performance, accessibility, progressive web apps, and more.

## Getting it work

> Offline assets - html, css, js

* [Service Workers](https://www.w3.org/TR/service-workers/) is a script that gets executed before every outgoing requests, here we can pull the files from the local storage instead of continuiung with the request

> Offline data storage

There are several options introduced by HTML5:

* WebStorage – key-value storage

> WebStorage is a key-value storage. This is the simplest cross-browser storage, but there are several pitfalls to be aware of. You have to take care of serialization and deserialization of data that you put inside because the values must be plain strings. You may run up against size limits with larger data sets. Also, it’s possible to get into a race condition, meaning if you have two tabs opened at the same time in the browser you could end up with unexpected behavior.


* IndexedDB – NoSQL database

> IndexedDB is much more powerful and seems to be the best way to go with offline storage. It has plenty of space available. It supports transactions and can be safely used in several browser tabs at the same time. It’s also supported by all modern browsers.


* WebSQL – built-in SQLite database

> WebSQL is literally SQLite in the browser. Full-featured relational DB with ACID on the client. Unfortunately, WebSQL has been deprecated by the standards committee and was never supported in non-Blink/Webkit browsers.
