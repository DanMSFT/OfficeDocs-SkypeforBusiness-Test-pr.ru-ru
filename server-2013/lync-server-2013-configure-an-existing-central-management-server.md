﻿---
title: 'Lync Server 2013: настройка существующего центрального сервера управления'
TOCTitle: Настройка существующего центрального сервера управления
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205315(v=OCS.15)
ms:contentKeyID: 49311328
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка существующего центрального сервера управления в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-21_

При повторном использовании управления из существующего развертывания Lync Server 2013 выполните процедуру, описанную ниже, чтобы обеспечить корректную работу управления Lync Server и Windows PowerShell.

## Настройка существующего сервера управления

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Используйте командлет **Update-CsAdminRole**, чтобы обновить роли управления доступом на основе ролей (RBAC), сохраненные в управления.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>При отсутствии ошибок вывод результатов не ожидается.</td>
    </tr>
    </tbody>
    </table>
