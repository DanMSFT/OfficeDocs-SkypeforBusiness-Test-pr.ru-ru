﻿---
title: Remove-CsManagementConnection
TOCTitle: Remove-CsManagementConnection
ms:assetid: 2fe69a3d-0154-418f-b6ee-99a88e5a9c7d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425803(v=OCS.15)
ms:contentKeyID: 49309337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsManagementConnection

 

_**Дата изменения раздела:** 2015-03-09_

Resets the management connection to the Active Directory service control point for the управления. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsManagementConnection [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 removes the existing management connection information and replaces it with the default connection information stored in Active Directory.

    Remove-CsManagementConnection

## Detailed Description

Configuration data for Lync Server is stored in the управления; it is crucial that both Windows PowerShell and the management replication services be able to locate this database. When you install Lync Server, a service control point is created in Доменные службы Active Directory that provides location information for this database. Typically, computers rely on this service control point in order to connect to the управления. To see the details behind this connection (that is, if you want to know which computer the управления is running on, as well information about the SQL Server connection to that управления), you can run the **Get-CsManagementConnection** cmdlet.

As a general rule, you will not need to change your management connection. However, it is possible that you might need to temporarily use a new management connection. When you are ready to switch back to the default connection all you need to do is run the **Remove-CsManagementConnection** cmdlet; this cmdlet erases the current connection information and replaces it with the connection information stored in the Active Directory service control point. This means you do not have to recreate the original connection information; the **Remove-CsManagementConnection** cmdlet will do that for you.

Note that no problems will occur if you call this cmdlet while using the default connection. If you do so, you will simply continue to use the default connection information stored in Active Directory. Note, too that this cmdlet only affects the management connection information for your current Windows PowerShell session: any changes to the management connection are limited to your local computer and local instance of Windows PowerShell.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsManagementConnection** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsManagementConnection"}

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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Remove-CsManagementConnection** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Remove-CsManagementConnection** cmdlet deletes instances of the Microsoft.Rtc.Management.Xds.ManagementConnection object.

## См. также

#### Другие ресурсы

[Get-CsManagementConnection](get-csmanagementconnection.md)  
[Remove-CsConfigurationStoreLocation](remove-csconfigurationstorelocation.md)  
[Set-CsManagementConnection](set-csmanagementconnection.md)

