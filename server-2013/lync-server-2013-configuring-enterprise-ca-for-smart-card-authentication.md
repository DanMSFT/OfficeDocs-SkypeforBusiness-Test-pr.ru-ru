﻿---
title: Настройка центра сертификации предприятия для проверки подлинности с помощью смарт-карты
TOCTitle: Настройка центра сертификации предприятия для проверки подлинности с помощью смарт-карты
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn308571(v=OCS.15)
ms:contentKeyID: 56270608
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка центра сертификации предприятия для проверки подлинности с помощью смарт-карты

 

_**Дата изменения раздела:** 2016-12-08_

В этом разделе описывается порядок настройки корневого центра сертификации (ЦС) предприятия для проверки подлинности с помощью смарт-карт. Сведения о том, как установить корневой ЦС предприятия, см. в разделе "Установка корневого центра сертификации предприятия" на странице [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).

## Настройка корневого центра сертификации предприятия для проверки подлинности с помощью смарт-карт

Ниже описан порядок действий по настройке корневого ЦС предприятия для проверки подлинности с помощью смарт-карт.

1.  Войдите на компьютер ЦС предприятия с учетной записью администратора домена.

2.  Запустите приложение System Manager и убедитесь в том, что установлена роль регистрации сертификатов через Интернет.

3.  В меню **Администрирование** откройте консоль управления **Центр сертификации**.

4.  В области навигации разверните узел **Центр сертификации**.

5.  Щелкните правой кнопкой элемент **Шаблоны сертификатов**, выберите команду **Создать**, а затем выберите **Выдаваемый шаблон сертификата**.

6.  Выберите параметры **Агент подачи заявок**, **Пользователь смарт-карты** и **Вход со смарт-картой**.

7.  Нажмите кнопку **ОК**.

8.  Щелкните правой кнопкой мыши элемент **Шаблоны сертификатов**.

9.  Выберите элемент **Управление**.

10. Откройте свойства шаблона пользователя смарт-карты.

11. Откройте вкладку **Безопасность**.

12. Задайте указанные ниже разрешения.
    
      - Добавьте учетные записи отдельных пользователей Active Directory с разрешениями на чтение и подачу заявок (разрешить).
    
      - Добавьте группу безопасности с пользователями смарт-карт, обладающую разрешениями на чтение и подачу заявок (разрешить).
    
      - Добавьте группу пользователей домена с разрешениями на чтение и подачу заявок (разрешить).
