# Bug Report API-003

## Создание папки по существующему пути возвращает HTTP-код 409 вместо 400

## Предусловия
1. Получен валидный OAuth-токен.
2. Папка `test1` уже существует.

## Шаги воспроизведения
1. Убедиться, что папка `test1` существует.
2. Ввести в поле `path` значение `test1`.
3. Нажать кнопку **«Попробовать!»**.
4. Проверить HTTP-код ответа.

## Фактический результат
Получен HTTP-код `409`.

Тело ответа:

```json
{
  "error": "DiskPathPointsToExistentDirectoryError",
  "description": "Specified path \"test1\" points to existent directory.",
  "message": "По указанному пути \"test1\" уже существует папка с таким именем."
}
```

Новая папка не создана.

## Ожидаемый результат
Получен HTTP-код `400`.
Новая папка не создана.

## Окружение
- Браузер: Mozilla Firefox 152.0.5
- ОС: Windows 11
- API: Яндекс Диск REST API
- Endpoint: `PUT https://cloud-api.yandex.net/v1/disk/resources`
- Инструмент: Swagger Яндекс.API

## Priority
Medium

## Severity
Medium

## Вложения
- [API-003-existing-folder.png](./API-003-existing-folder.png)

## Статус
Open

## На кого назначен
Unassigned