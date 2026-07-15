# Bug Report API-004

## Успешное создание папки при отсутствии обязательного заголовка Content-Type

## Предусловия
1. Получен валидный OAuth-токен.
2. Папка `test_postman2` отсутствует.

## Шаги воспроизведения
1. Открыть Postman.
2. Создать PUT-запрос `https://cloud-api.yandex.net/v1/disk/resources?path=test_postman2`.
3. Во вкладке Headers передать только `Authorization: OAuth <токен>`.
4. Убедиться, что заголовок `Content-Type` отсутствует.
5. Отправить запрос.

## Фактический результат
Получен HTTP-код `201`. Папка успешно создана на диске.

## Ожидаемый результат
Получен HTTP-код `400 Bad Request`. Новая папка не создана, так как отсутствует обязательный заголовок `Content-Type: application/json`.

## Окружение
- ОС: Windows 11
- Инструмент: Postman
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