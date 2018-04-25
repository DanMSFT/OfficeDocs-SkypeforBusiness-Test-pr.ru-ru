﻿---
title: 'Lync Server 2013: действия по подготовке и развертыванию гибридной среды Lync Server'
TOCTitle: Действия по подготовке и развертыванию гибридной среды Lync Server 2013
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205157(v=OCS.15)
ms:contentKeyID: 49310738
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Действия по подготовке и развертыванию гибридной среды Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

В следующей таблице перечислены действия по подготовке среды к гибридному развертыванию Microsoft Lync Online и Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Выполнение</th>
<th>Шаг</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p>Создание учетной записи клиента для Office 365 и включение Lync Online</p></td>
<td><p>Чтобы больше узнать о Office 365 и Lync Online, перейдите по ссылке <a href="http://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</p>
<p>Чтобы убедиться, что среда готова к использованию Office 365, см. раздел <a href="http://go.microsoft.com/fwlink/p/?linkid=401408">Системные требования</a>.</p>
<p>90% Более подробные сведения о настройке Office 365 см. на веб-страницах <a href="http://go.microsoft.com/fwlink/p/?linkid=254982">Начало работы с Office 365</a> и <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Настройка Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Добавление домена и проверка прав на владение доменом</p></td>
<td><p>Домен иногда называют <em>именным доменом</em> . Вам необходимо добавить домен в клиент Office 365 и затем проверить его в Office 365. Эти действия предназначены для проверки прав владения доменом.</p>
<p>Чтобы добавить домен в клиент Office 365, выполните действия, описанные на веб-странице <a href="http://go.microsoft.com/fwlink/p/?linkid=254983">Добавление домена в Office 365</a>.</p>
<p>Выполните все шаги, описанные в подразделах, включая подраздел &quot;Изменение записей DNS для служб Office 365&quot;.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Проверка готовности среды</p></td>
<td><p>Для развертывания Office 365 можно использовать помощник по настройке Office 365. Дополнительные сведения см. в статье <a href="http://go.microsoft.com/fwlink/p/?linkid=254985">Использование помощника по настройке для определения степени готовности Office 365</a>.</p>
<p>Подробнее об использовании данного инструмента и развертывании Office 365 см. в <a href="http://go.microsoft.com/fwlink/p/?linkid=257337">руководстве по развертыванию Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Подготовка к синхронизации Active Directory</p></td>
<td><p>Синхронизация Active Directory обеспечивает непрерывную синхронизацию локальной службы Active Directory и Office 365. Это позволяет не только создавать синхронизированные версии каждой учетной записи пользователя или группы, но и выполнять синхронизацию глобального списка адресов (GAL) между локальной средой сервера Microsoft Exchange Server и Microsoft Exchange Online..</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо синхронизировать учетные записи Active Directory для всех пользователей Lync в организации между локальным и сетевым развертываниями Lync, даже если пользователи не перемещаются в Lync Online. Если не синхронизировать всех пользователей, связь между пользователями локального и сетевого развертываний организации может функционировать неправильно.</td>
</tr>
</tbody>
</table>

</div>
<p>Инструкции по подготовке среды к синхронизации Active Directory, включая настройку единого входа, см. на веб-странице <a href="http://go.microsoft.com/fwlink/p/?linkid=254988">План внедрения синхронизации службы каталогов</a>.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Создание сертификатов для служб федерации Active Directory (AD FS)</p></td>
<td><p>Необходимо создать сертификаты, которые используются для федерации удостоверений Office 365. Дополнительные сведения см. в разделе «Сертификаты сервера федерации» темы «Планирование и развертывание AD FS для использования с функцией единого входа» статьи <a href="http://go.microsoft.com/fwlink/p/?linkid=285376">Контрольный список: Внедрение и управление единым входом с помощью служб федерации Active Directory</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Назначение сертификатов Active Directory</p></td>
<td><p>После создания сертификатов, используемых для федерации удостоверений Office 365, вы должны установить и назначить их.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Перемещение пользователей в Skype для бизнеса Online</p></td>
<td><p>После завершения подготовки и настройки среды для Skype для бизнеса Online вы можете переместить пользователей в Lync Online.</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-move-users-to-lync-online.md">Перемещение пользователей в Lync Online в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Администрирование пользователей в гибридном развертывании</p></td>
<td><p>Более подробные сведения об администрировании пользователей в гибридном развертывании см. в разделе <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>
