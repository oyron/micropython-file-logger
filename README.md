# Simple file logger for Micropython

Simple file logger for Micropython.
The logger reads the timestamp from the real time clock and appends a log line to the log file.
Please note that the logger does not contain logic for managing the log file (like rolling, deleting old files, etc).


## Example usage:

```python
from file_logger import Logger

logger = Logger("debug", "logfile.log")
logger.info("ESP started and connected to WiFi")

```

This will produce the following output in `logfile.log`:

```
2019-08-14 10:20:31.911 INFO: ESP8266 started and connected to WiFi
```

## Setting the real time clock
If the realtime clock is not set, the timestamps will start at 2000-01-01.
The real time clock can be set like this:
```python
    import machine

    rtc = machine.RTC()
    rtc.datetime(...) #array on the format (year, month, day, weekday, hours, minutes, seconds, subseconds)
```
For more info see http://docs.micropython.org/en/v1.9.3/pyboard/library/pyb.RTC.html
