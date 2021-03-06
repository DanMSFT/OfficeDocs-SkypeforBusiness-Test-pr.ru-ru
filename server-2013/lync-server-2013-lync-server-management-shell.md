﻿---
title: Командная консоль Lync Server
TOCTitle: Командная консоль Lync Server
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398474(v=OCS.15)
ms:contentKeyID: 49310037
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командная консоль Lync Server

 

_**Дата изменения раздела:** 2016-12-08_

В Microsoft Lync Server 2010 представлен большой набор новых и улучшенных функций по сравнению с функциями, доступными в Microsoft Office Communications Server 2007 R2. Одним из улучшений является способ управления реализацией. Например, существует пользовательский интерфейс управления Lync Server, который представляет значительное изменение по сравнению с тем, к чему привыкли большинство пользователей консоли управления (MMC). Другое значительное улучшение управления — включение Windows PowerShell.

Средство Windows PowerShell позволяет вам управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Впервые средство Windows PowerShell было представлено как доступный для загрузки выпуск для операционной системы Windows в конце 2006 г. и было встроено как интерфейс командной строки для управления Microsoft Exchange Server 2007. С тех пор это средство продолжало развиваться и встраиваться в большинство серверных продуктов Майкрософт, последним из которых стал Microsoft Lync Server 2013. В Lync Server 2010 было представлено почти 550 командлетов для различных продуктов, которые можно использовать для управления всеми аспектами вашего развертывания.

В следующих разделах представлен список командлетов и их описание. Эта информация также доступна напрямую из командной строки. Просто введите следующее в командной строке Командная консоль Lync Server:

    Get-Help <cmdlet name> -Full

Например, чтобы получить справку по командлету **New-CsVoicePolicy** из командной строки, введите следующую команду:

    Get-Help New-CsVoicePolicy -Full

Что нужно знать о Windows PowerShell в Lync Server 2013:

  - Для запуска комадлетов Lync Server откройте Командная консоль Lync Server.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если открыть окно Windows PowerShell вместо Командная консоль Lync Server, то по умолчанию вы не сможете выполнять командлеты Lync Server. Чтобы запускать командлеты Lync Server в Windows PowerShell, сначала введите следующее в командной строке Windows PowerShell:<br />
    Import-Module Lync</td>
    </tr>
    </tbody>
    </table>


  - Командная консоль Lync Server автоматически устанавливается на каждом интерфейсном сервере Lync Server Enterprise Edition или сервере Standard Edition.

  - Новые и обновленные сведения, примеры скриптов и справка по началу работу, а также дополнительные сведения о командлетах Windows PowerShell и Microsoft Lync Server 2013 доступны в блоге Windows PowerShell Lync Server по адресу [http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419).

