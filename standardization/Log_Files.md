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
        "startTime": "Integer of how many seconds have passed since epoch",
        "runningOpMode": "Class Name of the Running OpMode",
        "logs":[
            {
                "module": "ServoUsingMotor",
                "caption": "SystemStatus",
                "timeStamp": "Epoch Time",
                "content": "XXXXX",
                "level": "Integer Value of Log Level"
            }
        ]
    },
    {
        "startTime": "Integer of how many seconds have passed since epoch",
        "runningOpMode": "Class Name of the Running OpMode",
        "logs":[

        ]
    }
]
```