﻿---
title: Set-CsTestDevice
TOCTitle: Set-CsTestDevice
ms:assetid: 0a9fabfc-b0d3-4c94-ae04-0a87f0886db8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398156(v=OCS.15)
ms:contentKeyID: 49308892
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTestDevice

 

_**Дата изменения раздела:** 2015-03-09_

Modifies one or more of the device update management test devices that have been configured for use in your organization. Test devices provide a way for administrators to test firmware updates before those updates are distributed to all the devices in an organization. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsTestDevice [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsTestDevice [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Identifier <String>] [-IdentifierType <MACAddress | SerialNumber>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 modifies the Identifier property for the test device named UCPhone assigned to the Redmond site.

    Set-CsTestDevice -Identity site:Redmond/UCPhone -Identifier "09768-ABDR-83295"

## EXAMPLE 2

The command shown in Example 2 also modifies the test device named UCPhone assigned to the Redmond site. In this case, however, the command not only specifies a new Identifier but also assigns a new IdentifierType: SerialNumber.

    Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"

## Detailed Description

By identifying specific phones running Lync Phone Edition or other devices as test devices, administrators can verify and approve firmware updates before those updates are rolled out to all the relevant devices in the organization. When device update rules are imported to Lync Server, they are marked as "pending," which means that the updates corresponding to these rules will not automatically be downloaded and installed by the affected devices.

Instead, these pending rules will be downloaded and installed by any relevant test devices. That’s the idea behind test devices: new device update rules are automatically applied to test devices, giving administrators the opportunity to verify that the firmware updates work as expected. If they do, those administrators can then mark the rules as approved; approved rules are then downloaded and installed by all the relevant devices in the organization.

Test devices are created by using the **New-CsTestDevice** cmdlet. After a test device has been created, you can then use the **Set-CsTestDevice** cmdlet to change the Identifier and the IdentifierType of that device, or any other test device.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsTestDevice** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsTestDevice"}

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identifier</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Based on the IdentifierType, indicates the Media Access Control (MAC) address or serial number of the new test device. Serial numbers can be specified using numbers, letters, hyphens and underscores; for example:</p>
<p>-Identifier &quot;AB37_679e&quot;</p>
<p>MAC addresses must be specified as six or more two-character pairs; depending on the MAC address, these pairs can be a single string value or they can be separated using hyphens or colons. (Note that MAC addresses can include both letters and/or numbers.) Each of the following are valid MAC addresses:</p>
<p>010203040506</p>
<p>01-02-03-04-05-06</p>
<p>01:02:03:04:05:06</p>
<p>A MAC address such as 01-02-03-04-05 will not be accepted because it does not have at least six two-character pairs.</p></td>
</tr>
<tr class="even">
<td><p><em>IdentifierType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.IdentifierType</p></td>
<td><p>Indicates whether the test device will be uniquely identified by its MAC address or by its serial number. To identify a device by its MAC address, set the IdentifierType to MACAddress. To identify a device by its serial number, set the IdentifierType to SerialNumber. MACAddress and SerialNumber are the only allowed values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the test device to be modified. For example: -Identity site:Redmond/UCPhoneTestDevice. Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Test device object</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.TestDevice object. The **Set-CsTestDevice** cmdlet accepts pipelined input of the test device object.

## Return Types

The **Set-CsTestDevice** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.TestDevice object.

## См. также

#### Другие ресурсы

[Get-CsTestDevice](get-cstestdevice.md)  
[New-CsTestDevice](new-cstestdevice.md)  
[Remove-CsTestDevice](remove-cstestdevice.md)

