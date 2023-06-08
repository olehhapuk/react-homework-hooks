# Крок 2. Load More та модальне вікно

Продовжити створення сайту додавши кнопку Load More та модальне вікно для перегляду фото.

Створи компоненти `<Button>` та `<Modal>`. Готові стилі компонентів можна взяти у файлі [styles.css](../assets/styles.css) і підправити під себе, якщо потрібно.

## Інструкція Pixabay API

URL-рядок HTTP-запиту.

```bash
https://pixabay.com/api/?q=cat&page=1&key=your_key&image_type=photo&orientation=horizontal&per_page=12
```

Pixabay API підтримує пагінацію, за замовчуванням параметр `page` дорівнює `1`. Нехай у відповіді надходить по 12 об'єктів, встановлено в параметрі `per_page`. Не забудь, що під час пошуку за новим ключовим словом, необхідно скидати значення `page` до `1`.

У відповіді від апі приходить масив об'єктів, в яких тобі цікаві лише наступні властивості.

- `largeImageURL` – посилання на велике зображення для модального вікна

## Опис компонента `<Button>`

При натисканні на кнопку `Load more` повинна довантажуватись наступна порція зображень і рендеритися разом із попередніми. Кнопка повинна рендеритися лише тоді, коли є якісь завантажені зображення. Якщо масив зображень порожній, кнопка не рендериться.

## Опис компонента `<Modal>`

Під час кліку на елемент галереї повинно відкриватися модальне вікно з темним оверлеєм і відображатися велика версія зображення. Модальне вікно повинно закриватися по натисканню клавіші `ESC` або по кліку на оверлеї.

Зовнішній вигляд схожий на функціонал цього [VanillaJS-плагіна](https://basiclightbox.electerious.com/), тільки замість білого модального вікна рендериться зображення (у прикладі натисніть `Run`). Анімацію робити не потрібно!

```html
<div className="Overlay">
  <div className="Modal">
    <img src="" alt="" />
  </div>
</div>
```