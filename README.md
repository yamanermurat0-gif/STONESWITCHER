# Privacy Policy — StoneSwitcher

Статическая страница Privacy Policy в одном каталоге: `index.html` + `styles.css`.
Без сборки, без зависимостей и без JavaScript — готова к публикации на GitHub Pages как есть.

## Что менять перед публикацией

| Место | Что подставить |
|-------|----------------|
| `index.html`, `<title>` и `.eyebrow` | Имя приложения, если оно отличается от `StoneSwitcher` |
| `index.html`, `#definitions` → `Country/State` | Юрисдикция компании |
| `index.html`, `.updated` | Дата «Last updated» (сейчас 2026-11-06) |

Контакты в секции `#contact` уже заполнены. Текст политики перенесён дословно.

## Не открывайте `index.html` в TextEdit

TextEdit открывает `.html` как форматированный текст и при сохранении **перезаписывает файл
собственной разметкой** (`<meta name="Generator" content="Cocoa HTML Writer">`): пропадает
`<link rel="stylesheet">`, секции и якоря, остаётся Times 12px на белом фоне. Правьте только
в редакторе кода (VS Code, Xcode, `nano`) либо через `Open With → Other → TextEdit` с галкой
«Ignore rich text commands».

## Публикация на GitHub Pages

### Вариант 1 — отдельный репозиторий (проще всего)

```bash
# из корня этого каталога
git init
git add index.html styles.css README.md
git commit -m "Privacy Policy for StoneSwitcher"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

Затем в репозитории: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `/ (root)`**.
Через минуту страница будет доступна по адресу `https://<user>.github.io/<repo>/`.

### Вариант 2 — папка внутри существующего репозитория

Если каталог уже лежит в репозитории, включите Pages и укажите в качестве источника
ветку и папку с этими файлами (например `/docs`, если перенести туда). Pages отдаёт
страницу только из корня выбранной папки, поэтому `index.html` должен лежать
непосредственно в ней.

## Проверка локально

```bash
python3 -m http.server 8000
# открыть http://localhost:8000/
```

## Особенности вёрстки

- Светлая и тёмная тема — автоматически по системной настройке (`prefers-color-scheme`).
- Адаптив: на широких экранах оглавление фиксируется сбоку, на мобильных уходит наверх.
- Печать: шапка, оглавление и ссылка «Back to top» скрываются (`@media print`).
- Акцентный цвет взят из конфигурации приложения (`splash_color: #AE4233`).

## Ссылка для App Store Connect

В App Store Connect в поле **Privacy Policy URL** указывается полный адрес опубликованной
страницы, например `https://<user>.github.io/<repo>/`.
