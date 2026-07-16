# Bug Report API-004

## Успешное создание папки при отсутствии обязательного заголовка Content-Type

## Предусловия
1. Получен валидный OAuth-токен.
2. Папка `test4` отсутствует.

## Шаги воспроизведения
1. Отправить PUT-запрос на эндпоинт `https://cloud-api.yandex.net/v1/disk/resources` с параметром `path = test4` и заголовками: `Authorization: OAuth <token>`, (заголовок `Content-Type` намеренно отсутствует).
2. Проверить HTTP-код ответа.
3. Проверить JSON-схему ответа.

## Фактический результат
Получен HTTP-код `201`. Папка успешно создана на диске.

## Ожидаемый результат
Получен HTTP-код `400 Bad Request`. Новая папка не создана, так как отсутствует обязательный заголовок `Content-Type: application/json`.

## Окружение
- ОС: Windows 11
- API: Яндекс Диск REST API
- Endpoint: `PUT https://cloud-api.yandex.net/v1/disk/resources`

## Priority
Medium

## Severity
Medium

## Вложения
- [API-004-missing-content-type.png](./API-004-missing-content-type.png)

## Статус
Open

## На кого назначен
Unassigned