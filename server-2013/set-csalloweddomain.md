﻿---
title: Set-CsAllowedDomain
TOCTitle: Set-CsAllowedDomain
ms:assetid: d5b25b66-2b11-40ef-9ea4-efcae0b610e6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398931(v=OCS.15)
ms:contentKeyID: 49311293
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAllowedDomain

 

_**Дата изменения раздела:** 2015-03-09_

Modifies property values for a domain (or domains) included on the list of domains approved for federation. After a domain has been approved for federation (by being added to the allowed list), your users can exchange instant messages and presence information with people who have accounts in the federated domain. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsAllowedDomain [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsAllowedDomain [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Comment <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MarkForMonitoring <$true | $false>] [-ProxyFqdn <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the Comment property for the allowed domain with the Identity "fabrikam.com". This is done by including the Comment parameter and the appropriate parameter value: "Contact: Ken Myer (kenmyer@fabrikam.com)".

    Set-CsAllowedDomain -Identity fabrikam.com -Comment "Contact: Ken Myer (kenmyer@fabrikam.com)"

## EXAMPLE 2

Example 2 modifies the Comment and MarkForMonitoring properties for all of the allowed domains that have the string value "fabrikam" somewhere in their Identity. To carry out this task, the command first calls the **Get-CsAllowedDomain** cmdlet and the Filter parameter. The filter value "\*fabrikam\*" instructs the **Get-CsAllowedDomain** cmdlet to return any domain where the Identity includes the string value "fabrikam". (For example, this command returns domains such as fabrikam.com, us.fabrikam.net, and fabrikam-users.org). The filtered collection is then piped to the **Set-CsAllowedDomain** cmdlet, which modifies for Comment property and sets the MarkForMonitoring property to True ($True) for each item in the collection.

    Get-CsAllowedDomain -Filter *fabrikam* | Set-CsAllowedDomain -Comment "Contact: Ken Myer (kenmyer@fabrikam.com)" -MarkForMonitoring $True

## EXAMPLE 3

The command shown in Example 3 modifies all of the domains on the allowed list that are not currently monitored by мониторинга. (That is, all of the domains where the MarkForMonitoring property is set to False.) To do this, the **Get-CsAllowedDomain** cmdlet is called without any additional parameters in order to retrieve a collection of all the domains on the allowed list. That collection is piped to the **Where-Object** cmdlet, which selects only those domains where MarkForMonitoring is equal to False. The filtered collection is then piped to the **Set-CsAllowedDomain** cmdlet, which sets the MarkForMonitoring property for each domain in the collection to True.

    Get-CsAllowedDomain | Where-Object {$_.MarkForMonitoring -eq $False} | Set-CsAllowedDomain -MarkForMonitoring $True

## EXAMPLE 4

Example 4 adds a generic comment ("Need contact information.") to each domain on the allowed list where the Comment property currently has no value. To carry out this task, the command first calls the **Get-CsAllowedDomain** cmdlet to retrieve a collection of all the domains on the allowed list. This collection is then piped to the **Where-Object** cmdlet, which picks out those domains where the Comment property is equal to a null value. That filtered collection is then piped to the **Set-CsAllowedDomain** cmdlet, which modifies the Comment property for each item in the collection.

    Get-CsAllowedDomain | Where-Object {$_.Comment -eq $Null} | Set-CsAllowedDomain -Comment "Need contact information."

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must enable your servers running the Lync Server Access Edge service to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To set up a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list represents the organizations you have chosen to federate with. If a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

The **Set-CsAllowedDomain** cmdlet provides a way for you to modify property values for any domain on the list of allowed domains.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAllowedDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAllowedDomain"}

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
<td><p><em>Comment</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Optional string value that provides additional information about the domain being modified. For example, you might add a Comment that provides contact information for the federated domain.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the allowed domain for which the property values are being modified. For example:</p>
<p>-Identity fabrikam.com</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Blocked Domain object</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p></td>
</tr>
<tr class="even">
<td><p><em>MarkForMonitoring</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the federation connection between your domain and the remote domain will be monitored by мониторинга. By default, MarkForMonitoring is set to False, meaning that the connection will not be monitored.</p>
<p>This property will be ignored if you have not deployed мониторинга.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (for example, proxy-server.fabrikam.com) of the SIP proxy server deployed in the domain being added to the allowed list. This property is optional: if it is not specified then DNS SRV discovery procedures will be used to determine the location of the SIP proxy server.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowedDomain object. The **Set-CsAllowedDomain** cmdlet accepts pipelined instances of the allowed domain object.

## Return Types

The **Set-CsAllowedDomain** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowedDomain object.

## См. также

#### Другие ресурсы

[Get-CsAllowedDomain](get-csalloweddomain.md)  
[New-CsAllowedDomain](new-csalloweddomain.md)  
[Remove-CsAllowedDomain](remove-csalloweddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)

