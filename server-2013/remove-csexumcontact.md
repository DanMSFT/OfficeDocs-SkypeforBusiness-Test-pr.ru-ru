﻿---
title: Remove-CsExUmContact
TOCTitle: Remove-CsExUmContact
ms:assetid: d79f7082-f58b-4cc3-a90d-230111e32850
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398946(v=OCS.15)
ms:contentKeyID: 49311316
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsExUmContact

 

_**Дата изменения раздела:** 2015-03-09_

Removes an Auto Attendant or Subscriber Access contact object for hosted обмена сообщениями Exchange. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsExUmContact -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the обмена сообщениями Exchange contact with the SIP address exumsa1@fabrikam.com.

    Remove-CsExUmContact -Identity sip:exumsa1@fabrikam.com

## EXAMPLE 2

This example removes all обмена сообщениями Exchange contacts with LineURI values beginning with tel:425. The first part of this command calls the **Get-CsExUmContact** cmdlet with the Filter parameter, using this expression as the filter: LineURI -like "tel:425\*". That filter specifies that we want to retrieve the обмена сообщениями Exchange contact objects that have a LineURI matching the wildcard string tel:425\*. In other words, all line URIs that start with the string tel:425 and end with any set of characters. Once we have that collection of objects, we pipe the collection to the **Remove-CsExUmContact** cmdlet, which removes all the items in the collection.

    Get-CsExUmContact -Filter {LineURI -like "tel:425*"} | Remove-CsExUmContact

## Detailed Description

Lync Server works with обмена сообщениями Exchange to provide several voice-related capabilities, including Auto Attendant and Subscriber Access. When обмена сообщениями Exchange is provided as a hosted service (rather than on-premises), contact objects must be created by using Windows PowerShell to apply the Auto Attendant and Subscriber Access functionality. Any of the objects that are created can be removed with the **Remove-CsExUmContact** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsExUmContact** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsExUmContact"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>The unique identifier of the contact object you want to remove. Contact identities can be specified using one of four formats: 1) The contact’s SIP address; 2) the contact's user principal name (UPN); 3) the contact's domain name and logon name, in the form domain\logon (for example, litwareinc\exum1); and, 4) the contact's Active Directory display name (for example, Team Auto Attendant).</p>
<p>Full data type: Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
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

Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact object. Accepts pipelined input of обмена сообщениями Exchange contact objects.

## Return Types

This cmdlet does not return an object. It removes an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact.

## См. также

#### Другие ресурсы

[New-CsExUmContact](new-csexumcontact.md)  
[Set-CsExUmContact](set-csexumcontact.md)  
[Get-CsExUmContact](get-csexumcontact.md)  
[Move-CsExUmContact](move-csexumcontact.md)

