﻿---
title: New-CsSipResponseCodeTranslationRule
TOCTitle: New-CsSipResponseCodeTranslationRule
ms:assetid: f7667ffd-3d11-40ec-87d4-7f9b1a861aae
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413041(v=OCS.15)
ms:contentKeyID: 49311701
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsSipResponseCodeTranslationRule

 

_**Дата изменения раздела:** 2015-03-09_

Creates a new SIP response code translation rule. These rules enable administrators to map SIP response codes with values between 400 and 699 to the values used by Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsSipResponseCodeTranslationRule -Name <String> -Parent <String> <COMMON PARAMETERS>

    New-CsSipResponseCodeTranslationRule -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -TranslatedResponseCode <Int32> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Priority <Int32>] [-ReceivedISUPCauseValue <Int32>] [-ReceivedResponseCode <Int32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new SIP response code translation rule with the Identity PstnGateway:192.168.0.240/Rule404. This rule translates a received response code of 434 to the standard SIP response code 404 (Not Found).

    New-CsSipResponseCodeTranslationRule -Identity "PstnGateway:192.168.0.240/Rule404" -ReceivedResponseCode 434 -TranslatedResponseCode 404

## EXAMPLE 2

The command shown in Example 2 performs the same task as the command shown in Example 1. In Example 2, however, the Parent and Name parameters are used instead of the Identity parameter. This simply shows an alternate way of creating a new SIP response code translation rule that has the Identity PstnGateway:192.168.0.240/Rule404.

    New-CsSipResponseCodeTranslationRule -Parent "PstnGateway:192.168.0.240" -Name "Rule404" -ReceivedResponseCode 434 -TranslatedResponseCode 404

## Detailed Description

SIP trunking provides a way to connect a Voice over Internet Protocol (VoIP) network (such as Enterprise Voice) with the public switched telephone network (PSTN). In Lync Server, the посредник uses trunking peers to interact with the PSTN network. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call. When a посредник trunking peer receives that ISUP cause code, it converts that code to a SIP response code, which is then sent to the посредник itself. In turn, Lync Server uses these response codes to make its outbound routing decisions. For example, a malfunctioning gateway might automatically be assigned a "less-preferred" status; this minimizes the use of the malfunctioning gateway, and thus maximizes the chance of a call being successfully completed.

However, not all gateways use the recommended ISUP cause code to SIP response code mapping used by Lync Server. For these gateways, administrators can use the **CsSipResponseCodeTranslationRule** cmdlets to map the gateway SIP response code (in combination with the ISUP cause code, if that cause code is available) to a SIP response code used by Lync Server. For example, a gateway might map ISUP cause code 34 ("No circuit/channel is available") to SIP response code 486 ("Busy here"). Based on a response code of 486, the outbound routing logic of Lync Server will not attempt to find a new gateway in order to complete the call.

For Lync Server, however, that SIP response code of 486 should instead be mapped to SIP response code 503. A response code of 503 triggers the retry mechanism in the outbound routing logic of Lync Server; that means that the system will try to find another gateway in order to complete the call. To handle this situation, you can create a translation rule that maps the combination of ISUP cause code 34 and SIP response code 486 to a SIP response code of 503. These new translation rules are created by using the **New-CsSipResponseCodeTranslationRule** cmdlet. Translation rules can be assigned to the global scope, the site scope, or to the service scope (for the шлюзов PSTN only).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSipResponseCodeTranslationRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSipResponseCodeTranslationRule"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the translation rule to be created. The identity for a translation rule consists of two parts: the scope where the rule is to be assigned and the name to be given to the rule. For example, a translation rule named Rule404 to be created at the global scope would have an Identity that looks like this: global/Rule404.</p>
<p>Instead of using the Identity parameter, you can use the Parent and Name parameters when creating a new translation rule.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name used to differentiate one translation rule from another. Names must be unique within a given scope; for example, the Redmond site can only have one translation rule named Rule404. However, you can have a translation rule named Rule404 at the Redmond site and another rule named Rule404 at the Dublin site.</p>
<p>The Name parameter must always be used in conjunction with the Parent parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Scope where the new translation rule is to be assigned. To assign a rule to the global scope, use this syntax: -Parent global. To assign a rule to the site scope, use syntax like this: -Parent site:Redmond. To assign a rule to the service scope, use syntax similar to this: -Parent PstnGateway:192.168.0.242.</p>
<p>The Parent parameter must always be used in conjunction with the Name parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>TranslatedResponseCode</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of the Lync Server SIP response code that the ReceivedResponseCode and/or the ReceivedISUPCauseCode should be translated to. Translated response codes can be any integer value between 400 and 699, inclusive.</p></td>
</tr>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Создает ссылку на объект без фиксации объекта в качестве постоянного изменения. Если выходные данные этого командлета, вызванного с помощью указанного параметра, назначаются переменной, можно внести изменения в свойства ссылки на объект и затем зафиксировать эти изменения, вызвав соответствующий командлет Set-.</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Relative priority of the translation rule. Rules are processed in order of their assigned priority; the first rule to be processed has a priority of 0; the second rule to be processed has a priority of 1; and so on. If not specified the new rule will be given the lowest priority in its scope.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReceivedISUPCauseValue</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of the ISDN User Part (ISUP) code that must be present in the SIP response message used by a gateway when responding to an INVITE message. A value of -1 indicates that only the SIP response code will be used when executing the translation rule; the ISUP cause code will be ignored.</p></td>
</tr>
<tr class="even">
<td><p><em>ReceivedResponseCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of the SIP response code used by a gateway when responding to an INVITE message. A response code can be any integer value between 400 and 699, inclusive. Although the cmdlet will accept integer values less than 400, these are not recognized as final responses. As a result, the translation rule will never be used. A value of 0 means that only the ISUP cause code will be used when executing the translation rule; the SIP response code will be ignored.</p></td>
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

None. The **New-CsSipResponseCodeTranslationRule** cmdlet does not accept pipelined input.

## Return Types

The **New-CsSipResponseCodeTranslationRule** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.SipResponseCodeTRanslationRule\#Decorated object.

## См. также

#### Другие ресурсы

[Get-CsSipResponseCodeTranslationRule](get-cssipresponsecodetranslationrule.md)  
[Remove-CsSipResponseCodeTranslationRule](remove-cssipresponsecodetranslationrule.md)  
[Set-CsSipResponseCodeTranslationRule](set-cssipresponsecodetranslationrule.md)

