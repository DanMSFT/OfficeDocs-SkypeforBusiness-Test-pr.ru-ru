﻿---
title: 'Lync Server 2013: разрешения на развертывание для SQL Server'
TOCTitle: Разрешения на развертывание для SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398375(v=OCS.15)
ms:contentKeyID: 49309817
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Разрешения на развертывание для SQL Server в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Microsoft SQL Server 2012 R2 имеет особые требования при установке и развертывании сервера Lync Server 2013. Поскольку Windows и SQL Server по-разному определяют свои параметры безопасности, вход в качестве администратора в домен Active Directory не предоставляет неявно разрешения на SQL Server. Необходимо также быть членом объекта sysadmin на настраиваемом сервере под управлением SQL Server.

## Разрешения, необходимые для установки базы данных и Lync Server

В следующих вариантах сценариев показаны три типа связей разрешений и членства в группах для установки файлов сервера Lync Server 2013 и баз данных SQL Server. Выберите сценарий, наиболее соответствующий потребностям вашей организации.

### Связь разрешений и членства в группах

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server или роль сервера Lync Server 2013</th>
<th>Типичные для роли разрешения SQL Server и членство в группах</th>
<th>Типичные для роли разрешения сервера Lync Server 2013 и членство в группах</th>
<th>Результат разрешений</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Администратор сервера Lync Server 2013</p></td>
<td><p>Должно быть предоставлено членство в группе безопасности системных администраторов SQL Server и членство в группе локальных администраторов SQL Server</p></td>
<td><p>Должен быть членом группы RTCUniversalServerAdmins</p></td>
<td><p>Администратор сервера Lync Server 2013 имеет соответствующие разрешения для установки как сервера Lync Server 2013, так и баз данных SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Администратор SQL Server</p></td>
<td><p>Член группы системных администраторов SQL Server (или эквивалентной группы) и член группы локальных администраторов SQL Server</p></td>
<td><p>Должен быть членом группы RTCUniversalServerReadOnly</p></td>
<td><p>Администратор SQL Server имеет соответствующие разрешения на установку как сервера Lync Server 2013, так и баз данных SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Оба администратора разделяют обязанности по установке</p></td>
<td><p>Администратор SQL Server является членом группы системных администраторов (или эквивалентной группы) и членом группы локальных администраторов SQL Server</p></td>
<td><p>Администратор сервера Lync Server 2013 является членом группы RTCUniversalServerAdmins</p></td>
<td><p>Администратор сервера Lync Server 2013 может устанавливать сервер Lync Server 2013, но не может устанавливать базы данных. Администратор SQL Server использует командлеты командной консоли Командная консоль Lync Server и командной консоли Windows PowerShell, предоставленные администратором сервера Lync Server 2013, для установки баз данных. Командная консоль командная консоль Lync Server 2013, используемая администратором SQL Server, устанавливается на сервере переднего плана. Это устраняет необходимость установки средств администрирования сервера Lync Server 2013 на сервере под управлением SQL Server.</p></td>
</tr>
</tbody>
</table>
