---
title: Create Your AppLocker Planning Document
ms.custom: na
ms.prod: windows-server-2012-r2
ms.reviewer: na
ms.suite: na
ms.technology: 
  - techgroup-security
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1f111979-0457-4639-a63c-bd44bef47903
---
# Create Your AppLocker Planning Document
This planning topic for the IT professional summarizes the information you need to research and include in your AppLocker planning document.

## The AppLocker deployment design
The design process and the planning document help you investigate application usage in your organization and record your findings so you can effectively deploy and maintain application control policies by using AppLocker.

You should have completed these steps in the design and planning process:

1.  [Determine Your Application Control Objectives](Determine-Your-Application-Control-Objectives.md)

2.  [Create List of Applications Deployed to Each Business Group](Create-List-of-Applications-Deployed-to-Each-Business-Group.md)

3.  [Select Types of Rules to Create](Select-Types-of-Rules-to-Create.md)

4.  [Determine Group Policy Structure and Rule Enforcement](Determine-Group-Policy-Structure-and-Rule-Enforcement.md)

5.  [Plan for AppLocker Policy Management](Plan-for-AppLocker-Policy-Management.md)

### AppLocker planning document contents
Your planning document should contain:

-   A list of business groups that will participate in the application control policy project, their requirements, a description of their business processes, and contact information.

-   Application control policy project target dates, both for planning and deployment.

-   A complete list of applications used by each business group \(or organizational unit\), including version information and installation paths.

-   What condition to apply to rules governing each application \(or whether to use the default set provided by AppLocker\).

-   A strategy for using Group Policy to deploy the AppLocker policies.

-   A strategy in processing the application usage events generated by AppLocker.

-   A strategy to maintain and manage AppLocker polices after deployment.

### Sample template for an AppLocker planning document
You can use the following form to construct your own AppLocker planning document.

**Business group**:

**Operating system environment**: \(Windows and non\-Windows\)

||||
|-|-|-|
|**Contacts**|Business contact:|Technical contact:|
|**Other departments**|In this business group:|Affected by this project:|
|**Security policies**|Internal:|Regulatory\/compliance:|
|**Business goals**|Primary:|Secondary:|
|**Project target dates**|Design signoff date:|Policy deployment date:|

**Rules**

|Business group|Organizational unit|Implement AppLocker?|Applications|Installation path|Use default rule or define new rule condition|Allow or deny|GPO name|Support policy|
|------------------|-----------------------|------------------------|----------------|---------------------|-------------------------------------------------|-----------------|------------|------------------|
||||||||||

**Event processing**

|Business group|AppLocker event collection location|Archival policy|Analyzed?|Security policy|
|------------------|---------------------------------------|-------------------|-------------|-------------------|
||||||

**Policy maintenance**

|Business group|Rule update policy|Application decommission policy|Application version policy|Application deployment policy|
|------------------|----------------------|-----------------------------------|------------------------------|---------------------------------|
||Planned:<br /><br />Emergency:||||

### Example of an AppLocker planning document
**Rules**

|Business group|Organizational unit|Implement AppLocker?|Applications|Installation path|Use default rule or define new rule condition|Allow or deny|GPO name|Support policy|
|------------------|-----------------------|------------------------|----------------|---------------------|-------------------------------------------------|-----------------|------------|------------------|
|Bank Tellers|Teller\-East and Teller\-West|Yes|Teller Software|C:\\Program Files\\Woodgrove\\Teller.exe|File is signed; create a publisher condition|Allow|Tellers\-AppLockerTellerRules|Web help|
||||Windows files|C:\\Windows|Create a path exception to the default rule to exclude \\Windows\\Temp|Allow||Help desk|
|Human Resources|HR\-All|Yes|Check Payout|C:\\Program Files\\Woodgrove\\HR\\Checkcut.exe|File is signed; create a publisher condition|Allow|HR\-AppLockerHRRules|Web help|
||||Time Sheet Organizer|C:\\Program Files\\Woodgrove\\HR\\Timesheet.exe|File is not signed; create a file hash condition|Allow||Web help|
||||Internet Explorer 7|C:\\Program Files\\Internet Explorer\\|File is signed; create a publisher condition|Deny||Web help|
||||Windows files|C:\\Windows|Use the default rule for the Windows path|Allow||Help desk|

**Event processing**

|Business group|AppLocker event collection location|Archival policy|Analyzed?|Security policy|
|------------------|---------------------------------------|-------------------|-------------|-------------------|
|Bank Tellers|Forwarded to: AppLocker Event Repository on srvBT093|Standard|None|Standard|
|Human Resources|DO NOT FORWARD. srvHR004|60 months|Yes, summary reports monthly to managers|Standard|

**Policy maintenance**

|Business group|Rule update policy|Application decommission policy|Application version policy|Application deployment policy|
|------------------|----------------------|-----------------------------------|------------------------------|---------------------------------|
|Bank Tellers|Planned: Monthly through business office triage<br /><br />Emergency: Request through help desk|Through business office triage<br /><br />30\-day notice required|General policy: Keep past versions for 12 months<br /><br />List policies for each application|Coordinated through business office<br /><br />30\-day notice required|
|Human Resources|Planned: Monthly through HR triage<br /><br />Emergency: Request through help desk|Through HR triage<br /><br />30\-day notice required|General policy: Keep past versions for 60 months<br /><br />List policies for each application|Coordinated through HR<br /><br />30\-day notice required|

### Additional resources

-   The AppLocker Policies Design Guide is the predecessor to the AppLocker Policies Deployment Guide. When planning is complete, see the [AppLocker Policies Deployment Guide]().

-   For a complete list of AppLocker documentation and other resources, see [AppLocker Overview](assetId:///358610e4-88b2-40d0-b34d-dfd7ddee0ed9) in the Windows Server Technical Library.

