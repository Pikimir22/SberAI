# Проект по автоматизации тестирования web приложения Sber Frontend

## 	Содержание

> ➠ [Покрытый функционал](#покрытый-функционал)
>
> ➠ [Технологический стек](#технологический-стек)
>
> ➠ [Запуск тестов из терминала](#запуск-тестов-из-терминала)
>
> ➠ [Запуск тестов в Jenkins](#-удаленный-запуск-тестов-в-Jenkins)
>
> ➠ [Отчет о результатах тестирования в Allure Report](#-главная-страница-allure-отчета)
>
> ➠ [Уведомления в Telegram с использованием бота](#-уведомления-в-telegram-с-использованием-бота)
>
> ➠ [Пример запуска теста в Selenoid](#-пример-запуска-теста-в-selenoid)

##  Покрытый функционал

> Разработаны автотесты на <code>UI</code>.
### UI

- [x] Поиск статьи негативный/позитивный тест
- [x] Переход по категориям
- [x] Фильтрация статей по дате
- [x] Переход по кнопке

## Технологический стек

<p align="center">
<img width="6%" title="IntelliJ IDEA" src="readme_design/Intelij_IDEA.svg">
<img width="6%" title="Java" src="readme_design/Java.svg">
<img width="6%" title="Selenide" src="readme_design/Selenide.svg">
<img width="6%" title="Selenoid" src="readme_design/Selenoid.svg">
<img width="6%" title="Allure Report" src="readme_design/Allure_Report.svg">
<img width="6%" title="Gradle" src="readme_design/Gradle.svg">
<img width="6%" title="JUnit5" src="readme_design/JUnit5.svg">
<img width="6%" title="GitHub" src="readme_design/GitHub.svg">
<img width="6%" title="Jenkins" src="readme_design/Jenkins.svg">
<img width="6%" title="Telegram" src="readme_design/Telegram.svg">
</p>

### В данном проекте автотесты написаны на <code>Java</code> с использованием <code>Selenide</code> для UI-тестов.
>
> <code>Selenoid</code> выполняет запуск браузеров в контейнерах <code>Docker</code>.
>
> <code>Allure Report</code> формирует отчет о запуске тестов.
>
> Для автоматизированной сборки проекта используется <code>Gradle</code>.
>
> В качестве библиотеки для модульного тестирования используется <code>JUnit 5</code>.
>
> <code>Jenkins</code> выполняет запуск тестов.
>
> После завершения прогона отправляются уведомления с помощью бота в <code>Telegram</code>.

## Запуск тестов из терминала

### Локальный запуск тестов

#### Локальный запуск тестов с использованием параметров из property файла

```
gradle clean ui_tests -Denv={имя property файла в test.resources}
```

#### Локальный запуск тестов с использованием параметров из property файла test

```
gradle clean test
```

#### Описание параметров для запуска тестов

<p align="center">
<img title="Jenkins" src="readme_design/screens/image_2023-02-12_18-10-25.png">
</p>

##### Пример файла
```
browserName=chrome
browserVersion=108
baseUrl=https://www.google.com
browserSize=1920x1080
pageLoadTimeout=10000
timeout=10000
headless=false
isRemote=true
remoteUrl=https://selenoid.autotests.cloud
```

## <img width="4%" title="Jenkins" src="readme_design/Jenkins.svg"> Удаленный запуск тестов в Jenkins

> Для запуска тестов используется параметризированная сборка

<p align="center">
<img title="Jenkins" src="readme_design/screens/Jenkins.png">
</p>

#### 2. Выбрать пункт **Собрать с параметрами**
#### 3. В случае необходимости изменить параметры, выбрав значения из выпадающих списков
#### 4. Нажать **Собрать**
#### 5. Результат запуска сборки можно посмотреть в отчёте Allure

<p align="center">
<img title="Jenkins" src="readme_design/screens/Jenkins1.png">
</p>

## <img width="4%" title="Allure_Report" src="readme_design/Allure_Report.svg"> Главная страница allure отчета

<p align="center">
<img title="Allure_main" src="readme_design/allureScreen/Allure главная.png">
</p>

### <img width="4%" title="Allure_Report" src="readme_design/Allure_Report.svg"> Группировка тестов по проверяемому функционалу

<p align="center">
<img title="Allure_suits" src="readme_design/allureScreen/Allure Suite.png">
</p>

### <img width="4%" title="Allure_Report" src="readme_design/Allure_Report.svg"> Основной дашборд

<p align="center">
<img title="Allure_dashboard" src="readme_design/allureScreen/Allure Dash.png">
</p>

## <img width="4%" title="Telegram" src="readme_design/Telegram.svg"> Уведомления в Telegram с использованием бота

> После завершения сборки специальный бот, созданный в <code>Telegram</code>, автоматически обрабатывает и отправляет сообщение с отчетом о прогоне.
>
> Информация по настройке и использованию бота <code>https://github.com/qa-guru/allure-notifications</code>

<p align="center">
<img title="Telegram_notifications" src="readme_design/screens/Telegram.png">
</p>

## <img width="4%" title="Selenoid" src="readme_design/Selenoid.svg"> Пример запуска теста в Selenoid

> К каждому тесту в отчете прилагается видео. Одно из таких видео представлено ниже.

<p align="center">
<img title="Selenoid_gif" src="readme_design/allureScreen/7de60b9f3e783f5b0a470552a9896364.gif">
</p>
