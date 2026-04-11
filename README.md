# 3D-навигация по кампусу (ЛГУ)

Статический сайт: `lsu-dal-campus-nav.html`, модели GLB в папке `3D/`.

## Локальный сервер

**Вариант A — без установки зависимостей** (нужен Node.js):

```bash
npx --yes serve . -l 3000
```

**Вариант B — через npm в этом проекте:**

```bash
npm install
npm start
```

**Вариант C — встроенный сервер Python:**

```bash
python -m http.server 3000
```

Откройте в браузере: [http://127.0.0.1:3000](http://127.0.0.1:3000) (корень отдаёт `index.html` с переходом на сцену).

**Не открывайте HTML двойным щелчком** (`file://`) — GLB не загрузятся.

## Подключение к GitHub

1. Создайте **новый репозиторий** на GitHub (без README, если уже есть файлы локально).

2. В этой папке выполните (подставьте свой URL):

   ```bash
   git init
   git add .
   git commit -m "Initial commit: campus 3D nav"
   git branch -M main
   git remote add origin https://github.com/ВАШ_ЛОГИН/ИМЯ_РЕПО.git
   git push -u origin main
   ```

3. В репозитории на GitHub: **Settings → Pages → Build and deployment → Source** выберите **GitHub Actions**.

4. После успешного workflow сайт будет по адресу:

   `https://ВАШ_ЛОГИН.github.io/ИМЯ_РЕПО/`

   Откройте `lsu-dal-campus-nav.html` или корень (редирект через `index.html`). Пути к моделям относительные (`./3D/…`) — для project pages это работает.

### Большие GLB

Если репозиторий раздувается из‑за моделей, используйте [Git LFS](https://git-lfs.github.com/) или храните тяжёлые файлы в релизах / внешнем хранилище и укажите `BASE_URL` в скрипте на этот URL.

## Настройка корпусов

В начале `lsu-dal-campus-nav.html` отредактируйте массив `MANUAL_BUILDINGS` и при необходимости `MODEL_CONFIG.BASE_URL`.
