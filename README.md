In this project, we have designed and implemented the following instrumentation features into Chromium Browser in Linux and Android platforms. 

	-Raw data: HTML (per page/frame), cookies (per domain), scripts (per source) 
	
	-DOM events: common W3C events and touch events[1]. Basic attributes explored: timestamp, frame URL, element node, triggered handlers, error messages ,etc. 
	
	-Web navigation events: URL_loads (before), redirection, failures, file download, etc.


Logging the different Events
-----------------------------

SQLite3 instrumentation :
	In this approach, we tried to instrument the logger feature by using the SQLite library in android. The idea was to push the log events as database entries within tables for the respective event type. We were successful in implementing the sqlite functionalities in the C++ files to instrument logging features for various events. 

	The library for SQLite3 is already included in the chromium browser source code at “chromium/src/ third_party/sqlite/*” 

	The only difference in instrumentation in Android and Linux is the location of the path where the sqlite.db files are being stored. 
	 	LINUX: /home/usr/chrome_log.sqlite 
	 	Android: /mnt/sdcard/chrome_log.sqlite


TEAM : Subhasis Das and Rishi Josan
