﻿---
title: Disable-CsAdDomain
TOCTitle: Disable-CsAdDomain
ms:assetid: 98a4982c-7d8d-460d-bff9-243373b20290
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398785(v=OCS.15)
ms:contentKeyID: 49310610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsAdDomain

 

_**Дата изменения раздела:** 2015-03-09_

Undoes the domain preparation tasks carried out by the **Enable-CsAdDomain** cmdlet. This cmdlet is typically used only if you are uninstalling Lync Server from a domain. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Disable-CsAdDomain [-Confirm [<SwitchParameter>]] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 rolls back the domain preparation process in the local domain. Because the Force parameter is not included, the command will fail if the **Disable-CsAdDomain** cmdlet determines that at least one переднего плана, аудио- и видео конференций, or служб server is still active in the domain.

    Disable-CsAdDomain

## EXAMPLE 2

Example 2 rolls back the domain preparation process for the domain asia.litwareinc.com.

    Disable-CsAdDomain -Domain asia.litwareinc.com

## EXAMPLE 3

The command shown in Example 3 uses the Force parameter to force the rollback of the domain preparation process in the local domain. This means that rollback will occur even if the **Disable-CsAdDomain** cmdlet determines that at least one переднего плана, аудио- и видео конференций, or служб server is still active in the domain.

    Disable-CsAdDomain -Force

## Detailed Description

When you install Lync Server in a domain, that domain must be correctly prepared, a process that includes extending the Active Directory schema to allow for the addition of attributes specific to Lync Server as well as assigning the required Access Control Entries to the universal groups needed for managing and operating Lync Server. If you later decide to uninstall Lync Server (or if you encounter problems during the setup process), you might need to roll back these domain-level changes. The **Disable-CsAdDomain** cmdlet provides a way for you to undo all the domain-level modifications made by the **Enable-CsAdDomain** cmdlet.

Note that the tasks carried out by the **Disable-CsAdDomain** cmdlet are similar to the tasks carried out by the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /domain /action:DomainUnprep

Who can run this cmdlet: You must be a domain administrator in order to run the **Disable-CsAdDomain** cmdlet locally.

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
<td><p><em>Domain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain where domain preparation should be rolled back (for example, -Domain asia.litwareinc.com). If this parameter is not included, rollback will take place on the local domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the FQDN of the domain controller to be used when running <strong>Disable-CsAdDomain</strong>. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present rollback will occur even if the <strong>Disable-CsAdDomain</strong> cmdlet determines that at least one Front End, conferencing, or Web Services server is still active in the domain. If not present then the command will fail if a Front End, Conferencing, or Web Services server is still active in the domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Disable-CsAdDomain</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Доменные службы Active Directory this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\DisableDomain.html&quot;</p></td>
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

None. The **Disable-CsAdDomain** cmdlet does not accept pipelined input.

## Return Types

None.

## См. также

#### Другие ресурсы

[Enable-CsAdDomain](enable-csaddomain.md)  
[Get-CsAdDomain](get-csaddomain.md)

