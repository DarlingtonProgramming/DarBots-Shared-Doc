# 1.0 Log File Standardization

## 1.1 Log Level Standardization
Different Log Entries are divided into different levels. Here is a list of them.

|logLevel|Integer Value|Description|
|--------|-------------|-----------|
|FATAL|5|Very severe error events that might cause the application to terminate.|
|ERROR|4|Error events of considerable importance that will prevent normal program execution, but might still allow the application to continue running.|
|WARNING|3|Potentially harmful situations of interest to end users or system managers that indicate potential problems.|
|INFO|2|Informational messages that might make sense to end users and system administrators, and highlight the progress of the application.|
|DEBUG|1|Relatively detailed tracing used by application developers.|

## 1.2 File Storage
Darbots FTC Lib Logger Files are stored in the /FIRST/Logs/ directory of the phone's local storage space.   

## 1.3 Log File Structure
The Log File is a plain TXT file encoded in ASCII with the JSON scheme. The main structure of the file follows the following pattern:

```json
[
    {
        "initTime": 0, //type: long, represents how many milliseconds passed since EPOCH until OpMode Initialization, time zone = UTC.
        "startTime": 0, //type: long, how many milliseconds have passed since initialization until OpMode start, -1 = not started,
        "endTime": 0, //type: long, how many milliseconds have passed since initialization until OpMode stop
        "runningOpMode": "Robot4100Gen1Auto-BlueScanDouble", //Class Name of the Running OpMode
        "priority": 0, //Integer of Thread Priority, from 1 to 10, 1 = lowest, 10 = highest priority
        "logs":[
            {
                "module": "ServoUsingMotor", //Which Module is reporting this log?
                "caption": "SystemStatus", //What is the title of the log?
                "timeStamp": 0, //type: long, how many milliseconds have passed since initialization until this log entry is recorded
                "content": {
                    "type": "xxx", //log type, described in string
                    "value": {} //type: object
                }, //type: object, the content of the log entry
                "level": 1 //type: integer, integer value given by logLevel specified above.
            }
        ]
    },
    {
        "startTime": "Integer of how many seconds have passed since epoch",
        "runningOpMode": "Class Name of the Running OpMode",
        "priority": "Integer of Thread Priority, from 1 to 10",
        "logs":[

        ]
    }
]
```