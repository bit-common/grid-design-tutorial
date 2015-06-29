# Grid Layout

Верстка - це процес створення такого html-файла, який забезпечує розміщення всіх функціональних, інформаційних та візуальних блоків сторінки. Для корегування вигляду сторінки використовують таблиці стилів (css файли).

## [HTML](https://en.wikipedia.org/?title=HTML)

Структура файлу

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Загальна конфігурація -->
  </head>
  <body>
    <!-- DOM - елементи -->
  </body>
</html>
```

Все, що знаходиться всередині тега `<body>` може бути видимим в браузері. Ми можемо розміщувати там три типи елементів, а саме,
* блочні (block)
* стрічкові (inline)
* стрічково-блочні (inline-block)

Блочний елемент займає всю доступну йому ширину (100% від батьківського блоку). Висота блочного елемента визначається його вмістом або відповідним css-правилом `height`.`<LINK href="special.css" rel="stylesheet" type="text/css">`
Найпопулярнішими блочними елементами є [div](http://www.w3schools.com/tags/tag_div.asp) (блок, секція сторінки), [p](http://www.w3schools.com/tags/tag_p.asp) (параграф), [h](http://www.w3schools.com/tags/tag_hn.asp) (заголовок) та інші.

Стрічкові елементи відрізняються від блокових (боксових) тим, що займають лише необхідну їм висоту та ширину. Окрім того, в них не можна включати лиш інші стрічкові елементи.
Найпопулярнішими стрічковими елементами є [a](http://www.w3schools.com/tags/tag_a.asp) (посилання), [span](http://www.w3schools.com/tags/tag_span.asp) (виділення частини тексту), [img](http://www.w3schools.com/tags/tag_img.asp) (зображення), [input](http://www.w3schools.com/tags/tag_input.asp) (поле вводу), тощо.

Стрічково-блочні елементи створюються за допомогою css - правила `display: inline-block`. Такий елемент поєднює властивості блочних та стрічкових елементів.

## [CSS](https://en.wikipedia.org/wiki/Cascading_Style_Sheets)

CSS файли підключаються в HTML-файлі тегом `<link href="адреса-до/main.css" rel="stylesheet" type="text/css">`
CSS код складається з селектора і правил, які ми хочемо йому присвоїти. Наприклад:
```
a{
  text-decoration: none;
  /* знімає підкреслення з посилань */
}

.header{
  background-color: #ccc;
  /* встановлює сірий колір тла для класу background */
}

#user-pic{
  display: none;
  /* ховає елемент з id user-pic */
}
```

css правила опрацьовуються двигуном зверху вниз, тому для селекторів однакової ваги буде використовуватися найнижче правило в файлі.

#### Вага селекторів

Деколи деякі селектори потрібно уточнювати. Так, ми доповнюємо, розширюємо класи, створюємо певні конструкції з html елементів. Поняття ваги селекторів допомагає нам конкретизувати множину елементів, до яких ми хочемо звернутися.

Пояснюю на коді.

```
<div id='top'>
    <p>Hello world!</p>
</div>
```

```
* Всі абзаци всередині будь-якого елемента з id top */
#top p {
}

/* Всі абзаци всередині елементів div */
div p {
}

/* Всі абзаци всередині елементів div з id top */
div#top p {
}

/* Всі абзаци в документі */
p {
}

/* Всі елементи всередині всіх елементів div */
div * {
}

/* Всі елементи всередині кожного елемента з id top */
#top * {
}
```

Вага правила залежить від наступних факторів:

* Місце визначення правила (правила, задані в тезі style мають більшу вагу, ніж в правила в стильовому файлі). Я ВАМ ЦЕ ЗАРАЗ КАЖУ, АЛЕ ПООБІЦЯЙТЕ, ЩО НІКОЛИ, ЧУЄТЕ, НІКОЛИ ТАК РОБИТИ НЕ БУДЕТЕ.
* Наскільки точно правило описує вкладеності (body p специфічніше ніж просто p)
* Наскільки точно правило вказує на елементи (body * маенш специфічне ніж body p)
* Наскільки точно правило вказує на класс та id елемента ( p#first і p.first специфічніше ніж p)
