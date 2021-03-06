### com.esri.rttest.mon.TimescaleSqlMon

- Monitors a HyperTable count and measures and reports rate of change in count.  
- When the tool starts it gets the current count and starts sampling count every sampleRateSec seconds (defaults to 5 seconds).
- When count changes the tool starts collecting sample points. 
- After collecting three points the output will use linear regression to estimate the rate of change.
- After count stops changing the final line will give the count received and the best fit linear approximation of the rate.  The last sample is excluded from the final rate calculation.
- After reporting the final count and rate the tool will continue monitoring for count changes.  Use **Ctrl-C** to stop.

<pre>
java -cp target/rttest.jar com.esri.rttest.mon.TimescaleSqlMon
Usage: TimescaleSqlMon [connectionUrl] [schema] [tableName] [sampleRateSec=5] [username] [password]
</pre>

Example:

<pre>
java -cp target/rttest.jar com.esri.rttest.mon.TimescaleSqlMon jdbc:postgresql://HostName:5432/dbName realtime safegraph 20 user pass
</pre>

