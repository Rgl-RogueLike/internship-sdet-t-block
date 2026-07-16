# Bug Report API-001

## Создание новой папки возвращает HTTP-код 201 вместо 200

## Предусловия
1. Получен валидный OAuth-токен.
2. Папка с именем `test1` отсутствует.

## Шаги воспроизведения
1. Отправить PUT-запрос на эндпоинт `https://cloud-api.yandex.net/v1/disk/resources` с параметром `path = test1` и заголовками: `Authorization: OAuth <token>, Content-Type: application/json`.
2. Проверить HTTP-код ответа.
3. Проверить JSON-схему ответа.

## Фактический результат
Получен HTTP-код `201`.
Папка успешно создана.

## Ожидаемый результат
Получен HTTP-код `200`.
Папка создана по указанному пути.

## Окружение
- ОС: Windows 11
- API: Яндекс Диск REST API
- Endpoint: `PUT https://cloud-api.yandex.net/v1/disk/resources`

## Priority
Medium

## Severity
Medium

## Вложения
- [API-001-success-create.png](./API-001-success-create.png)

## Статус
Open

## На кого назначен
Unassigned