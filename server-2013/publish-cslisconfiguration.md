﻿---
title: Publish-CsLisConfiguration
TOCTitle: Publish-CsLisConfiguration
ms:assetid: 54f9d653-075d-4533-b508-231f53b54db4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398364(v=OCS.15)
ms:contentKeyID: 49309792
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publish-CsLisConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Publishes the Location Information Server (LIS) configuration to the управления. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Publish-CsLisConfiguration [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command commits the LIS configuration to the управления.

    Publish-CsLisConfiguration

## Detailed Description

In order to implement Enhanced 9-1-1 (E9-1-1) in Lync Server, you must create a location mapping (called a wiremap). This mapping includes matching physical addresses to ports, subnets, switches, and wireless access points so any calls made over an Enterprise Voice connection will reach the nearest emergency operator and provide that operator with the correct location of the caller. This mapping configuration, created by calling cmdlets such as the **Set-CsLisPort** cmdlet and the **Set-CsLisSubnet** cmdlet, is stored in a central location database. This cmdlet commits any changes in the central location database to the управления, allowing the information to be replicated to the Location Information servers so that the locations can be rendered to clients. The configuration can be removed from the управления by calling the **Unpublish-CsLisConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Publish-CsLisConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Publish-CsLisConfiguration"}

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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

None.

## Return Types

This cmdlet does not return a value.

## См. также

#### Другие ресурсы

[Debug-CsLisConfiguration](debug-cslisconfiguration.md)  
[Unpublish-CsLisConfiguration](unpublish-cslisconfiguration.md)  
[Import-CsLisConfiguration](import-cslisconfiguration.md)  
[Export-CsLisConfiguration](export-cslisconfiguration.md)  
[Test-CsLisConfiguration](test-cslisconfiguration.md)

