﻿---
title: 'Lync Server 2013: технические требования для сервера сохраняемого чата'
TOCTitle: Технические требования для сервера сохраняемого чата
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398495(v=OCS.15)
ms:contentKeyID: 49310073
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Технические требования для сервера сохраняемого чата в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Для каждого компьютера, на котором размещается сохраняемого сеанса беседы, должен быть доступ к существующей топологии Lync Server 2013 со следующими компонентами:

  - **Lync Server 2013, переднего плана.**  переднего плана – это основа для маршрутизации протокола SIP, которая реализует связь между компьютерами с сохраняемого сеанса беседы и сохраняемый сеанс беседы. Перед развертыванием сохраняемого сеанса беседы проверьте развертывание Lync Server 2013, Standard Edition или Lync Serverпереднего плана и всех других внутренних компьютеров с Lync Server подходящим для организации образом.

В следующих разделах описываются определенные требования для сохраняемого сеанса беседы и базы данных, в которой хранятся данные сохраняемый сеанс беседы.

## Требования сохраняемого сеанса беседы

Дополнительные сведения о рекомендуемом оборудовании для развертывания Lync Server и последней версии сохраняемого сеанса беседы см. в разделе [Аппаратные серверные платформы для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

Дополнительные сведения о поддержке серверов и средств в операционных системах для Lync Server и сохраняемого сеанса беседы см. в разделе [Поддержка сервера и средств в операционной системе в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

Дополнительные сведения о дополнительном программном обеспечении, необходимом для развертывания сохраняемого сеанса беседы см. в следующей таблице.

### Необходимое программное обеспечение для сохраняемого сеанса беседы

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Программное обеспечение</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Очереди сообщений</p></td>
<td><p>Используется сохраняемого сеанса беседы и службой соответствия сохраняемый сеанс беседы, если она развернута.</p></td>
</tr>
</tbody>
</table>


## Требования к базе данных сохраняемого сеанса беседы

сохраняемого сеанса беседы использует базу данных сохраняемый сеанс беседы для хранения журнала бесед, конфигурации и данных подготовки пользователей. При необходимости используется база данных соответствия сохраняемый сеанс беседы для сохранения данных соответствия.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>База данных сохраняемый сеанс беседы (mgc) и база данных соответствия (mgccomp) могут размещаться в одном экземпляре SQL Server или на другом SQL-серверы.</td>
</tr>
</tbody>
</table>


Чтобы подготовить платформу сервера базы данных, убедитесь, что каждый компьютер соответствует требованиям к оборудованию, а затем установите все необходимые программные компоненты.

Для платформы серверов баз данных сохраняемый сеанс беседы требуется то же оборудование, что и для сервера внутренней базы данных Lync Server. Дополнительные сведения см. в разделе [Аппаратные серверные платформы для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

На сервере базы данных убедитесь, что установлено одно из следующих приложений:

  - Microsoft SQL Server 2012. Дополнительные сведения по установке Microsoft SQL Server 2012 см. в разделе «Установка SQL Server 2012» по адресу [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Дополнительные сведения по установке Microsoft SQL Server 2008 R2 см. в разделе «Установка SQL Server (SQL Server 2008 R2)» по адресу [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).

## Требования к сертификатам сохраняемого сеанса беседы

Дополнительные сведения о получении сертификатов, создании базы данных SQL Server и хранилища файлов см. в разделе [Развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md)в документации по развертыванию.
