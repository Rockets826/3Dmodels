# Backup разметки навигации

Файл **`room-markup-backup.json`** — эталонная разметка всех корпусов в репозитории.

При открытии `lsu-dal-campus-nav.html` приложение:

1. Загружает этот JSON (если файл не пустой).
2. Поверх подставляет данные из **localStorage** браузера (ключ `lsu-dal-campus-nav-room-markup-v1`), если они есть.

## Как сохранить вашу разметку из браузера Cursor

**Способ A (рекомендуется)**

1. Откройте навигацию через локальный сервер: `npm start` → http://127.0.0.1:3000/lsu-dal-campus-nav.html  
2. Включите «Режим разметки».
3. Нажмите **«Скачать backup для репозитория»**.
4. Сохраните скачанный файл сюда, заменив `room-markup-backup.json`.
5. Закоммитьте в git.

**Способ B (из DevTools)**

1. F12 → Application → Local Storage → ключ `lsu-dal-campus-nav-room-markup-v1`.
2. Скопируйте значение целиком.
3. Вставьте в `room-markup-backup.json` (должен быть валидный JSON-объект `{ "korpus-01": […], … }`).

## Формат

```json
{
  "korpus-04": [
    {
      "id": "k04-hall",
      "label": "Холл",
      "floor": 1,
      "local": { "x": 0, "z": 1 },
      "kind": "hall",
      "corridorPath": [{ "x": 1, "z": 0 }]
    }
  ]
}
```

Пустой `{}` — backup отключён, используются только дефолты из кода и localStorage.
