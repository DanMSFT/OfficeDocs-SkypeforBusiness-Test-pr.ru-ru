﻿---
title: Создание или изменение коллекции параметров конфигурации Lync Phone Edition
TOCTitle: Создание или изменение коллекции параметров конфигурации Lync Phone Edition
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49888033
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение коллекции параметров конфигурации Lync Phone Edition

 

_**Дата изменения раздела:** 2013-02-23_

При установке Lync Server вы получаете глобальную коллекцию параметров Lync Phone Edition. Они применяются ко всем устройствам под управлением Lync Phone Edition в вашем развертывании. Вы можете изменить эти настройки в любое время. Вы также можете настроить новую коллекцию параметров, которая применяется к устройствам в определенном узле. Параметры узла имеют более высокий приоритет, чем глобальные параметры.

Параметры конфигурации состоят из имени коллекции, области (глобальная или узел), параметра безопасности SIP, уровня ведения журнала, уровня качества обслуживания (QoS) голосовой связи, параметра блокировки телефона и сведений о блокировке, т. е. а) каким по длине должен быть ПИН-код для разблокировки и б) как долго телефон может быть неактивным до автоматической блокировки.

## Создание коллекции параметров конфигурации Lync Phone Edition или изменение параметров существующей коллекции

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Конфигурация устройства**.

4.  На странице **Конфигурация устройства** выполните одно из следующих действий.
    
      - Чтобы создать новую коллекцию параметров конфигурации Lync Phone Edition, нажмите кнопку **Создать**, выберите узел, нажмите кнопку **ОК**, изучите параметры по умолчанию и, при необходимости, внесите изменения.
    
      - Чтобы изменить параметры существующей коллекции, щелкните ее, откройте меню **Правка**, щелкните **Показать подробности** и внесите изменения.
        

        > [!TIP]
        > Чтобы вернуться к параметрам глобальной коллекции по умолчанию, откройте меню <STRONG>Правка</STRONG>, щелкните <STRONG>Удалить</STRONG> и нажмите кнопку <STRONG>ОК</STRONG>. При этом глобальная коллекция не удаляется, просто восстанавливаются настройки по умолчанию.



5.  Нажмите кнопку **Сохранить**.

## Создание новых параметров конфигурации Lync Phone Edition с помощью командлетов Командная консоль Lync Server

Параметры конфигурации Lync Phone Edition также можно создать (только в области узла) с помощью командлетов Командная консоль Lync Server и **New-CsUCPhoneConfiguration**. Их можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Создание новых параметров конфигурации Lync Phone Edition, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации телефона UC для сайта Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Так как в предыдущей команде не были указаны параметры (кроме обязательного параметра Identity), новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех свойств.

## Изменение значения одного свойства при создании параметров конфигурации Lync Phone Edition

  - Чтобы создать параметры, использующие разные значения свойств, просто укажите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации телефона UC, которые требуют блокировки телефона по умолчанию, используйте следующую команду:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## Изменение значений нескольких свойств при создании параметров конфигурации Lync Phone Edition

  - Значения нескольких свойств можно изменить, указав несколько параметров. Например, следующая команда применяет блокировку телефона и также задает минимальную длину ПИН-кода (8 разрядов):
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

Дополнительные сведения см. в разделе [New-CsUCPhoneConfiguration](new-csucphoneconfiguration.md).

## См. также

#### Задачи

[Удаление существующей коллекции параметров конфигурации Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Настройка параметров безопасности для Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Принудительная блокировка телефона](lync-server-2013-enforce-phone-locking.md)

