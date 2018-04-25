﻿---
title: 'Lync Server 2013: требования к видео-клиенту Lync'
TOCTitle: Требования к видео-клиенту Lync
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49888085
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования к видео-клиенту Lync для Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

В этом разделе описывается поддержка видеоустройств для видеовызовов Lync 2013, а также приводится способ определения ожидаемого качества видео для различных конфигураций компьютера, планшета и мобильных устройств.

## Требования и возможности рабочего стола Windows и видео для планшетов

В Lync 2013 появилась поддержка аппаратного ускорения кодирования и декодирования видео на основе стандарта H.264/MPEG-4 Part 10 Advanced Video Coding. Эта возможность позволяет компьютерам с более низкой скоростью ЦП кодировать и декодировать видео с более высоким разрешением. Требования к видеоустройствам зависят от конфигурации компьютера и необходимого разрешения видео.

## Требования к видеоустройствам


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Функция</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аппаратное ускорение декодирования H.264 с помощью DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>Графическая карта должна поддерживать DirectX 9.0 и работать в режиме декодирования DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Должен быть установлен последний драйвер графической карты.</p></li>
</ul>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения о режимах декодирования см. на сайте <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Аппаратное ускорение кодирования H.264: требования к набору микросхем</p></td>
<td><p>Поддерживаются перечисленные ниже решения Intel для кодирования видео с аппаратным ускорением.</p>
<ul>
<li><p>Наборы микросхем второго и третьего поколения Intel HD Graphics 2000, 2500, 3000 и 4000 (или более поздние версии) со встроенными аппаратными видеокодировщиками. Требуется установка драйвера Intel HD Graphics 15.28.9.2884 или более поздней версии с перечисленными ниже компонентами</p>
<ul>
<li><p>Драйвер дисплея 9.17.10.2884 или более поздней версии</p></li>
<li><p>Платформа HMFT 3.12.10.31 или последней версии</p></li>
</ul></li>
</ul>
<p>Поддерживаются перечисленные ниже решения AMD для кодирования видео с аппаратным ускорением (требуется установка накопительного пакета обновлений 1 для сервера Lync Server 2013).</p>
<ul>
<li><p>Модуль видеокодеков AMD Video Codec Engine, имеющийся в некоторых адаптерах дискретной графики, а также во встроенных блоках ускоренной обработки серии AMD A-Series Accelerated Processors. Должен быть установлен драйвер AMD Video Codec Engine 9.12.0.0 или более поздней версии.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Аппаратное ускорение кодирования H.264: требования к камере</p></td>
<td><p>Видеокамеры USB со встроенным аппаратным кодировщиком H.264, поддерживающие спецификацию USB Video Class (UVC) версии 1.5.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync 2013 поддерживает камеры UVC 1.5 с ОС Windows 8 или Windows 8.1, в которую включена поддержка UVC 1.5. Поскольку в Windows 7 не включена поддержка UVC 1.5, Lync 2013 работает с камерами UVC 1.5 как с обычными камерами без поддержки аппаратного кодирования.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Аппаратное ускорение декодирования H.264 с помощью DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>Графическая карта должна поддерживать DirectX 9.0 и работать в режиме декодирования DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Должен быть установлен последний драйвер графической карты.</p></li>
</ul>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения о режимах декодирования см. на сайте <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Аппаратное ускорение кодирования H.264: требования к набору микросхем</p></td>
<td><p>Поддерживаются перечисленные ниже решения Intel для кодирования видео с аппаратным ускорением.</p>
<ul>
<li><p>Наборы микросхем второго и третьего поколения Intel HD Graphics 2000, 2500, 3000 и 4000 (или более поздние версии) со встроенными аппаратными видеокодировщиками. Требуется установка драйвера Intel HD Graphics 15.28.9.2884 или более поздней версии с перечисленными ниже компонентами</p>
<ul>
<li><p>Драйвер дисплея 9.17.10.2884 или более поздней версии</p></li>
<li><p>Платформа HMFT 3.12.10.31 или последней версии</p></li>
</ul></li>
</ul>
<p>Поддерживаются перечисленные ниже решения AMD для кодирования видео с аппаратным ускорением (требуется установка накопительного пакета обновлений 1 для сервера Lync Server 2013).</p>
<ul>
<li><p>Модуль видеокодеков AMD Video Codec Engine, имеющийся в некоторых адаптерах дискретной графики, а также во встроенных блоках ускоренной обработки серии AMD A-Series Accelerated Processors. Должен быть установлен драйвер AMD Video Codec Engine 9.12.0.0 или более поздней версии.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Аппаратное ускорение кодирования H.264: требования к камере</p></td>
<td><p>Видеокамеры USB со встроенным аппаратным кодировщиком H.264, поддерживающие спецификацию USB Video Class (UVC) версии 1.5.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync 2013 поддерживает камеры UVC 1.5 с ОС Windows 8 или Windows 8.1, в которую включена поддержка UVC 1.5. Поскольку в Windows 7 не включена поддержка UVC 1.5, Lync 2013 работает с камерами UVC 1.5 как с обычными камерами без поддержки аппаратного кодирования.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
</tbody>
</table>


## Определение возможностей кодирования и декодирования видео H.264

В общем случае максимальная производительность кодирования и декодирования для конкретной конфигурации компьютера определяется четырьмя основными факторами:

  - поддержка аппаратного ускорения декодирования с помощью DXVA;

  - поддержка аппаратного ускорения кодирования;

  - количество физических ядер;

  - индекс производительности Windows (WEI).

Средство оценки производительности WinSAT определяет индекс WEI. Средство WinSAT создает XML-документ Formal.Assessment в каталоге %windir%\\Performance\\WinSAT\\DataStore. В этом XML-файле представлены два показателя, на основании которых можно определить возможности кодирования и декодирования:

  - значение VideoEncodeScore показывает производительность компьютера по программному кодированию видео;

  - значение GraphicsScore показывает производительность компьютера по кодированию видео с аппаратным ускорением.

В следующих таблицах приводится максимальная производительность кодирования и декодирования для нескольких типов ПК в зависимости от поддержки аппаратного ускорения. Для разрешения 640x360 и выше максимальная поддерживаемая частота кадров составляет 30 кадров в секунду (кадр/с). Для разрешений ниже 640x360 максимальная поддерживаемая частота кадров составляет 15 кадр/с.

### Компьютер без DXVA и без аппаратного ускорения кодирования

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 при 15 кадр/с только для приема)</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 4</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 при 15 кадр/с только для приема)</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 4</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Н/Д</p></td>
</tr>
</tbody>
</table>


### Компьютер с DXVA, но без аппаратного ускорения кодирования

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 3</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 6</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 8,2</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 3</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 6</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В Windows 7 максимальное значение показателя WinSAT составляет 7,9, поэтому такая производительность кодирования для компьютера без аппаратного ускорения может быть достигнута только в Windows 8 или Windows 8.1, где максимальное значение показателя WinSAT составляет 9,9.</td>
</tr>
</tbody>
</table>


### Компьютер с DXVA и с аппаратным ускорителем кодирования Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Все графические карты Intel HD Graphics второго и третьего поколения</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Графические карты Intel HD Graphics второго и третьего поколения и GraphicsScore ≥ 5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Все графические карты Intel HD Graphics второго и третьего поколения</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Графические карты Intel HD Graphics второго и третьего поколения и GraphicsScore ≥ 5</p></td>
</tr>
</tbody>
</table>


## Возможности видео для мобильных устройств

В следующей таблице описываются максимальные возможности видео для поддерживаемых мобильных устройств. Подробнее о поддерживаемых мобильных устройствах см. в статье [Планирование для мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Функция</th>
<th>Windows Phone</th>
<th>iPhone и iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Максимальное разрешение для кодирования H.264</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4: 192x144</p>
<p>iPad и все другие поддерживаемые модели iPhone: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>Максимальное разрешение для декодирования H.264</p></td>
<td><p>640x480</p></td>
<td><p>iPhone и iPad: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="odd">
<td><p>Максимальное разрешение для кодирования H.264</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4: 192x144</p>
<p>iPad и все другие поддерживаемые модели iPhone: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>Максимальное разрешение для декодирования H.264</p></td>
<td><p>640x480</p></td>
<td><p>iPhone и iPad: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
</tbody>
</table>


1Для устройств Android с процессором Qualcomm Snapdragon S3 или S4 и любым набором микросхем 8x60 в рамках процессов отправки и получения поддерживается разрешение 640x480.
