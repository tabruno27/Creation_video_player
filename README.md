# Пример подключения видеоплеера
## Описание
Данный проект демонстрирует, как подключить и настроить видеоплеер на веб-странице с использованием HTML, CSS и JavaScript. Плеер включает базовые элементы управления, такие как воспроизведение, пауза, регулировка громкости и полноэкранный режим.

![image](https://github.com/user-attachments/assets/6aa48f6a-c31e-483a-bfcd-90e809e7e563)

## Используемые технологии
**HTML5:** Основная структура веб-страницы.

**CSS:** Стилизация элементов плеера.

**JavaScript:** Логика работы плеера и взаимодействие с элементами управления.

**Font Awesome:** Используется для отображения иконок.

## Структура проекта
**index.html:** Основной файл, содержащий разметку плеера.

**player.js:** Файл, содержащий логику работы плеера (необходим для создания плеера, необходимо реализовать).

**Библиотеки:**
- jQuery (для упрощения работы с DOM)
- Playable.js (для создания видеоплеера)

## Установка
1. Склонируйте репозиторий или скачайте ZIP-архив с проектом.
2. Откройте файл index.html в вашем браузере.

Как выглядит плеер можно посмотреть [тут](http://localhost:63342/Creation_video_player/dist/index.html?_ijt=9s6lqspkljougre3gglaskrhi6&_ij_reload=RELOAD_ON_SAVE)

### Как подключить библиотеки
JS код поставляется в виде одного файла ```player.js```, который нужно скачать из этого репозитория. Для работы он требует двух библиотек - jQuery и Playable. Пример подключения в браузере:

```bash
<script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
<script src="https://unpkg.com/playable@2.10.3/dist/statics/playable.bundle.min.js"></script>
<script src="player.js"></script>
```
### Если хотите другое видео
Если вы хотите выбрать другое видео, вы можете указать его с помощью аргумента ```src```. Убедитесь, что ссылки заканчиваются расширением файла. 
Пример:

```bash
<script type="text/javascript">
  createPlayer({
    elementId: 'player',
    src: 'https://dvmn.org/media/filer_public/d0/16/d016d9b8-4180-4bb9-ad83-0241f61627b8/samsung_demo_-_alive_in_color.mp4'
  });
</script>
```
**Обратите внимание, что скрипт player.js необходимо подключать строго после ```<div>``` с указанным elementId.**

## Как подключить кнопки
Для корректного функционирования плеера необходимо добавить HTML-разметку для кнопок управления. Вот пример, как можно организовать кнопки с использованием иконок:

```bash
<div class="controls">
    <button class="control-button js-play-button">
        <i class="fa fa-play icon" aria-hidden="true"></i>
    </button>
</div>    
```

### Элементы управления
Каждая кнопка имеет свой класс, который используется для управления функциональностью плеера:

```js-play-button``` — кнопка для воспроизведения видео. Она будет отображаться, когда видео остановлено.

```js-pause-button``` — кнопка для паузы видео. Эта кнопка автоматически скрывается при инициализации плеера и отображается, когда видео воспроизводится.

```js-volume-button``` — кнопка для увеличения громкости. Эта кнопка будет активна, когда звук включен.

```js-mute-button``` — кнопка для отключения звука. Она автоматически скрывается, когда звук выключен. Чтобы избежать мерцания, вы можете добавить атрибут hidden в момент загрузки страницы.

```js-fullscreen-button``` — кнопка для перехода в полноэкранный режим.

### Использование иконок
В данном примере иконки для кнопок берутся из библиотеки Font Awesome. Убедитесь, что вы подключили эту библиотеку в вашем проекте, добавив следующий код в ```<head>``` вашего HTML-документа:

```bash
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
```

### Стилизация кнопок
Вы можете изменить стиль кнопок с помощью CSS. Например, вы можете добавить следующий код, чтобы настроить внешний вид кнопок:

```bash
.control-button {
    width: 37px; /* Ширина кнопки */
    height: 37px; /* Длинна кнопки */
    border-style: none; /* Убираем рамку */
    cursor: pointer; /* Курсор при наведении */
    margin: 0.3%; /* Отступы между кнопками */
    background-color: transparent; /* Прозрачный фон */
    font-size: 150% /* Размер иконки внутри кнопки */
}
.icon {
   color:white; /* Цвет иконок */
}
```

Добавьте этот CSS-код в ваш файл стилей или внутри ```<style>``` тега в HTML, чтобы изменить внешний вид кнопок.

## Цель проекта
Код написан в образовательных целях на онлайн-курсе для веб-разработчиков dvmn.org.
