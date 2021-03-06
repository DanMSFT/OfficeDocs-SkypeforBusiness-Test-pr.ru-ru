﻿---
title: 'Lync Server 2013: проверка структуры топологии'
TOCTitle: Проверка структуры топологии
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412951(v=OCS.15)
ms:contentKeyID: 49311061
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка структуры топологии в Lync Server 2013

 

_**Дата изменения раздела:** 2012-01-02_

топологий автоматически проверяет топологию. Любая ошибка топологии считается ошибкой проверки и обозначается значком ошибки проверки рядом с ролью сервера. Важно также проверить, что топология правильно представляет топологию вашего развертывания.

## Проверка топологии до публикации

1.  Проверьте, что все простые URL-адреса настроены правильно.

2.  Проверьте, что сервер на основе SQL Server включен и доступен компьютеру, на котором установлено топологий, включая все необходимые правила брандмауэра.

3.  Проверьте, что файловое хранилище доступно и для него заданы необходимые разрешения.

4.  Проверьте, что в топологии заданы правильные роли сервера, удовлетворяющие требованиям развертывания.

5.  Проверьте, что в Доменные службы Active Directory имеются серверы. Это осуществляется автоматически, если серверы присоединены к домену.

Когда топология проверена и ошибки проверки отсутствуют, все должно быть готово к публикации топологии. Если имеются ошибки проверки, то перед публикацией топологии их необходимо исправить. Дополнительные сведения о публикации топологии см. в разделе [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).

