﻿---
title: 'Lync Server 2013: настройка номеров доступа для конференц-связи с телефонным подключением'
TOCTitle: Настройка номеров доступа для конференц-связи с телефонным подключением
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398952(v=OCS.15)
ms:contentKeyID: 49311326
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013

 

_**Дата изменения раздела:** 2011-07-17_

При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.

Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами. Дополнительные сведения о регионах см. в разделе [Требования к связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) документации по планированию. Сведения о настройке абонентских групп для конференц-связи с телефонным подключением см. в статье [Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Нельзя использовать новый номер удаленного доступа до завершения репликации номеров доступа доменными службами Active Directory (AD DS). Репликация может занять несколько часов.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа. Чтобы изменить отображаемое имя, используйте командлет <strong>Set-CsDialInConferencingAccessNumber</strong>. Объекты Active Directory не следует изменять вручную. Сведения об изменении номеров доступа см. в документации Командная консоль Lync Server по командлету <strong>Set-CsDialInConferencingAccessNumber</strong>.</td>
</tr>
</tbody>
</table>


## Содержание

[Создание или изменение номера доступа к конференции с телефонным подключением в Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## См. также

#### Концепции

[Требования к связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Другие ресурсы

[Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)
