﻿---
title: Настройка DNS-записей для развертывания пилотного пула
TOCTitle: Настройка DNS-записей для развертывания пилотного пула
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49888245
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка DNS-записей для развертывания пилотного пула

 

_**Дата изменения раздела:** 2012-09-29_

Перед развертыванием пилотного пула Lync Server 2013 следует обновить записи A узла DNS для этого пула. Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.

**Настройка записей A узла DNS**

1.  На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.

2.  В дереве консоли для своего домена разверните узел **Зоны прямого просмотра** и щелкните правой кнопкой домен, в котором будет установлен Lync Server 2013.

3.  Выберите команду **Создать узел (A или AAAA)**.

4.  Щелкните поле **Имя** и введите имя узла Lync Server 2013 (имя домена принимается соответствующим зоне, в которой определяется запись, и его не нужно вводить как часть записи A).

5.  Щелкните **IP-адрес** и введите IP-адрес для переднего плана.

6.  Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.

7.  По завершении нажмите кнопку **Готово**.
