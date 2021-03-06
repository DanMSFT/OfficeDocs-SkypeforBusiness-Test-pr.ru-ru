﻿---
title: 'Lync Server 2013: поддержка аппаратных устройств'
TOCTitle: Поддержка аппаратных устройств
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412908(v=OCS.15)
ms:contentKeyID: 49310964
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддержка аппаратных устройств в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Перед развертыванием IP-телефонов и аналоговых устройств необходимо рассмотреть особые конфигурации оборудования.

IP-телефоны Lync Phone Edition поддерживают протоколы LLDP-MED и PoE. Чтобы воспользоваться преимуществами протокола LLDP-MED, коммутатор должен поддерживать IEEE802.1AB и ANSI/TIA-1057. Чтобы воспользоваться преимуществами протокола PoE, коммутатор должен поддерживать PoE802.3AF или 802.3at.

Для включения LLDP-MED администратор должен включить LLDP с помощью консоли коммутатора и задать политику сети LLDP-MED с правильным ИД виртуальной локальной сети для голосовых служб.

Если в развертывании используются аналоговые устройства, вам потребуется настроить аналоговый шлюз для использования Lync Server. В качестве шлюза можно использовать одно из следующих устройств:

  - Аналоговый телефонный адаптер (ATA)

  - Аналоговый шлюз ТСОП

  - Устройство для обеспечения связи в филиалах, которое содержит аналоговый шлюз ТСОП

  - Устройство для обеспечения связи в филиалах, которое содержит шлюз ТСОП, взаимодействующий с аналоговым телефонным адаптером

Дополнительные сведения о настройке аналогового шлюза см. в статье библиотеки TechNet по Lync Server 2010 «Планирование развертывания аналоговых устройств» по адресу [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537). (В Lync Server 2013 аналоговые устройства работают точно так же, как в Lync Server 2010.)

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Вы можете настроить коммутатор для службы Enhanced 9-1-1 (E9-1-1), если он поддерживает эту службу.</td>
</tr>
</tbody>
</table>

