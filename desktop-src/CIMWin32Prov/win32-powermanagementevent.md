---
Description: The Win32\_PowerManagementEvent &\#32; WMI class represents power management events resulting from power state changes.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: b5781805-87c7-4eaf-afbb-a1770fcff41c
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: Win32\_PowerManagementEvent class
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Win32\_PowerManagementEvent class

The **Win32\_PowerManagementEvent** [WMI class](https://msdn.microsoft.com/cfe4bcca-692e-45cd-a840-93ebfe4ae267) represents power management events resulting from power state changes. These state changes are associated with either the Advanced Power Management (APM) or the Advanced Configuration and Power Interface (ACPI) system management protocols.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[UUID("{86460B6B-E709-11d2-B139-00105A1F77A1}"), AMENDMENT]
class Win32_PowerManagementEvent : __ExtrinsicEvent
{
  uint8  SECURITY_DESCRIPTOR[];
  uint64 TIME_CREATED;
  uint16 EventType;
  uint16 OEMEventCode;
};
```

## Members

The **Win32\_PowerManagementEvent** class has these types of members:

-   [Properties](#properties)

### Properties

The **Win32\_PowerManagementEvent** class has these properties.

<dl> <dt>

**EventType**
</dt> <dd> <dl> <dt>

Data type: **uint16**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**MappingStrings**](https://msdn.microsoft.com/671ea769-f68d-4788-96f5-c4f86ab3b00e) ("Win32API\|Power Management Events")
</dt> </dl>

Type of change in the system power state.

<dt>

<span id="Entering_Suspend"></span><span id="entering_suspend"></span><span id="ENTERING_SUSPEND"></span>

<span id="Entering_Suspend"></span><span id="entering_suspend"></span><span id="ENTERING_SUSPEND"></span>**Entering Suspend** (4)


</dt> <dd>

While suspended, the computer appears to be off; however, it can be "awakened" in response to various events, including user input (such as moving the mouse or pressing a key on the keyboard). While the computer is suspended, power consumption is reduced to one of several levels depending on how the system is to be used. The lower the level of power consumption, the more time it takes the system to return to the working state. When the computer enters the suspend state, the desktop is locked, and you must press CTRL+ALT+DELETE and provide a valid user name and password to resume operations

</dd> <dt>

<span id="Resume_from_Suspend"></span><span id="resume_from_suspend"></span><span id="RESUME_FROM_SUSPEND"></span>

<span id="Resume_from_Suspend"></span><span id="resume_from_suspend"></span><span id="RESUME_FROM_SUSPEND"></span>**Resume from Suspend** (7)


</dt> <dd>

Indicates that a Resume from Suspend message has been sent, enabling the computer to return to its regular power state.

</dd> <dt>

<span id="Power_Status_Change"></span><span id="power_status_change"></span><span id="POWER_STATUS_CHANGE"></span>

<span id="Power_Status_Change"></span><span id="power_status_change"></span><span id="POWER_STATUS_CHANGE"></span>**Power Status Change** (10)


</dt> <dd>

Indicates a change in the power status of the computer, such as a switch from battery power to AC, or from AC to an uninterruptible power supply. The system also broadcasts this event when remaining battery power slips below the threshold specified by the user or if the battery power changes by a specified percentage.

</dd> <dt>

<span id="OEM_Event"></span><span id="oem_event"></span><span id="OEM_EVENT"></span>

<span id="OEM_Event"></span><span id="oem_event"></span><span id="OEM_EVENT"></span>**OEM Event** (11)


</dt> <dd>

Indicates that an Advanced Power Management (APM) BIOS has sent an OEM event. The value of the event will be captured in the **OEMEventCode** property. Because some APM BIOS implementations do not provide OEM event notifications, this event might never be broadcast on some computers. APM is a legacy power management scheme. Although still supported, APM has been largely superseded by ACPI (Advanced Configuration and Power Interface).

</dd> <dt>

<span id="Resume_Automatic"></span><span id="resume_automatic"></span><span id="RESUME_AUTOMATIC"></span>

<span id="Resume_Automatic"></span><span id="resume_automatic"></span><span id="RESUME_AUTOMATIC"></span>**Resume Automatic** (18)


</dt> <dd>

Indicates that the computer has awakened in response to an event. If the system detects user activity (such as a mouse click), the ResumeSuspend message will be broadcast, letting applications know that they can resume full interactivity with the user.

</dd> </dl>

</dd> <dt>

**OEMEventCode**
</dt> <dd> <dl> <dt>

Data type: **uint16**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**MappingStrings**](https://msdn.microsoft.com/671ea769-f68d-4788-96f5-c4f86ab3b00e) ("Win32API\|Power Management Events")
</dt> </dl>

System power state defined by the original equipment manufacturer (OEM) when the **EventType** property of this class is set to 11 (OEM Event); otherwise, this property is set to **NULL**. OEM events are generated when an APM BIOS signals an APM OEM event. OEM event codes are in the range 0x0200h - 0x02FFh.

</dd> <dt>

**SECURITY\_DESCRIPTOR**
</dt> <dd> <dl> <dt>

Data type: **uint8** array
</dt> <dt>

Access type: Read-only
</dt> </dl>

Descriptor used by the event provider to determine which users can receive the event. This property is inherited from [**\_\_Event**](https://msdn.microsoft.com/4d2e4715-041c-49e9-b948-a148dfe85483). For more information about constants used to set this security descriptor, see [WMI Security Constants](https://msdn.microsoft.com/f6808f50-a1fd-434f-8a42-efa3afbe7871).

</dd> <dt>

**TIME\_CREATED**
</dt> <dd> <dl> <dt>

Data type: **uint64**
</dt> <dt>

Access type: Read-only
</dt> </dl>

Unique value that indicates the time at which the event was generated. This is a 64-bit value that represents the number of 100-nanosecond intervals after January 1, 1601. The information is in the Coordinated Universal Times (UTC) format.

This property is inherited from [**\_\_Event**](https://msdn.microsoft.com/4d2e4715-041c-49e9-b948-a148dfe85483).

For more information about using **uint64** values in scripts, see [Scripting in WMI](https://www.bing.com/search?q=Scripting+in+WMI).

</dd> </dl>

## Remarks

The **Win32\_PowerManagementEvent** class is derived from [**\_\_ExtrinsicEvent**](https://msdn.microsoft.com/8fddbcd1-7393-4a3b-8a10-a8b620efc19f).

Changes in power status often indicate that a problem has occurred with a computer or with another managed device. If a server suddenly switches from AC power to an uninterruptible power supply, this change can indicate that an electrical problem of some kind has occurred, either with the computer itself or with the electrical system in the room in which the computer is kept.

Administrators need to monitor these changes in power status and be notified of such changes immediately. This enables them to take action before the device loses power entirely. (Uninterruptible power supply systems, for example, might run for only 15 minutes or so before shutting down.)

The **Win32\_PowerManagementEvent** class can be used to monitor changes in power status on a computer. These changes can include a switch from one power source to another as well as a change in computer power state (for example, entering or exiting Suspend mode).

The **Win32\_PowerManagementEvent** class has only two properties: EventType, used to indicate the type of power change event that occurred, and OEMEventType, which is used by some original equipment manufacturers to define additional power change events.

For more information on responding to Windows power events, see the [Monitor and Respond to Windows Power Events with PowerShell](http://blogs.technet.com/b/heyscriptingguy/archive/2011/08/16/monitor-and-respond-to-windows-power-events-with-powershell.aspx) article on the Hey! Scripting Guy! blog.

For more information on charging laptops, see [Hey, Scripting Guy! How Can I Retrieve Information About Laptops Changing from Full Power to Minimal Power Usage?](http://blogs.technet.com/b/heyscriptingguy/archive/2010/04/14/hey-scripting-guy-april-14-2010.aspx)

## Examples

The following VBScript monitors changes in power status on a computer.


```VB
Set colMonitoredEvents = GetObject("winmgmts:")._
 ExecNotificationQuery("SELECT * FROM Win32_PowerManagementEvent")
Do
 Set strLatestEvent = colMonitoredEvents.NextEvent
 Wscript.Echo strLatestEvent.EventType
Loop
```



## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**\_\_ExtrinsicEvent**](https://msdn.microsoft.com/8fddbcd1-7393-4a3b-8a10-a8b620efc19f)
</dt> <dt>

[Computer System Hardware Classes](computer-system-hardware-classes.md)
</dt> <dt>

[Monitoring Changes in Computer Power Status](https://TechNet.Microsoft.Com/en-us/library/ee176537.aspx)
</dt> </dl>

 

 



