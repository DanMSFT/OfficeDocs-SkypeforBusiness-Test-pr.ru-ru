﻿---
title: New-CsSipProxyUseDefault
TOCTitle: New-CsSipProxyUseDefault
ms:assetid: 1e8bedca-8bd5-4559-b530-0f18ae23d6d3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398274(v=OCS.15)
ms:contentKeyID: 49309141
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsSipProxyUseDefault

 

_**Дата изменения раздела:** 2015-03-09_

Used to assign the default realm (SIP Communications Service) to a collection of proxy configuration settings. Realms (also known as protection domains) are used to authenticate user credentials during logon. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsSipProxyUseDefault

## Examples

## EXAMPLE 1

The command shown in Example 1 assigns the default realm (SIP Communications Service) to a variable named $x.

    $x = New-CsSipProxyUseDefault

## Detailed Description

Proxy servers provide a way for users outside your internal network to access resources on your internal network. Each proxy server must be associated with a realm; realms (also known as protection domains) indicate where a user’s logon credentials should be processed. By default, Lync Server uses SIP Communications Service as its default realm; however, it is possible to change the realm employed by a proxy server. If you change the realm and then want to revert back to using the default realm, you can do so by creating a SipProxy.UseDefault object, and then assigning that object to the Realm property of the appropriate proxy server (or servers).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSipProxyUseDefault** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSipProxyUseDefault"}

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
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>This cmdlet provides only common Windows PowerShell parameters.</p>
<p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsSipProxyUseDefault** cmdlet does not accept pipelined input.

## Return Types

The **New-CsSipProxyUseDefault** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.UseDefault object.

## См. также

#### Другие ресурсы

[New-CsSipProxyCustom](new-cssipproxycustom.md)  
[New-CsSipProxyRealm](new-cssipproxyrealm.md)

