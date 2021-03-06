Log4Netly
=========

Simple, asynchronous [Loggly](https://www.loggly.com) log4net appender. Find the NuGet package [here](https://www.nuget.org/packages/Log4Netly).

```json
{
  "level":"ERROR",
  "time":"2014-06-28T00:40:27.7318531-04:00",
  "machine":"MYMACHINE",
  "process":"Log4NetlyTesting.vshost",
  "thread":"10",
  "message":"Now you've done it...",
  "logger":"Log4NetlyTesting.Program",
  "customProperty":"Your very own LoggingEvent property!",
  "exception":{
    "message":"Attempted to divide by zero.",
    "stackTrace":" at Log4NetlyTesting.Program.Main(String[] args) in c:\\SomePath\\Log4Netly\\Log4NetlyTesting\\Program.cs:line 19",
    "type":"DivideByZeroException",
    "innerException": {
      "message":"Inner exception message.",
      "stackTrack":" at Log4NetlyTesting.Program.Main(String[] args) in c:\\SomePath\\Log4Netly\\Log4NetlyTesting\\Program.cs:line 18",
      "type":"Exception"
    }
  }
}
```

```xml
<appender name="LogglyAppender" type="Log4Netly.LogglyAppender, Log4Netly">
  <endpoint value="https://logs-01.loggly.com/" />
  <token value="your-loggly-token" />
  <tags value="tag1,tag2,tag3" /><!-- One or more tags -->
</appender>
```
or
```xml
<appender name="BufferedLogglyAppender" type="Log4Netly.BufferedLogglyAppender, Log4Netly">
  <endpoint value="https://logs-01.loggly.com/"/>
  <token value="your-loggly-token" />
  <tags value="tag1,tag2,tag3" /><!-- One or more tags -->
  <bufferSize value="512" />
  <intervalInMs value="2500" />
</appender>
```