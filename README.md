<a name="Title">
# vLI-Veeam-CP

vRealize Log Insight Content Pack for Veeam

|Navigation|
|-----------------|
|[About](#About)|
|[Features](#Features)|
|[Setup](#Setup)|


<a name="About">
# About
[*Back to top*](#Title)

Project Owner: Markus Kraus

Project WebSite: http://mycloudrevolution.com/projekte/vrealize-log-insight-veeam-content-pack/

Project Details: Veeam Backup & Replication Content Pack for VMware vRealize Log Insight

<a name="Features">
# Features
[*Back to top*](#Title)

## Dashboards
### Veeam - General
![alt text](/Media/Veeam - General.png "Veeam - General")

### Veeam - StoreOnce
![alt text](/Media/Veeam - StoreOnce.png "Veeam - StoreOnce")

### Veeam - Jobs
![alt text](/Media/Veeam - Jobs.png "Veeam - Jobs")

### Veeam - CloudConnect
![alt text](/Media/Veeam - CloudConnect.png "Veeam - CloudConnect")

<a name="Setup">
# Setup
[*Back to top*](#Setup)

1. Download /ContentPack/Veeam.vlcp
2. Import Content Pack
3. Configure Agent Group "Veeam" for all your Veeam Severs
4. If you need to monitor Explicit Jobs in addition. Add another Agent Group for teh Veeam Main Server "Veeam - Jobs":

```javascript
[filelog|VEEAM-JOB-Backup_1]
directory=C:\ProgramData\Veeam\Backup\Backup_1
include=*.log
event_marker=(\[)\d{2}(\.|-)\d{2}(\.|-)\d{4}\s\d{2}(\:|-)\d{2}(\:|-)\d{2}(\])
tags={"Appname" : "Veeam", "Veeam_JobLog" : "Backup_1"}

[filelog|VEEAM-JOB-BackupCopy_1]
directory=C:\ProgramData\Veeam\Backup\BackupCopy_1
include=*.log
event_marker=(\[)\d{2}(\.|-)\d{2}(\.|-)\d{4}\s\d{2}(\:|-)\d{2}(\:|-)\d{2}(\])
tags={"Appname" : "Veeam", "Veeam_JobLog" : "BackupCopy_1"}
```
