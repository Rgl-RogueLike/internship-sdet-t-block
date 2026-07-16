# Bug Report API-002

## Создание папки по несуществующему пути возвращает HTTP-код 409 вместо 400

## Предусловия
1. Получен валидный OAuth-токен.
2. Родительская папка `test2` отсутствует.

## Шаги воспроизведения
1. Отправить PUT-запрос на эндпоинт `https://cloud-api.yandex.net/v1/disk/resources` с параметром `path = test2/test21` (где `test2` не существует) и заголовками: `Authorization: OAuth <token>, Content-Type: application/json`.
2. Проверить HTTP-код ответа.
3. Проверить JSON-схему ответа.

## Фактический результат
Получен HTTP-код `409`.

Тело ответа:

```json
{
  "error": "DiskPathDoesntExistsError",
  "description": "Specified path \"test2/test21\" doesn't exists.",
  "message": "Указанного пути \"test2/test21\" не существует."
}
```

Папка не создана.

## Ожидаемый результат
Получен HTTP-код `400`.
Папка не создана.

## Окружение
- ОС: Windows 11
- API: Яндекс Диск REST API
- Endpoint: `PUT https://cloud-api.yandex.net/v1/disk/resources`

## Priority
Medium

## Severity
Medium

## Вложения
- [API-002-nonexistent-path.png](./API-002-nonexistent-path.png)

## Статус
Open

## На кого назначен
Unassigned