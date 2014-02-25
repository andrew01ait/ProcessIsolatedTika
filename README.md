ProcessIsolatedTika
===================

Project to abstract the use of tika-server in a seperate process/JVM

This project runs a background process/JVM for tika-server to isolate its execution.  Files/InputStreams can be passed to this class for parsing, and they are sent to the tika-server via JAXRS.  The return values are populated in to the Metadata object that is passed to the parse() method, just like a normal call to Tika.

A copy of a tika-server jar will be contained within this jar and is copied to a temporary folder for background execution.

If a call to the tika-server takes longer than 10 seconds (by default) the tika-server is restarted.