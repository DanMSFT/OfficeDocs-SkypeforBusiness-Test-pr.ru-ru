﻿---
title: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013'
TOCTitle: Системные требования для серверов, на которых работает Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398588(v=OCS.15)
ms:contentKeyID: 49310231
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Системные требования для серверов, на которых работает Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Подробнее о требованиях к оборудованию см. в статье <a href="lync-server-2013-server-hardware-platforms.md">Аппаратные серверные платформы для Lync Server 2013</a> (Аппаратные серверные платформы).</td>
</tr>
</tbody>
</table>


К серверам Standard Edition и Enterprise Edition применяются одинаковые требования к программному обеспечению.

Серверы с Lync Server 2013 Enterprise Edition предназначены для использования в качестве основной системы в крупных организациях. Сервер Enterprise Edition предназначен для масштабирования до приблизительно 80 000 пользователей на пул. Серверы с выпуском Lync Server 2013 Standard Edition предназначены для небольших организаций и удаленных филиалов крупных организаций. Одна пара серверов Standard Edition может обеспечить поддержку 5000 пользователей. Подробнее об отличиях серверов Standard Edition и Enterprise Edition см. в статье [Обзор развертывания для Lync Server 2013](lync-server-2013-deployment-overview.md) (Общие сведения о развертывании).

## Установка операционной системы

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для Lync Server 2013 доступна только 64-разрядная версия, для которой требуется 64-разрядное оборудование и 64-разрядная версия операционной системы Windows Server. 32-разрядный выпуск Lync Server 2013 недоступен.</td>
</tr>
</tbody>
</table>


Серверы Standard Edition и Enterprise Edition могут использовать любой из следующих операционных систем:

  - Windows Server 2008 R2 SP1 или последний пакет обновления.

  - Windows Server 2012

  - Windows Server 2012 R2

Установите операционную систему на сервер Standard Edition или сервер переднего плана Enterprise Edition. Установите все обновления, чтобы обновить операционную систему до последней версии в соответствии со стандартами организации. Дополнительные сведения о требованиях см. в разделе [Поддержка сервера и средств в операционной системе в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) документации по поддержке.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для работы Lync Server 2013 на Windows Server 2012 R2 может потребоваться изменение значения ключа реестра в Windows Server. Это изменение также может быть необходимым для правильной работы сертификатов и регистрации клиентов в для обеспечения связи в филиалах. Дополнительные сведения см. в статье <a href="http://support.microsoft.com/kb/2901554" class="uri">http://support.microsoft.com/kb/2901554</a>.</td>
</tr>
</tbody>
</table>


## Дополнительное программное обеспечение для Lync Server 2013

Помимо обновлений операционной системы для работы Lync Server 2013 требуются роли и компоненты операционной системы, а также программное обеспечение. Дополнительные сведения о дополнительном ПО, которое нужно установить перед публикацией топологии и установкой Lync Server 2013 см. в разделе [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md) документации по планированию.

## Дополнительное программное обеспечение, необходимое для всех ролей сервера

На всех серверных роля также необходимо установить командной строки Windows PowerShell 3.0 и Microsoft .NET Framework 4.5.

Кроме того, требуется установить командной строки Windows PowerShell 3.0 и Microsoft .NET Framework 4.5 на каждом компьютере, на котором будут выполняться средства администрирования Lync Server.

## Windows PowerShell 3.0

Для Lync Server 2013 необходимо установить Windows PowerShell 3.0 на каждом компьютере, который будет участвовать в топологии Lync Server. Дополнительные сведения об установке Windows PowerShell 3.0 см. в разделе [Установка Windows PowerShell 3.0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>На Windows Server 2008 R2 с пакетом обновлений 1 (SP1) нельзя установить командной строки Windows PowerShell 3.0 перед установкой Microsoft .NET Framework 4.5.</td>
</tr>
</tbody>
</table>


## Платформа Microsoft .NET Framework 4.5.

Когда программное обеспечение Microsoft .NET Framework 4.5 устанавливают на серверах, на которых выполняется Lync Server 2013 на сервере Windows Server 2012 или Windows Server 2012 R2, необходимо выполнить один дополнительный шаг. После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.

**Установка службы HTTP-активации .NET 4.5 в ОС Windows Server 2012 или Windows Server 2012 R2**

1.  В меню **Пуск** последовательно выберите пункты **Программы** , **Администрирование** , **Диспетчер сервера**.

2.  В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.

3.  Разверните узел **.NET Framework 4.5**.

4.  Выберите пункт **WCF-активация** , если он еще не выбран. Затем выберите **HTTP-активация**.

5.  Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.

