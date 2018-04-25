﻿---
title: Get-CsPool
TOCTitle: Get-CsPool
ms:assetid: e0911c68-9a0a-461a-88d6-c610c6cd996c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398992(v=OCS.15)
ms:contentKeyID: 49311421
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPool

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о пулах, используемых в развертывании Lync Server. Пулы — это коллекции компьютеров на сайте, на которых работает один и тот же набор служб Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsPool [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsPool [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Site <String>]

## Примеры

## ПРИМЕР 1

В примере 1 извлекаются все пули, найденные в развертывании Lync Server.

    Get-CsPool

## ПРИМЕР 2

В примере 2 отображаются подробные сведения о компьютерах, обнаруженных в каждом пуле. Для этого сначала вызывается командлет **Get-CsPool**, а затем полученные данные отправляются в командлет **Select-Object**. Далее используется параметр ExpandProperty, чтобы "развернуть" значение свойства Computers. Свойство Computers представляет собой массив объектов, представляющих каждый компьютер в пуле. Разворачивая свойство Computers, можно получить подробные сведения о каждом из этих компьютеров.

    Get-CsPool | Select-Object -ExpandProperty Computers

## ПРИМЕР 3

В примере 3 с помощью параметра Identity извлекаемые данные ограничиваются теми, которые относятся к пулу с удостоверением atl-cs-001.litwareinc.com.

    Get-CsPool -Identity atl-cs-001.litwareinc.com

## ПРИМЕР 4

В примере 4 извлекаются все пулы, обнаруженные в узле Redmond. Для этого используется параметр Site, значение "Redmond" которого ограничивает данные пулами, свойство Site которых имеет значение Redmond.

    Get-CsPool -Site "Redmond"

## ПРИМЕР 5

Команда, показанная в примере 5, извлекает коллекцию всех пулов, в которых не установлены никакие службы Lync Server. Для выполнения этой задачи сначала вызывается командлет **Get-CsPool** без параметров. который возвращает коллекцию всех пулов, используемых в организации в текущий момент. Затем эта коллекция передается в командлет **Where-Object**, который отбирает те пулы, свойство Services.Count которых имеет значение 0. Если это свойство имеет значение 0, то в данном пуле отсутствуют настроенные службы Lync Server.

    Get-CsPool | Where-Object {$_.Services.Count -eq 0}

## Подробное описание

В Lync Server пул представляет собой один или несколько компьютеров одного узла, на которых работает один и тот же набор служб, Например, если в узле Redmond имеется один сервер, на котором работает сервер-посредник, то имеется пул серверов-посредников, состоящий из этого одного компьютера. Если в узле Redmond имеется два компьютера, на которых работает сервер-посредник, то имеется пул серверов-посредников, состоящий из двух компьютеров. Количество пулов, используемых в организации, зависит от имеющегося количества серверов и от разных служб, работающих на этих серверах.

Командлет **Get-CsPool** позволяет получать сведения о каждом пуле, используемом в организации, включая сведения о службах, работающих в каждом пуле.

По умолчанию право на локальный запуск командлета **Get-CsPool** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPool"}

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
<th>Параметр</th>
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет использовать подстановочные знаки при указании удостоверения извлекаемого пула. Например, для извлечения всех пулов с удостоверениями, заканчивающимися строкой &quot;.fabrikam.com&quot;, можно использовать следующий синтаксис: -Filter &quot;*.fabrikam.com&quot;.</p>
<p>В одной команде нельзя одновременно использовать параметры Filter и Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Полное доменное имя извлекаемого пула. Например: -Identity atl-cs-001.litwareinc.com.</p>
<p>Если этот параметр не указан, то будут возвращены все пулы в организации.</p></td>
</tr>
<tr class="odd">
<td><p><em>Site</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Возвращает все пулы, найденные в указанном узле. На нужный узел следует ссылаться с помощью отображаемого имени (DisplayName) узла (Redmond), а не с помощью удостоверения (site:Redmond). Например: -Site &quot;Redmond&quot;. Извлечь отображаемые имена для узлов можно с помощью следующей команды:</p>
<p>Get-CsSite | Select-Object Identity, DisplayName</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsPool** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsPool** возвращает экземпляры объекта Microsoft.Rtc.Management.Deploy.Internal.Cluster.

## См. также

#### Другие ресурсы

[Get-CsSite](get-cssite.md)  
[Get-CsTopology](get-cstopology.md)
