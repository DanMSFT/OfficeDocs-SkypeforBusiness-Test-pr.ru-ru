﻿---
title: Установка основных файлов Lync Server 2013 и базы данных RTCLocal
TOCTitle: Установка основных файлов Lync Server 2013 и базы данных RTCLocal
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204734(v=OCS.15)
ms:contentKeyID: 49309168
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка основных файлов Lync Server 2013 и базы данных RTCLocal

 

_**Дата изменения раздела:** 2012-10-20_

Чтобы установить файлы основных данных Lync Server 2013 на компьютер, выполните следующие действия. База данных RTCLocal устанавливается автоматически при установке файлов основных данных. Обратите внимание, что установка SQL Server на узлах-наблюдателях не требуется. Вместо этого установка SQL Server, экспресс-выпуск выполняется автоматически.

Установка файлов основных данных Lync Server 2013 и базы данных RTCLocal:

1.  На компьютере узла-наблюдателя в меню **Пуск** щелкните **Все программы**, выберите **Стандартные**, щелкните правой кнопкой мыши **Командная строка**, а затем выберите команду **Запуск от имени администратора**.

2.  В окне консоли введите следующую команду и нажмите клавишу ВВОД. Укажите соответствующий путь к файлам программы установки Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Чтобы проверить установку основных компонентов Lync Server, в меню **Пуск** щелкните **Все программы**, выберите **Lync Server 2013** и нажмите **Командная консоль Lync Server**. В командная консоль Lync Server 2013, введите следующую команду Windows PowerShell, после чего нажмите клавишу ВВОД:

    Get-CsWatcherNodeConfiguration

При первом выполнении этой команды данные не возвращаются, так как в качестве узла-наблюдателя не настроек ни один компьютер. Пока команда выполняется, не возвращая ошибок, можно считать, что установка Lync Server выполнена успешно.

Если узел-наблюдатель размещен в пределах сети периметра, можно выполнить следующую команду, чтобы проверить установку Lync Server 2013:

    Get-CsPinPolicy

Отобразятся данные в следующем виде в соответствии с количеством политик ПИН-кодов, настроенных для организации:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Если отображаются сведения о политиках ПИН-кодов, это означает, что основные компоненты были успешно установлены.

