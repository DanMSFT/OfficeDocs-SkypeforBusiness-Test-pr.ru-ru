﻿---
title: 'Lync Server 2013: процесс развертывания для интеграции локальной единой системы обмена сообщениями'
TOCTitle: Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425737(v=OCS.15)
ms:contentKeyID: 49309233
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Если вы хотите интегрировать систему обмена сообщениями Exchange с Lync Server 2013, необходимо выполнить задачи, описанные в данном разделе. Также обязательно изучите рекомендации по планированию и развертыванию, описанные в статье [Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). В этом разделе предполагается, что вы развернули Lync Server 2013 с совместно размещенным сервером-посредником и активировали пользователей для Lync Server 2013, но не предполагается, что вы гарантированно выполнили все действия по развертыванию и настройке для активации системы корпоративной голосовой связи, описанные в статье [Развертывание корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.

## Процесс интеграции единой системы обмена сообщениями

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Важно скоординировать администраторов Exchange вашей организации, чтобы подтвердить задачи, которые они будут выполнять для обеспечения успешной интеграции.</td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Выполните развертывание одного из следующих компонентов:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 с пакетом обновления 1 (SP2) или с последним пакетом обновления</p></li>
<li><p>Microsoft Exchange Server 2010 или с последним пакетом обновления</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Если вы используете Microsoft Exchange Server 2013, установите следующие роли Exchange Server в том же лесу, где расположен Lync Server 2013, или в другом лесу:</p>
<ul>
<li><p>клиентский доступ;</p></li>
<li><p>почтовый ящик.</p></li>
</ul>
<p>Если Microsoft Exchange Server 2013 и обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы обеспечить доверие лесу Lync Server 2013.</p>
<p>Если вы используете Exchange 2010, установите следующие роли Exchange Server в том же лесу, где расположен Lync Server 2013, или в другом лесу:</p>
<ul>
<li><p>единая система обмена сообщениями;</p></li>
<li><p>транспортный сервер-концентратор;</p></li>
<li><p>клиентский доступ;</p></li>
<li><p>почтовый ящик.</p></li>
</ul>
<p>Если Lync Server 2013 и обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы обеспечить доверие лесу Lync Server 2013.</p></td>
<td><p>Администраторы предприятия (если это первый сервер Exchange Server в организации)</p>
<p>- ИЛИ -</p>
<p>Администратор организации Exchange (если это не первый сервер Exchange Server в организации)</p></td>
<td><p>Изучите соответствующую документацию для вашей версии Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>документация по развертыванию Exchange Server 2007 по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>документация по развертыванию Exchange Server 2010 или последнего пакет обновления по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>планирование и развертывание Microsoft Exchange Server 2013 по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Установите сертификаты.</p></td>
<td><p>Загрузите и установите сертификаты для каждого сервера обмена сообщениями Exchange из доверенного корневого центра сертификации. Эти сертификаты требуются для функции привязки безопасности транспортного уровня Mutual-TLS (MTLS) между сервером обмена сообщениями Exchange и сервером Lync Server 2013.</p></td>
<td><p>Администраторы</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Создайте и настройте новую абонентскую группу SIP обмена сообщениями Exchange.</p></td>
<td><p>На сервере обмена сообщениями Exchange создайте абонентскую группу SIP на основе требований к развертыванию вашей организации.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p>Для Exchange 2007 SP1 или более поздней версии пакета обновлений см. статью «Создание новой абонентской группы для единой системы обмена сообщениями с универсальным кодом ресурса SIP» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновлений см. раздел «Создание абонентской группы единой системы обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</p>
<p>Для Exchange 2013 см. раздел «Единая система обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Настройте параметры безопасности для абонентской группы SIP обмена сообщениями Exchange.</p></td>
<td><p>Для шифрования трафика Enterprise Voice настройте параметры безопасности абонентской группы SIP обмена сообщениями Exchange как <strong>С защитой SIP</strong> или <strong>С защитой</strong>. Это особенно важно, если вы уже развернули или планируете развернуть устройства Lync Phone Edition в своей среде. Чтобы устройства Lync Phone Edition работали в среде с интеграцией с обмена сообщениями Exchange, параметры шифрования Lync Server должны соответствовать параметрам безопасности абонентской группы обмена сообщениями Exchange. Дополнительные сведения см. в документации по развертыванию.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями на сервере Microsoft Exchange в Lync Server 2013</a></p>
<p>Для Exchange 2007 SP1 или более поздней версии пакета обновлений см. также следующие статьи:</p>
<p>«Настройка параметров безопасности для телефонной группы единой системы обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</p>
<p></p>
<p>Для Exchange 2010 или более поздней версии пакета обновления см. также следующие статьи:</p>
<p>«Настройка безопасности VoIP в абонентской группе единой системы обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</p>
<p></p>
<p>Для Exchange 2013 см. раздел «Единая система обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Добавьте серверы единой системы обмена сообщениями в абонентскую группу SIP обмена сообщениями Exchange.</p></td>
<td><p>Чтобы добавленный сервер единой системы обмена сообщениями отвечал на входящие звонки и обрабатывал их, необходимо добавить его в абонентскую группу единой системы обмена сообщениями. В этом случае добавьте сервер в абонентскую группу SIP обмена сообщениями Exchange.</p></td>
<td><p>Администраторы</p>
<p>Администраторы Exchange Server</p></td>
<td><p>Для Exchange 2007 SP1 или более поздней версии пакета обновлений см. статью «Добавление сервера единой системы обмена сообщениями к телефонной группе» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновлений см. статью «Просмотр или настройка свойств сервера единой системы обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</p>
<p></p>
<p>Для Exchange 2013 см. раздел «Единая система обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Настройте SIP-адреса для почтовых ящиков.</p></td>
<td><p>Назначьте SIP-адреса почтовым ящикам пользователей Enterprise Voice, которые будут применять компоненты обмена сообщениями Exchange.</p></td>
<td><p>Администратор сервера Lync Server 2013</p>
<p>Администратор получателей Exchange</p></td>
<td><p>Для Exchange 2007 SP1 или более поздней версии пакета обновлений см. статью «Добавление, удаление и изменение SIP-адреса для пользователя с включенной поддержкой единой системы обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновлений см. статью «Включение поддержки единой системы обмена сообщениями для пользователя» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</p>
<p></p>
<p>Для Exchange 2013 см. раздел «Единая система обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Запустите скрипт exchucutil.ps1.</p></td>
<td><p>На сервере, на котором запущены службы обмена сообщениями Exchange, откройте командную консоль Exchange и выполните скрипт exchucutil.ps1, который выполняет следующие задачи:</p>
<ul>
<li><p>предоставляет Lync Server 2013 разрешение на чтение объектов обмена сообщениями Exchange  Доменные службы Active Directory, в частности, абонентских групп SIP, созданных на предыдущем шаге;</p></li>
<li><p>создайте объект IP-шлюза единой системы обмена сообщениями в Active Directory для каждого пула Lync Server 2013 Enterprise Edition или сервера Standard Edition, на котором размещаются пользователи, активированные для применения Enterprise Voice;</p></li>
<li><p>создает сервисную группу обмена сообщениями Exchange для каждого шлюза. Пилотным идентификатором сервисной группы будет имя абонентской группы, связанной с соответствующим шлюзом. Их необходимо сопоставлять 1:1, если абонентских групп несколько.</p></li>
</ul></td>
<td><p>Администратор организации Exchange</p>
<p>Администратор получателей Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями на сервере Microsoft Exchange в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройте абонентские группы Lync Server 2013.</p></td>
<td><p>Если вы реализуете интеграцию с Exchange 2007 SP1, более поздней версией пакета обновлений или Exchange 2010, создайте новую абонентскую группу корпоративной голосовой связи с именем, совпадающим с полным доменным именем абонентской группы единой системы обмена сообщениями Exchange.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Это потребуется сделать для каждой абонентской группы единой системы обмена сообщениями.</td>
</tr>
</tbody>
</table>

</div>
<p>Если вы реализуете интеграцию с Exchange 2010 SP1, убедитесь, что настроены соответствующие абонентские группы корпоративной голосовой связи глобального уровня, уровня сайта или пула.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы реализуете интеграцию с Exchange 2010 SP1, имена абонентской группы Lync Server и абонентской группы SIP единой системы обмена сообщениями Exchange необязательно должны совпадать.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Настройка абонентских групп в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Запустите средство интеграции обмена сообщениями Exchange.</p></td>
<td><p>На сервере Lync Server 2013 запустите средство <strong>ocsumutil.exe</strong>, которое выполняет следующие задачи:</p>
<ul>
<li><p>создает объекты контактов абонентского доступа и автосекретаря;</p></li>
<li><p>проверяет, существует ли абонентская группа корпоративной голосовой связи с именем, совпадающим с полным доменным именем абонентской группы единой системы обмена сообщениями Exchange. Если вы используете Exchange 2010 SP1 или более поздней версии, имена абонентских групп необязательно должны совпадать и вы можете игнорировать соответствующее предупреждение средства интеграции.</p></li>
</ul>
<p>Это средство сканирует Active Directory на наличие параметров единой системы обмена сообщениями Exchange и позволяет администратору Lync Server 2013 просматривать, создавать и изменять объекты контактов.</p></td>
<td><p>RTCUniversalServerAdmins <em>и</em> RTCUniversalUserAdmins</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для успешного выполнения ocsumutil.exe пользователь должен принадлежать обеим этим группам.</td>
</tr>
</tbody>
</table>

</div>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы создать объекты контактов, пользователей, запускающий средство ocsumutil.exe, должен обладать нужными разрешениями для подразделения Active Directory, в котором хранятся новые объекты контактов. Эти разрешения можно получить, выполнив командлет <strong>Grant-CsOUPermission</strong>. Дополнительные сведения см. в документации по командной консоли Командная консоль Lync Server.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Если необходимо, выполните другие действия по настройке корпоративной голосовой связи.</p></td>
<td><p>Если вы еще не настроили параметры корпоративной голосовой связи для серверов или пользователей, выполните одно или несколько из следующих действий:</p>
<ul>
<li><p>разверните и настройте</p>
<p>шлюзы и серверы-посредники телефонной сети общего пользования (ТСОП);</p></li>
<li><p>определите политики голосовой связи, записи использования ТСОП и маршруты исходящих вызовов;</p></li>
<li><p>активируйте пользователей для применения Enterprise Voice;</p></li>
<li><p>при необходимости настройте абонентские группы для определенных пользователей.</p></li>
</ul>
<p>В зависимости от активируемых функций корпоративной голосовой связи могут потребоваться и другие действия по настройке.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>См. следующие разделы:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Настройка политик голосовой связи, записей использования ТСОП и маршрутов голосовых вызовов в Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Включение поддержки Enterprise Voice для пользователей в обмена сообщениями Exchange.</p></td>
<td><p>На сервере обмена сообщениями Exchange убедитесь, что создана политика почтовых ящиков единой системы обмена сообщениями и каждому пользователю назначен уникальный добавочный номер, а затем включите поддержку единой системы обмена сообщениями для пользователей.</p></td>
<td><p>Администратор получателей Exchange</p></td>
<td><p>Для Exchange 2007 SP1 или более поздней версии пакета обновлений см. статью «Включение поддержки единой системы обмена сообщениями для пользователя» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновлений см. статью «Включение единой системы обмена сообщениями для пользователя» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p></p>
<p>Для Exchange 2013 см. раздел «Единая система обмена сообщениями» по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>

