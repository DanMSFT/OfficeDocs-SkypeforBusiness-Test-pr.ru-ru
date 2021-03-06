﻿---
title: Отчет по сравнению качества среды
TOCTitle: Отчет по сравнению качества среды
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205236(v=OCS.15)
ms:contentKeyID: 49311063
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отчет по сравнению качества среды

 

_**Дата изменения раздела:** 2015-03-09_

Сравнительный отчет качества мультимедиа-данных позволяет сравнить значения качества звонков для различных типов аудиозвонков (например, звонков, выполненных через беспроводные сети и звонков, выполненных через проводное соединение).

## Доступ к сравнительному отчету качества мультимедиа-данных

Сравнительный отчет качества мультимедиа-данных доступен на домашней странице отчетов мониторинга.

## Фильтры

Фильтры предоставляют способ получения более точно настроенного набора данных или просмотра возвращенных данных различными способами. В следующей таблице перечислены фильтры, которые можно использовать в сравнительном отчете качества мультимедиа-данных.

### Фильтры сравнительного отчета качества мультимедиа-данных

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>От</strong></p></td>
<td><p>Дата и время начала для диапазона времени. Чтобы просмотреть данные по часам, введите дату и время начала следующим образом:</p>
<p>07.07.2012 13:00</p>
<p>Если не ввести время начала, отчет автоматически начинается в 00:00 указанного дня. Чтобы просмотреть данные по дням, введите только дату:</p>
<p>07.07.2012</p>
<p>Чтобы просмотреть данные по неделе или по месяцу, введите дату, которая попадает в любое место недели или месяца, которые требуется просмотреть (не требуется вводить первый день недели или месяца):</p>
<p>03.07.2012</p>
<p>Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</p></td>
</tr>
<tr class="even">
<td><p><strong>До</strong></p></td>
<td><p>Дата и время окончания для диапазона времени. Чтобы просмотреть данные по часам, введите дату и время окончания следующим образом:</p>
<p>07.07.2012 13:00</p>
<p>Если не ввести время окончания, отчет автоматически оканчивается в 00:00 указанного дня. Чтобы просмотреть данные по дням, введите только дату:</p>
<p>07.07.2012</p>
<p>Чтобы просмотреть данные по неделе или по месяцу, введите дату, которая попадает в любое место недели или месяца, которые требуется просмотреть (не требуется вводить первый день недели или месяца):</p>
<p>03.07.12</p>
<p>Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Звонки</strong></p></td>
<td><p>Тип звонка, который будет использоваться в качестве основного элемента для сравнения. Допускаются следующие значения:</p>
<ul>
<li><p>[Все]</p></li>
<li><p>Внешние</p></li>
<li><p>Внутренние</p></li>
<li><p>VPN</p></li>
<li><p>Не VPN</p></li>
<li><p>Проводные</p></li>
<li><p>Беспроводные</p></li>
<li><p>Внешние и проводные</p></li>
<li><p>Внешние и беспроводные</p></li>
<li><p>Внешние и VPN</p></li>
<li><p>Внешние и не VPN</p></li>
<li><p>Внутренние и проводные</p></li>
<li><p>Внутренние и беспроводные</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Сравнить со звонками</strong></p></td>
<td><p>Тип звонка, который будет использоваться в качестве второго элемента для сравнения. Допускаются следующие значения:</p>
<ul>
<li><p>[Все]</p></li>
<li><p>Внешние</p></li>
<li><p>Внутренние</p></li>
<li><p>VPN</p></li>
<li><p>Не VPN</p></li>
<li><p>Проводные</p></li>
<li><p>Беспроводные</p></li>
<li><p>Внешние и проводные</p></li>
<li><p>Внешние и беспроводные</p></li>
<li><p>Внешние и VPN</p></li>
<li><p>Внешние и не VPN</p></li>
<li><p>Внутренние и проводные</p></li>
<li><p>Внутренние и беспроводные</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Интервал</strong></p></td>
<td><p>Временной интервал. Выберите одно из следующих значений:</p>
<ul>
<li><p>Ежечасно (может отображаться максимум 25 часов)</p></li>
<li><p>Ежедневно (может отображаться максимум 31 день)</p></li>
<li><p>Еженедельно (может отображаться максимум 12 недель)</p></li>
</ul>
<p>Если даты начала и окончания превышают максимальное допустимое число для выбранного интервала, будет отображено только максимальное число значений (начиная с даты начала). Например, если выбрать интервал &quot;Ежедневно&quot; с датой начала 07.07.2012 и датой окончания 28.08.2012, дата отображается для дней с 07.08.2012 00:00 по 07.09.2012 00:00 (то есть в сумме будут отображены данные для 31 дня).</p></td>
</tr>
</tbody>
</table>


## Метрики

В следующей таблице приведены сведения, предоставляемые сравнительным отчетом качества мультимедиа-данных

### Метрики сравнительного отчета качества мультимедиа-данных

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Можно ли сортировать по этому элементу?</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Число звонков</strong></p></td>
<td><p>Нет</p></td>
<td><p>Полное число звонков.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ухудшение (MOS)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Среднее значение числа MOS (средней экспертной оценки разборчивости речи), показывающей ухудшение качества связи во время звонка. Значения ухудшения качества могут находиться в диапазоне от 0,0 до 5,0; значение 0,5 или ниже соответствует приемлемому ухудшению. Исторически средние экспертные оценки разборчивости речи вычислялись при помощи пользователей, которые оценивали качество звонка по шкале от 1 до 5. Сервер Lync Server использует набор алгоритмов для прогнозирования того, как пользователи могут оценить звонок.</p>
<p>Высокие значения ухудшения могут быть вызваны перегрузкой; недостаточной пропускной способностью; перегрузкой беспроводной сети или интерференцией; перегрузкой сервера мультимедиа или конечной точки. Сильное ухудшение приводит к повреждению или потере аудиосигнала.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Процент неудовлетворительных звонков</strong></p></td>
<td><p>Нет</p></td>
<td><p>Полное число звонков, классифицированных как неудовлетворительные. Неудовлетворительный звонок — это любой звонок, в котором хотя бы одна измеренная метрика превысила допустимое значение (например, звонок, подверженный слишком сильному дрожанию).</p></td>
</tr>
<tr class="even">
<td><p><strong>Время кругового пути (мс)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Среднее время (в миллисекундах), требуемое для переноса пакета протокола RTP на другую конечную точку и затем обратно. Время кругового пути в 200 миллисекунд или меньше считается приемлемым качеством.</p>
<p>Высокие значения времени кругового пути могут быть вызваны международной маршрутизацией звонков; неправильной настройкой кругового пути; или перегрузкой сервера мультимедиа. Высокие значения времени кругового пути приводят к сложностям в двухсторонних аудиобеседах в реальном времени.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Потеря пакетов</strong></p></td>
<td><p>Нет</p></td>
<td><p>Средняя скорость потери пакетов протокола RTP. (Потеря пакетов возникает, когда пакеты RTP, используемые протоколом для передачи звука и видео через Интернет, не достигают конечного компьютера.) Высокая скорость потери пакетов обычно вызвана переполнением; недостаточной пропускной способностью; перегрузкой беспроводной сети или интерференцией; или перегрузкой сервера мультимедиа. Потеря пакетов обычно приводит к повреждению или потере аудиосигнала.</p></td>
</tr>
<tr class="even">
<td><p><strong>Дрожание (мс)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Среднее значение дрожания, зарегистрированное между приходом пакетов RTP. (Дрожание — это показатель &quot;неустойчивости&quot; звонка.) Высокие значения дрожания обычно вызваны переполнением или перегрузкой сервера мультимедиа и приводят к повреждению или потере аудиосигнала.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Соотношение исключенных фрагментов</strong></p></td>
<td><p>Нет</p></td>
<td><p>Количество исключенных звуковых фрагментов по отношению к общему числу фрагментов. (Исключение звуковых фрагментов — это метод, используемый для сглаживания резких переходов, которые обычно вызываются потерей сетевых пакетов.) Высокие значения указывают на значительное количество исключений, примененных по причине потери пакетов или дрожания, что приводит к повреждению или потере аудиосигнала.</p></td>
</tr>
<tr class="even">
<td><p><strong>Соотношение растянутых фрагментов</strong></p></td>
<td><p>Нет</p></td>
<td><p>Количество растянутых звуковых фрагментов по отношению к общему числу фрагментов. (Растягивание звука — это прием для поддержания качества звука в случае обнаружения потери сетевого пакета.) Высокие значения указывают на значительные уровни растягивания фрагментов, вызванного дрожанием, что приводит к роботоподобному звучанию или искажениям.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Соотношение сжатых фрагментов</strong></p></td>
<td><p>Нет</p></td>
<td><p>Количество сжатых звуковых фрагментов по отношению к общему числу фрагментов. (Сжатие звука — это прием для поддержания качества звука в случае обнаружения потери сетевого пакета.) Высокие значения указывают на значительные уровни сжатия фрагментов, вызванного дрожанием, что приводит к ускоренному звучанию или искажениям.</p></td>
</tr>
</tbody>
</table>

