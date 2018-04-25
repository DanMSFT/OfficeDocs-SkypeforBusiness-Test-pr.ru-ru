﻿---
title: Настройка доверенных серверов приложений
TOCTitle: Настройка доверенных серверов приложений
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204735(v=OCS.15)
ms:contentKeyID: 49309169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка доверенных серверов приложений

 

_**Дата изменения раздела:** 2014-11-05_

В неоднородной среде при создании нового сервера доверенных приложений необходимо задать пул следующих прыжков Lync Server 2013. В неоднородной среде в раскрывающемся списке будут отображаться и предыдущая версия пула Lync Server 2010, и пул Lync Server 2013. Предыдущую версию пула выбрать нельзя.

**При создании сервера доверенных приложений выберите Lync Server 2013 в качестве следующего прыжка.**

1.  Откройте построитель топологий.

2.  В левой панели щелкните правой кнопкой мыши **Серверы доверенных приложений** , затем щелкните **Создать пул надежных приложений** .

3.  Введите **Полное доменное имя пула** для пула доверенных приложений и укажите, будет ли это пул с одним или несколькими серверами.

4.  Нажмите кнопку **Далее** .

5.  На странице **Выбор следующего перехода** выберите в списке интерфейсный пул Lync Server 2013.

6.  Нажмите кнопку **Готово** .

7.  Выберите верхний узел **Lync Server** в меню **Действие** выберите действие **Опубликовать** .
    
    Убедитесь в том, что **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.
