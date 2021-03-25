---
title: "<img>"
author: grachev
contributors: skorobaeus
summary:
  - картинка
  - img
---

## Кратко

Тег `<img>` добавляет изображение на страницу.

Можно встроить изображение в формате GIF, JPEG или PNG. Поддержка других форматов зависит от браузера.

## Пример

```html
<img src="URL" alt="Текст, который покажут, если картинка не загрузится">
```

## Как пишется

Пропишите внутри `<img>` ссылку на картинку и настройте другие параметры с помощью атрибутов.

🤖 `<img>` — это один из замещаемых элементов: на такие не распространяются CSS-стили. С помощью стилей можно задать положение картинки, но не её внешний вид.

## Атрибуты

- `alt` — браузер покажет этот текст, если картинка не загрузится. Такое может быть из-за ошибки в URL изображения, неподдерживаемого формата или если изображение не успевает загрузиться. Текст в `alt` называется альтернативным текстом изображения: обычно он описывает то, что изображено на картинке.
- `crossorigin` — запрещает или ограничивает использование изображения другими сайтами. Можно настроить два параметра:
- `anonymous` — сайты могут использовать оригинал вашей картинки, но cookie, пароли и другую информацию они не получат;
- `use-credentials` — сайты могут получить оригинал изображения, а также cookie, сертификат, данные доступа.
- `decoding` — подсказывает браузеру, в какой момент показывать изображение, относительно остального содержимого страницы. Есть три режима:
- `sync` — изображение появляется одновременно с остальным содержимым;
- `async` — изображение начинает появляться после основного содержимого, чтобы быстрее загрузить основной контент страницы;
- `auto` — браузер пользователя сам решит, загружать картинку одновременно с остальным контентом или асинхронно.
- `height` — высота изображения в пикселях. В HTML 4 высота могла быть определена в пикселях или в процентах, а в HTML5 — только в пикселях.
- `ismap` — сообщает браузеру, что перед нами не просто картинка, а серверная карта-изображение. Это значит, что тот или иной участок изображения может быть ссылкой. И, если на неё кликнуть, браузер отправит на сервер точные координаты нажатия мыши. Это сработает только если изображение `<img>` находится внутри элемента `<a href="URL">`. Координаты будут отправлены в пикселях, например, x = 313 (px); y = 156 (px), относительно границ изображения.
- `longdesc` — ссылка на подробное описание изображения. Задаётся с помощью URL или id элемента.
- `sizes` — определяет, какой размер картинки нужно использовать на том или ином размере экрана.
- `src` — обязательный атрибут, который указывает адрес вашей картинки.
- `srcset` — с его помощью вы пропишите, какие изображения на каких устройствах можно использовать.
- `width` — ширина изображения в пикселях. Её важно указать, чтобы браузер быстрее загружал картинку. В HTML 4 ширина могла быть определена в пикселях или в процентах, а в HTML5 — только в пикселях.
- `usemap` — часть URL после #, которая отсылает к картинке. Этот атрибут нельзя использовать, если ваш `<img>` находится внутри элемента `<a>` или `<button>`.

## Что может пойти не так

Изображение на странице может не загрузиться в нескольких случаях:

- Если атрибут `src` не содержит адрес или адрес неправильный.
- Если в `src` задан такой же URL, что и у страницы, на которой вы находитесь.
- Нужное изображение повреждено.
- Метадата изображения повреждена и не содержит информацию о его размере, а атрибуты `<img>` не задают размер картинки.
- Браузер не поддерживает такой формат изображения.

## Подсказки

💡 Картинка может и сама быть ссылкой: для этого поместите тег `<img>` в контейнер `<a>`. Вокруг изображения при этом появится рамка, которую можно убрать, если добавить атрибут `border="0"` в тег `<img>`.

💡 Старайся всегда прописывать `alt` изображения. Если пользователь открывает страницу в невизуальном браузере, или он отключил изображения, или использует озвучивание текста с экрана, то альтернативный текст подскажет, что изображено на картинке.

💡 Прописывай ширину `width` и высоту `height` изображения, чтобы страница загружалась быстрее. Задавая значения этим атрибутам не пишите `px`, только числа.

💡 При этом если указать некорректные ширину и высоту, то картинка деформируется. Чтобы не сломать макет и не высчитывать промежуточные размеры (современный браузер может просчитать их за вас), особенно, если ширина или высота задаётся в процентах, лучше указывать только один из параметров. Это происходит потому, что картинка строчный, а не блоковый элемент.

💡 Используй атрибуты `sizes` и `srcset`, чтобы ваша картинка адаптировалась на разных устройствах. Получается красиво, а страница загружается быстрее.

## Ещё примеры

```html
<img
  class="fit-picture"
  src="images/dogs.png"
  alt="doka mainpage dog"
>
```

```css
.fit-picture {
  width: 50%;
}
```

<iframe title="Картинка с заданной шириной" src="demos/img-fix-width.html"></iframe>