﻿---
title: New-CsPersistentChatAddin
TOCTitle: New-CsPersistentChatAddin
ms:assetid: 0566f4c2-0903-4dd1-87bc-784f0bdb4391
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204641(v=OCS.15)
ms:contentKeyID: 49308812
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPersistentChatAddin

 

_**Дата изменения раздела:** 2015-03-09_

Enables you to configure a new сохраняемый сеанс беседы add-in. A сохраняемый сеанс беседы add-in is a customized web page that can be embedded within a сохраняемый сеанс беседы client. Данный командлет впервые появился в Lync Server 2013.

## Синтаксис

    New-CsPersistentChatAddin -Name <String> -Url <String> [-PersistentChatPoolFqdn <String>]

## Examples

## Example 1

The command shown in Example 1 creates a new сохраняемый сеанс беседы add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.litwareinc.com. The URL parameter and the parameter value http://atl-cs-001.litwareinc.com/itchat specify the location of the add-in's webpage.

    New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com" -Url "http://atl-cs-001.litwareinc.com/itchat"

## Detailed Description

The сохраняемый сеанс беседы service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Add-ins serve as extensions to a сохраняемый сеанс беседы chat room. Add-ins are external applications (that is, items not built into сохраняемый сеанс беседы itself) that are associated with a particular chat room. For example, a help desk chat room might include a URL that links to a Web page or to a Silverlight application that shows the status of the day's help requests. Командная консоль Lync Server does not provide the ability to create these add-ins. Instead, the **CsPersistentChatAddin** cmdlets are used to associate (or disassociate) an add-in from a chat room.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPersistentChatAddin"}

**управления Lync Server:** To create a new сохраняемый сеанс беседы add-in using the управления Lync Server, click **сохраняемый сеанс беседы**, click **Add-in**, and then click **New**.

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
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Friendly name to be given to the сохраняемый сеанс беседы add-in. Names must be unique per серверов сохраняемого сеанса беседы.</p></td>
</tr>
<tr class="even">
<td><p><em>Url</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>URL of the webpage to be displayed by the сохраняемый сеанс беседы add-in.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the серверов сохраняемого сеанса беседы.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsPersistentChatAddin** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPersistentChatAddin** cmdlet creates new instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.AddinObject object.

## См. также

#### Другие ресурсы

[Get-CsPersistentChatAddin](get-cspersistentchataddin.md)  
[Remove-CsPersistentChatAddin](remove-cspersistentchataddin.md)  
[Set-CsPersistentChatAddin](set-cspersistentchataddin.md)

