﻿---
title: Get-CsWatcherNodeConfiguration
TOCTitle: Get-CsWatcherNodeConfiguration
ms:assetid: 20dae017-375c-4361-8d65-b56f4c09b375
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204739(v=OCS.15)
ms:contentKeyID: 49309162
ms.date: 04/05/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsWatcherNodeConfiguration

 

_**Дата изменения раздела:** 2017-04-05_

Returns information about the watcher node configuration settings in use in your organization. Watcher nodes are computers that periodically use Microsoft System Center Operations Manager and Lync Server 2013 synthetic transactions to verify that Lync Server components are working as expected. The watcher node configuration settings let you know which pools have been associated with a watcher node. Данный командлет впервые появился в Lync Server 2013.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>This command must be run on the dedicated Trusted Application Server previously configured as a watcher node using the <strong>New-CsWatcherNodeConfiguration</strong> command otherwise the output will display a null result.</td>
</tr>
</tbody>
</table>


## Синтаксис

    Get-CsWatcherNodeConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsWatcherNodeConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the watcher nodes currently configured for use in the organization.

    Get-CsWatcherNodeConfiguration

## Example 2

In Example 2, information is returned for the watcher node associated with the pool.

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com"

## Example 3

The command shown in Example 3 returns information about all the watcher nodes where the test users include the user with the SIP address sip:kenmyer@litwareinc.com. To do this, the command first uses the **Get-CsWatcherNodeConfiguration** cmdlet to return a collection of all the watcher nodes in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those nodes where the TestUsers property contains the SIP address sip:kenmyer@litwareinc.com.

    Get-CsWatcherNodeConfiguration | Where-Object {$_.TestUsers -contains "sip:kenmyer@litwareinc.com"}

## Example 4

In Example 4, information is returned for all the watcher nodes that include the PSTN test type. To carry out this task, the command first calls the **Get-CsWatcherNodeConfiguration** cmdlet in order to return a collection of all the watcher nodes in the organization. That collection is then piped to the **Where-Object** cmdlet, which selects only those watcher nodes where the ExtendedTests property includes (-matches) the string value "TestType=PSTN".

    Get-CsWatcherNodeConfiguration | Where-Object {$_.ExtendedTests -match "TestType=PSTN"}

## Detailed Description

If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions in order to verify that Lync Server is working as expected. Watcher nodes are assigned to pools, and are managed using the **CsWatcherNodeConfiguration** cmdlets. Note that you do not need to install watcher nodes if you are using System Center Operations Manager. You can still monitor your system without using watcher nodes; the only difference is that any synthetic transactions you want to run will need to be invoked manually rather than automatically invoked by Operations Manager.

The **Get-CsWatcherNodeConfiguration** cmdlet returns information about all the watcher nodes that have been configured for use in your organization.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the командной строки Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsWatcherNodeConfiguration"}

**управления Lync Server:** The functions carried out by the **Get-CsWatcherNodeConfiguration** cmdlet are not available in the управления Lync Server.

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters in order to return one or more watcher nodes. For example, to return all of the watcher nodes for the domain litwareinc.com use this syntax:</p>
<p>-Filter &quot;*.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name of the pool that the watcher node has been assigned to. For example:</p>
<p>-Identity &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>If this parameter is not specified then the <strong>Get-CsWatcherNodeConfiguration</strong> cmdlet will return information about all the watcher nodes configured for use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the watcher node configuration data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsWatcherNodeConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsWatcherNodeConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

## См. также

#### Другие ресурсы

[New-CsWatcherNodeConfiguration](new-cswatchernodeconfiguration.md)  
[Remove-CsWatcherNodeConfiguration](remove-cswatchernodeconfiguration.md)  
[Set-CsWatcherNodeConfiguration](set-cswatchernodeconfiguration.md)  
[Test-CsWatcherNodeConfiguration](test-cswatchernodeconfiguration.md)

