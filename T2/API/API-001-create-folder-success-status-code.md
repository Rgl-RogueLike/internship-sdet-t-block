# Bug Report API-001

## Создание новой папки возвращает HTTP-код 201 вместо 200

## Предусловия
1. Получен валидный OAuth-токен.
2. Папка с именем `test1` отсутствует.

## Шаги воспроизведения
1. Ввести в поле `path` значение `test1`.
2. Нажать кнопку **«Попробовать!»**.
3. Проверить HTTP-код ответа.

## Фактический результат
Получен HTTP-код `201`.
Папка успешно создана.

## Ожидаемый результат
Получен HTTP-код `200`.
Папка создана по указанному пути.

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
- [API-001-success-create.png](./API-001-success-create.png)

## Статус
Open

## На кого назначен
Unassigned