# Volga-It от Serolapy #

> **Программирование на языке JavaScript** <br>Иванов Владислав, ПсковГУ, Институт Инженерных наук

## Пример подключения к странице ##
[Ссылка для просмотра страницы "вживую"][1]. Страница с наполнением контента.

Также код собранного виджета находится в `index.html`. Странца без наполнения контентом.

## Подключение к странице ##
Чтобы подключить виджет к странице, необходимо:

 0. Подключить к странице, где будет расположен виджет, React JS и Babel, если их ещё нет. Пример:
```
<!-- React -->
<script src="https://unpkg.com/react@17/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
<!-- Babel -->
<script src="https://unpkg.com/@babel/standalone/babel.js"></script>
```
 1. Разместить файлы `main.css`, `script.js`, "папки" `img` и `fonts` (вместе с содержимым!) на хостинге (сервере).
 2. Рассмотреть содержимое файла `widget.html` и подключать так:

```
<html>
  <head>
    <!--код-->

    <style>
	  #glasses-quiz-widget{
		top: 0;
		left: 0;
		--glassesQuizWidget_width: 375px; 	/*ширина виджета - не меньше 318px - стандарт 375px*/
		--glassesQuizWidget_height: 638px; 	/*высота виджета - стандарт 638px*/
	  }
    </style>
    <link rel="stylesheet" href="main.css">

    <!--код-->
  </head>
  <body>
    <!--код-->

    <div id="glasses-quiz-widget" data-source="https://example.com/"></div>
    <script type="text/babel" src="script.js"></script>

    <!--код-->
  </body>
</html>
```
  3. Подогнать настройки под свои нужды.

### Настройка виджета ###
**Размещение на странице**

В атрибутах `src` и `href` указанных ниже строк установить значения пути (ссылки) на файлы `script.js` и `main.css` соответственно:
```
<link rel="stylesheet" href="ссылка на main.css">
<script type="text/babel" src="ссылка на script.js"></script>
```
Настроить позирование виджета на странице **относительно границ** экрана. Это делается в тегах `<style></style>` (см. код выше). При скроллинге страницы виджет остаётся неподвижен.

1. `top` и `left` - позирование относительно верхней и левой границы экрана. Можно заменить на `right` и/или `bottom` при надобности.
2. `--glassesQuizWidget_width` - ширина виджета, `--glassesQuizWidget_height` - его высота.

**Настройка файла `script.js`**

Заменить значение константы `glassesQuizWidget_imgUrl` на путь к папке `img`. В данном репозитории скрипт и папка с картинками находятся на одном уровне дерева папок, потому в даном случае
```
const glassesQuizWidget_imgUrl = 'img/';
```

## Особенности моего варианта выполнения задания ##

Это мой первый опыт работы с ReactJS, потому код может быть не столь эффективным, однако он рабочий!

Содержимое многих страниц виджета было выровнено при помощи графических редакторов: скриншота узла накладывался на картинку с Фигмы и выполнялась коррекция положений элементов, если она была нужна.

Добавлено немного визуальных анимаций при помощи CSS и JS: движение голубой линии ("status bar") выполняется плавно; при наведении мыши на кнопки последние отбразывают тень, чтобы привлечь внимание пользователя к содержимому выбранной кнопки; на страницах 8 и 10 возможен скроллинг кнопок с брендами и типами очков при помощи колёсика мыши; если не выбрана ни одна кннопка на этих же страницах, то при наведении курсора на "Continue" пользователь увидит "запрещающий" курсор.


  [1]: https://serolapy.github.io/volgaIt22/
