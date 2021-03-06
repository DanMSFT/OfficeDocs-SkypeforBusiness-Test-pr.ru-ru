﻿---
title: 'Lync Server 2013: настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата'
TOCTitle: Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204653(v=OCS.15)
ms:contentKeyID: 49308860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка доставки журналов SQL Server в Lync Server 2013 для основной базы данных сервера сохраняемого чата

 

_**Дата изменения раздела:** 2012-11-12_

С помощью SQL Server Management Studio подключитесь к экземпляру основной базы данных доставки журналов сохраняемого сеанса беседы и убедитесь, что запущен агент SQL Server.

Подключив SQL Server Management Studio к экземпляру основной базы данных сохраняемый сеанс беседы, выполните следующие действия.

1.  Убедитесь, что запущен агент SQL Server.

2.  Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства** .

3.  В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций** .

4.  Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов** .

5.  В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования** .

6.  В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервных копий журналов транзакций.

7.  Если папка резервного копирования располагается на основном сервере, введите локальный путь к папке резервного копирования в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке (пример: c:\\backup)** . (Если папка резервного копирования находится не на основном сервере, это поле можно оставить пустым.)
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если учетная запись службы SQL Server на основном сервере выполняется с использованием учетной записи локальной системы, вам следует создать резервную папку на основном сервере и указать локальный путь к ней.</td>
    </tr>
    </tbody>
    </table>


8.  Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение** .

9.  Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования** . Чтобы настроить расписание для установки, щелкните элемент **Расписание** и измените расписание агента SQL Server необходимым образом.

10. В разделе **Сжатие** выберите пункт **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК** .

11. В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить** .

12. Нажмите кнопку **Подключить** и подключитесь к экземпляру SQL Server, который вы настроили в качестве дополнительного сервера.

13. В поле **База данных-получатель** выберите в списке базу данных **mgc** .

14. На вкладке **Инициализация базы данных-получателя** выберите пункт **Да, создать полную резервную копию базы данных-источника и выполнить восстановление из нее в базу данных-получатель (создать базу данных-получатель, если она не существует)**.

15. На вкладке **Копирование файлов** в поле **Папка назначения для копирования файлов** введите путь к папке, в которую необходимо копировать резервные копии журналов транзакций. Эта папка часто находится на дополнительном сервере.

16. Обратите внимание на расписание копирования, приведенное в поле **Расписание** в разделе **Задание копирования** . Чтобы настроить расписание для установки, щелкните элемент **Расписание** и измените расписание агента SQL Server необходимым образом. Это расписание должно приблизительно совпадать с расписанием резервного копирования.

17. На вкладке **Восстановление** в разделе **Папка назначения для копирования файлов** выберите пункт **Режим без восстановления** .

18. В списке **Отложить восстановление резервных копий по крайней мере на** выберите значение **0 минут** .

19. В поле **Предупреждение, если восстановление не выполнено в течение** выберите порог оповещений.

20. Просмотрите расписание восстановления в поле **Расписание** в разделе **Задание восстановления** . Чтобы настроить расписание для установки, щелкните элемент **Расписание** , измените расписание агента SQL Server необходимым образом и нажмите кнопку **ОК** . Это расписание должно приблизительно совпадать с расписанием резервного копирования.

21. В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК** , чтобы приступить к настройке.

