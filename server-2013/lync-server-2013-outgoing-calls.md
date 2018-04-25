﻿---
title: 'Lync Server 2013: исходящие звонки'
TOCTitle: Исходящие звонки
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994049(v=OCS.15)
ms:contentKeyID: 52058267
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Исходящие звонки в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

На маршрутизацию исходящих звонков пользователей, для которых включена маршрутизация на основе местоположения, влияет расположение конечной точки пользователя в сети. В приведенной ниже таблице показано, как маршрутизация на основе местоположения влияет на маршрутизацию исходящих звонков в зависимости от расположения конечной точки звонящего абонента.

### Абонент совершает исходящий звонок ТСОП

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Конечная точка пользователя расположена на сетевом сайте, для которого включена маршрутизация на основе местоположения.</th>
<th>Конечная точка пользователя расположена на неизвестном сетевом сайте или на сайте, для которого не включена маршрутизация на основе местоположения.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Авторизация исходящих звонков</p></td>
<td><p>Звонок авторизован на основе политики голосовой связи пользователя.</p></td>
<td><p>Звонок авторизован на основе политики голосовой связи пользователя.</p></td>
</tr>
<tr class="even">
<td><p>Маршрутизация исходящего звонка</p></td>
<td><p>Звонок маршрутизируется в соответствии с политикой маршрутизации голосовой связи для данного сетевого сайта.</p></td>
<td><p>Звонок маршрутизируется в соответствии с политикой голосовой связи пользователя и только через магистрали, для которых не включена маршрутизация на основе местоположения (если они доступны).</p></td>
</tr>
</tbody>
</table>


## См. также

#### Другие ресурсы

[Сценарии маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)
