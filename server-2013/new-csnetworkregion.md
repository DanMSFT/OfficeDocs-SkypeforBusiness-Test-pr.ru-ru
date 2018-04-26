﻿---
title: New-CsNetworkRegion
TOCTitle: New-CsNetworkRegion
ms:assetid: 33a8efed-23d3-4a03-bede-80f649eaa7b9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425829(v=OCS.15)
ms:contentKeyID: 49309394
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkRegion

 

_**Дата изменения раздела:** 2015-03-09_

Creates a new network region. Network regions represent network hubs or backbones in an enterprise network. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsNetworkRegion -NetworkRegionID <String> <COMMON PARAMETERS>

    New-CsNetworkRegion -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -CentralSite <String> [-AudioAlternatePath <$true | $false>] [-BWAlternatePaths <PSListModifier>] [-BypassID <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-VideoAlternatePath <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In this example a new network region named NorthAmerica is created. The region name is specified as the value for the Identity parameter. A value is also specified for the optional Description parameter, describing this region as being composed of "All North American Locations." Finally, the CentralSite parameter receives a value of the name of the сайт for this region, Redmond-NA-MLS.

    New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS

## EXAMPLE 2

This example creates a new network region named EMEA that includes settings for an audio alternate path. To do this we call the **New-CsNetworkRegion** cmdlet, passing an Identity of EMEA. We assign a value for the required parameter CentralSite (in this example the name of the сайт for this region is Dublin-EU-Site), and then we specify the AudioAlternatePath parameter, passing it the value $False. Setting AudioAlternatePath to False indicates that if adequate bandwidth is not available, the audio calls will not be routed to an alternate path; instead, they will simply not be completed.

    New-CsNetworkRegion -Identity EMEA -CentralSite Dublin-EU-Site -AudioAlternatePath $False

## EXAMPLE 3

This example creates the same network region that was created in Example 2. However, in this case we use the BWAlternatePaths parameter to define alternate path settings rather than the AudioAlternatePath parameter. The first line in the example calls the **New-CsNetworkBWAlternatePath** cmdlet to create a new alternate path. An alternate path has only two properties: BWPolicyModality, which must be set to either audio or video (audio in this example); and AlternatePath, which must be either True or False (False in this example). We assign the output from this cmdlet, a reference to the alternate path object just created, to the variable $a.

In line 2 of this example we use this newly created alternate path when we create a new network region. To do this we call the **New-CsNetworkRegion** cmdlet, passing an Identity of EMEA. We assign a value for the required parameter CentralSite (in this example the name of the сайт for this region is Dublin-EU-Site), and then we specify the BWAlternatePaths parameter, passing it the variable ($a) containing the alternate path object we just created.

    $a = New-CsNetworkBWAlternatePath -BWPolicyModality "audio" -AlternatePath $False
    New-CsNetworkRegion -Identity EMEA -CentralSite Dublin-EU-Site -BWAlternatePaths $a

## Detailed Description

A network region interconnects various parts of a network across multiple geographic areas. Every network region must be associated with a сайт. The сайт is the data center site on which the call admission control (CAC) bandwidth policy service is running. Use this cmdlet to create a new network region. The parameters of this cmdlet allow you to provide settings that determine whether alternate paths through the Internet are allowed for audio and video connections, and can automatically generate the bypass ID.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsNetworkRegion** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkRegion"}

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
<td><p><em>CentralSite</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The сайт running the bandwidth policy service. This service must be enabled in order to use CAC. This service runs on the переднего плана or the Сервер Standard Edition.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>A unique identifier for the newly created network region. Regions are created only at the global scope, so this identifier does not need to specify a scope. Instead, it contains a string that is a unique name that identifies that region.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>This value is the same as the Identity. You cannot specify both an Identity and a NetworkRegionID; a value entered for one will be automatically used for both.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioAlternatePath</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</p>
<p>This parameter populates the BWAlternatePaths property. The value supplied to this parameter is stored in the AlternatePath property for the alternate path element with a BWPolicyModality value of Audio.</p>
<p>If you supply a value for this parameter, you cannot specify a value for the BWAlternatePaths parameter.</p>
<p>Default: True. Set this parameter to False only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this value must be True, regardless of bandwidth settings.</p></td>
</tr>
<tr class="odd">
<td><p><em>BWAlternatePaths</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of objects that contain information about whether alternate Internet connection paths are allowed if a media request is unable to complete along the preferred path (for example, if limits on that path have been exceeded). Alternate path objects must be created by calling the <strong>New-CsNetworkBWAlternatePath</strong> cmdlet.</p>
<p>If you supply a value for this parameter, you cannot supply values for either the AudioAlternatePath or VideoAlternatePath parameters.</p>
<p>Alternate paths for audio and video are enabled (AlternatePath = True) by default.</p></td>
</tr>
<tr class="even">
<td><p><em>BypassID</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A globally unique identifier (GUID). This GUID is used to map network regions to media bypass settings within a CAC or Enhanced 9-1-1 (E9-1-1) network configuration. (Use this BypassID value in the call to the <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet.)</p>
<p>If you do not specify a value for this parameter, a value will be automatically generated. If you do specify a value, it must be in the format of a GUID (for example, 3b24a047-dce6-48b2-9f20-9fbff17ed62a). Auto-generation is recommended. If you supply a value for this parameter, you’ll receive a confirmation prompt asking if you really want to supply this value rather than allow it to be auto-generated.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A string that describes the region. This parameter can be used to provide a more descriptive explanation of what the region is for than can be expressed by the Identity alone.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes. For example, if you supply a value to the BypassID parameter, you will not be prompted for confirmation.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Создает ссылку на объект без фиксации объекта в качестве постоянного изменения. Если выходные данные этого командлета, вызванного с помощью указанного параметра, назначаются переменной, можно внести изменения в свойства ссылки на объект и затем зафиксировать эти изменения, вызвав соответствующий командлет Set-.</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoAlternatePath</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</p>
<p>This parameter populates the BWAlternatePaths property. The value supplied to this parameter is stored in the AlternatePath property for the alternate path element with a BWPolicyModality value of Video.</p>
<p>If you supply a value for this parameter you cannot specify a value for the BWAlternatePaths parameter.</p>
<p>Default: True. Set this parameter to False only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this value must be True, regardless of bandwidth settings.</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType.

## См. также

#### Другие ресурсы

[Remove-CsNetworkRegion](remove-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[New-CsNetworkBWAlternatePath](new-csnetworkbwalternatepath.md)

