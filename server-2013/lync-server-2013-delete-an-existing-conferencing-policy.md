﻿---
title: Удаление существующей политики конференц-связи
TOCTitle: Удаление существующей политики конференц-связи
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49888036
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление существующей политики конференц-связи

 

_**Дата изменения раздела:** 2013-02-23_

Выполните приведенные действия, чтобы удалить политику конференц-связи уровня пользователя или уровня узла.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Вы не можете удалить глобальную политику конференц-связи.</td>
</tr>
</tbody>
</table>


## Удаление политики конференц-связи для узла или пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конференция**, а затем выберите **Политика конференц-связи**.

4.  В списке политик конференций выберите политику узла или пользователя, которую нужно удалить, нажмите кнопку "Изменить", а затем "Удалить".

## Удаление политик конференц-связи с помощью командлетов Командная консоль Lync Server

Вы также можете удалить параметры конфигурации магистрали с помощью Командная консоль Lync Server и командлета **Remove-CsConferencingPolicy**. Его можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Удаление указанной политики конференц-связи

  - Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## Удаление всех политик конференц-связи, применяемых на уровне пользователя

  - Следующая команда удаляет все политики конференц-связи, настроенные на уровне пользователя:
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## Удаление всех политик конференц-связи, разрешающих запись внешними пользователями

  - Следующая команда удаляет все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

Дополнительные сведения см. в разделе [Remove-CsConferencingPolicy](remove-csconferencingpolicy.md).

