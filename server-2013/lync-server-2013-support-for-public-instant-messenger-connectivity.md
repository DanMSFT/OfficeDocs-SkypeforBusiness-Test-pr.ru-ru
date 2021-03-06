﻿---
title: Поддержка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013
TOCTitle: Поддержка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59373664
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддержка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

## Поддержка подключения к общедоступным службам обмена мгновенными сообщениями

В этой статье приводятся сведения о поддержке общедоступных служб обмена мгновенными сообщениями. Возможность подключения к общедоступным службам обмена мгновенными сообщениями — это функция Microsoft Lync, с помощью которой организации могут разрешить своим пользователям Lync связываться с пользователями определенных общедоступных служб обмена мгновенными сообщениями с использованием клиентов и удостоверений Lync.

Преимущество для конечных пользователей заключается в том, что они могут связываться с клиентами, партнерами и поставщиками удобными для них способами. Преимущество для ИТ-отдела заключается в поддержке единого клиента для связи в режиме реального времени с сохранением всех возможностей контроля, обеспечения соответствия требованиям и архивации, предоставляемых приложением Lync. Возможность связи между пользователями Lync и Skype, [которая стала доступна в мае 2013 г.](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), основывается на тех же механизмах, которые изначально использовались в Lync, Office Communications Server и Live Communications Server для подключения к MSN, Windows Live, AOL и Yahoo. Дополнительные сведения о возможности связи между пользователями Lync и Skype см. на странице [Подключение Lync к Skype](http://office.microsoft.com/ru-ru/lync/lync-skype-connectivity-fx103789635.aspx). Поддержка федерации с Windows Live, AOL и Yahoo близится к завершению. На этой странице приводятся сведения о состоянии каждой службы.

Для подключения к общедоступным службам обмена мгновенными сообщениями клиентам необходимо активировать соответствующую службу для каждого поставщика. Необходимые для этого действия зависят от поставщика службы обмена мгновенными сообщениями и программы лицензирования клиента.

## Windows Live Messenger

Корпорация Майкрософт объединила Windows Live Messenger и Skype. В апреле 2013 г. был произведен переход пользователей на Skype, который осуществлялся при входе в систему. Клиенты Lync, использующие федерацию с Messenger, по-прежнему могут связываться с контактами Messenger даже после их миграции в Skype. Администраторам и конечным пользователям Lync не нужно предпринимать никаких действий для обеспечения непрерывности обслуживания. Управление этой возможностью в Lync осуществляется так же, как это делалось при использовании Messenger.

Когда пользователи Messenger входят в Skype с помощью своих учетных записей Майкрософт (то есть тех же учетных записей, которые они используют для входа в Messenger), все их контакты Messenger, включая федеративные контакты Lync, доступны в Skype. Для этих контактов поддерживается обмен сведениями о присутствии и мгновенными сообщениями между Skype и Lync.

Возможность связи между Lync и Skype (включая добавление контактов, обмен сведениями о присутствии и мгновенными сообщениями, а также голосовые звонки между пользователями Lync и Skype) теперь также доступна всем клиентам Lync.

## Yahoo\! и AOL Instant Messenger

Поддержка федерации с Yahoo\! и AOL для клиентов Lync (и Office Communications Server) близится к завершению. Возможность предоставления этих услуг корпорацией Майкрософт зависела от поддержки компаний Yahoo\! и AOL, срок действия базовых соглашений с которыми подходит к концу. Федерация с Yahoo\! и AOL будет доступна до июня 2014 года включительно.

  - **Yahoo** — обслуживание продлится до июня 2014 года включительно. Клиентам будет по-прежнему нужна лицензия подписки пользователя на возможность подключения к общедоступным службам обмена мгновенными сообщениями Microsoft Lync (PIC USL). С 1 сентября 2012 г. лицензия PIC USL недоступна для приобретения в рамках новых или продляемых соглашений. Клиенты, которые приобрели лицензии до этой даты, смогут пользоваться федерацией с Yahoo\! до прекращения ее поддержки или истечения срока действия лицензии в зависимости от того, какое из этих событий наступит раньше. Прочитать [объявление](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) можно в блоге группы разработчиков Lync. Клиенты с лицензиями PIC, действующими после 30 июня 2014 г, получат кредит, размер которого будет рассчитан пропорционально оставшемуся периоду действия лицензии после 30 июня 2014 г.

  - **AOL** — 30 июня 2014 г. возможность подключения Lync к этой службе обмена мгновенными сообщениями станет недоступна. Чтобы свести к минимуму перерывы в обслуживании, мы прекратили предоставление дополнительных доменов клиентов. До 30 июня 2014 г. клиентам не требуется предпринимать никаких действий для обеспечения федерации с AIM. После этой даты (а также в случае, если до ее наступления клиентам потребуются дополнительные домены) будет доступна альтернативная служба, предоставляемая непосредственно компанией AOL. Дополнительные сведения о новой службе AOL см. в статье [Установление прямой федерации с AIM](http://aimenterprise.aol.com/pic.php) (откроется новая страница на сайте AOL.com).

## Сводная информация о поставщиках общедоступных служб обмена мгновенными сообщениями

В следующей таблице приводится сводная информация о поставщиках общедоступных служб обмена мгновенными сообщениями, возможностях их федерации с Lync и требованиях к лицензированию.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поставщик общедоступной службы обмена мгновенными сообщениями</th>
<th>Возможности федерации</th>
<th>Требования к лицензированию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Мгновенные сообщения, сведения о присутствии, голосовая связь</p></td>
<td><p>Клиентские лицензии Lync Server, Lync Online (план 1, 2, 3)</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Мгновенные сообщения, сведения о присутствии, голосовая и видеосвязь</p></td>
<td><p>Клиентские лицензии Lync Server (служба будет доступна, пока не будет завершена поддержка Windows Live Messenger)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Мгновенные сообщения, сведения о присутствии</p></td>
<td><p>Клиентские лицензии Lync Server; поддерживается для существующих клиентов до июня 2014 г. включительно</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Мгновенные сообщения, сведения о присутствии</p></td>
<td><p>Требуется дополнительная лицензия лицензия подписки пользователя на возможность подключения к общедоступным службам обмена мгновенными сообщениями Microsoft Lync (PIC USL) в дополнение к клиентским лицензиям Lync Server. Лицензия PIC USL недоступна для приобретения с выхода прейскуранта за сентябрь 2012 г. Клиенты с активными лицензиями могут по-прежнему использовать федерацию с Yahoo! Messenger до отключения службы (30 июня 2014 г.).</p></td>
</tr>
</tbody>
</table>

