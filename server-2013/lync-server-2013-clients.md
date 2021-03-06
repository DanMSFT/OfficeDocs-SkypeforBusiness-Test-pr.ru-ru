﻿---
title: 'Lync Server 2013: клиенты'
TOCTitle: Клиенты для Lync Server
ms:assetid: e143ce9b-3624-4066-942d-6c86ad99be91
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398996(v=OCS.15)
ms:contentKeyID: 49311439
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Клиенты для Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Lync Server 2013 поддерживает несколько типов клиентского программного обеспечения, которое можно развернуть для пользователей вашей организации, в том числе клиентское программное обеспечение, установленное на компьютеры, веб-клиенты и мобильные устройства. В этом разделе описываются клиенты, которые можно использовать. Подробное сравнение возможностей клиентов Lync Server 2013 см. в разделе [Таблица сравнения клиентов в Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

## Lync 2013

Lync 2013 – это полнофункциональный клиент для Lync Server. Пользовательский интерфейс Lync 2013 был полностью переделан и теперь содержит новые функции, такие как сохраняемый сеанс беседы (в Lync 2010 был отдельный клиент для такой функции), беседы со вкладками, предварительный просмотр видео и видео с несколькими участниками. Сводную информацию об изменениях см. в статье [Новые возможности для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Программа установки Lync 2013 является частью программы установки Office на установочном носителе.

## надстройка собраний по сети для Lync 2013

надстройка собраний по сети для Lync 2013 поддерживает управление собраниями из клиента Microsoft Outlook для обмена сообщениями и совместной работы. Программное обеспечение надстройка собраний по сети для Lync 2013 устанавливается автоматически с Lync 2013.

## Веб-планировщик Lync

Веб-планировщик Lync – это веб-инструмент для планирования собраний и управления ими для пользователей, не имеющих доступа к Microsoft Outlook либо применяющих операционную систему, которая не основана на Windows. С помощью веб-планировщика Lync пользователи могут создавать новые собрания, менять существующие собрания и отправлять приглашения в предпочитаемой программе для электронной почты.

## Lync Web App

Lync Web App – это веб-клиент для проведения конференций для Lync Server 2013. В этом выпуске добавление аудио и видео в Lync Web App предоставляет полноценные функции, доступные во время собрания, всем пользователям, у которых клиент Lync не установлен локально. У участников собрания есть доступ ко всем функциям совместной работы и общего доступа, а также элементам управления собранием докладчика.

Если Lync 2013 не установлен на компьютере пользователя, а пользователь щелкает ссылку собрания в запросе на собрание, открывается веб-приложение Lync Web App. Вы также можете настроить страницу присоединения к собранию, чтобы позволить пользователям присоединяться к собраниям с помощью предыдущих версий клиентов. См. [Конфигурация страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) в документации по развертыванию.

Из-за улучшений Lync Web App обновленная версия Участник Microsoft Lync 2010 недоступна для Lync Server 2013. Lync Web App – это клиент для участников за пределами вашей организации. При использовании Lync Web App не требуется устанавливать клиент локально, хотя для возможностей голосовой и видеосвязи, а также функций общего доступа требуется установка подключаемого модуля во время первого использования.

## Lync 2013 Основное

Lync 2013 Basic – это доступный для загрузки клиент для пользователей с лицензированным локальным развертыванием Lync Server 2013 и пользователями, подписанными на план Microsoft Office 365, который не включает в себя полный клиент Lync 2013. Клиент Lync Basic предоставляет улучшенные функции для сведений о присутствии, контактах, мгновенных сообщений, собраний Lync и базовой голосовой связи. В Lync Basic не поддерживается видеосвязь с несколькими участниками, интеграция с OneNote, поддержка инфраструктуры виртуальных рабочих столов (VDI), поиск по навыкам, запись, корпоративная голосовая связь и расширенная обработка звонков (например, переадресация звонков и групповой звонок). Дополнительные сведения см. в разделе [Таблица сравнения клиентов в Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

## Приложение Lync Магазина Windows

Магазина Lync Windows – это приложение Lync, оптимизированное для сенсорных экранов, которое разработано специально для Windows 8.1, Windows 8 и Windows RT. Пользователи могут загрузить это приложение через Магазин Windows, выполнив поиск по слову Lync. Дополнительные сведения см. в разделах [Таблица сравнения клиентов в Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md), [Требования приложения Lync из Магазина Windows](lync-server-2013-lync-windows-store-app-requirements.md) и [Развертывание приложения Lync из Магазина Windows](lync-server-2013-deploying-lync-windows-store-app.md).

## Lync 2013 для мобильных устройств

Мобильные приложения Lync 2013 теперь содержат возможности голосовой связи VoIP и видеосвязи через IP-подключения, а также функции контактов, сведений о присутствии и обмена мгновенными сообщениями. Мобильные пользователи могут выбрать способы связи с другими людьми – обмен мгновенными сообщениями, голосовые звонки или видеозвонки, – используя Wi-Fi или сотовое соединение для передачи данных. Одним щелчком по ссылке собрания в элементе календаря мобильные пользователи могут присоединиться к голосовым и видеособраниям. Дополнительные сведения о мобильных приложениях Lync 2013 см. в разделе [Планирование для мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

## Поддерживаемые клиенты из предыдущих выпусков

Lync Server 2013 поддерживает следующие клиенты из предыдущих выпусков. Некоторые предыдущие версии клиентов можно сделать свободными для пользователей при присоединении к собраниям. Дополнительные сведения см. в разделе [Конфигурация страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) в документации по развертыванию.

  - **Lync 2010**    Lync 2010 предоставляет полный интерфейс для настольных компьютеров, включая обмен мгновенными сообщениями, расширенные сведения о присутствии, голосовую связь, видеосвязь, общий доступ и телефонию. Однако новые функции, представленные в Lync Server 2013, не будут доступны до тех пор, пока клиент пользователя не будет обновлен до Lync 2013.

  - **Lync 2010 Mobile**    Lync Server 2013 поддерживает все мобильные приложения Microsoft Lync 2010 Mobile. Microsoft Lync 2010 Mobile предоставляет функции обмена мгновенными сообщениями, улучшенные сведения о присутствии, а также возможности телефонной связи для пользователей, которые подключаются со смартфона или телефона под управлением Windows Mobile Professional. Вы можете сообщить пользователям о необходимости установки Microsoft Lync 2010 Mobile, направив их в магазин приложений для их мобильного телефона. Дополнительные сведения см. в разделе "Планирование для мобильных клиентов" в документации Lync Server 2010 по адресу <http://go.microsoft.com/fwlink/?linkid=235955>.

  - **Lync Phone Edition**   Программное обеспечение Lync Phone Edition для интеллектуальных IP-телефонов (например, USB-телефонов) не обновлялось для Lync Server 2013. Поддержка Lync Phone Edition продолжается для осуществления и приема звонков, улучшенных сведений о присутствии, а также клиентских возможностей голосовой связи для конференций.

  - **оператор Lync 2010**   Интегрированная программа управления звонками Оператор Microsoft Lync 2010 позволяет секретарю управлять несколькими беседами одновременно с помощью быстрой обработки звонков, обмена мгновенными сообщениями и маршрутизации на экране.

## См. также

#### Концепции

[Взаимодействие клиентов в Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md)

