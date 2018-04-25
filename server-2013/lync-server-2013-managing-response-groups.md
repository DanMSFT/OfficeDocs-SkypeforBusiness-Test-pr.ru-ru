﻿---
title: Управление группами ответа в Lync Server 2013
TOCTitle: Управление группами ответа в Lync Server 2013
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg520996(v=OCS.15)
ms:contentKeyID: 49309872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление группами ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-01_

Группы ответа — это компонент управления вызовами, который позволяет поместить в очередь вызовы, предназначенные определенной области, например службе технической поддержки, и затем перенаправить их группе назначенных людей, которых называют *агентами*.

Чтобы управлять группами ответов, следует настроить группы агентов, очереди и рабочие процессы, которые определяют, что происходит с вызовом с момента его получения до момента ответа на него агентом.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если в одном пуле развертывания группы ответа у вас используется более 300 рабочих процессов, для их создания лучше всего использовать командлеты командной консоли Командная консоль Lync Server. Если для создания рабочих процессов в пуле с более чем 300 рабочими процессами использовать средство настройки группы ответа, загрузка веб-страницы занимает слишком много времени.</td>
</tr>
</tbody>
</table>


Темы в данном разделе содержат пошаговые процедуры по настройке и обслуживанию групп ответов в развертывании

## Содержание

  - [Управление группами агентов группы ответов](lync-server-2013-managing-response-group-agent-groups.md)

  - [Управление очередями группы ответа](lync-server-2013-managing-response-group-queues.md)

  - [Управление рабочими процессами для группы ответа](lync-server-2013-managing-response-group-workflows.md)

  - [Управление параметрами группы ответа уровня приложения в Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Перемещение групп ответа в новый пул](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Управление группами ответов в Lync Server 2013 в аварийном режиме](lync-server-2013-managing-response-groups-during-a-disaster.md)
