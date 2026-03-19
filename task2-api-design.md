# Проектирование API: экран партнерских магазинов

## Контекст

В мобильном приложении реализуется экран партнерских магазинов.

Цель - предоставить пользователю список доступных партнеров с возможностью перехода на внешний ресурс.

---

## Экран

![Partners Screen](./diagrams/partners-screen.jpg)

---

## Endpoint

GET /api/v1/partners

---

## Пример запроса

```http
GET /api/v1/partners?city=moscow&platform=android
Authorization: Bearer <token>
Accept: application/json
```

## Пример ответа

```json
{
  "stores": [
    {
      "id": "store_1",
      "name": "METRO",
      "logo_url": "https://cdn.shop.ru/stores/metro-cc.png",
      "external_url": "https://metro-cc.ru",
      "delivery_info": {
        "type": "scheduled",
        "title": "Ближайшая доставка",
        "subtitle": "сегодня 21:00–23:00",
        "date": "2026-03-03",
        "time_from": "21:00",
        "time_to": "23:00",
        "is_today": true
      }
    },
    {
      "id": "store_2",
      "name": "Ашан",
      "logo_url": "https://cdn.shop.ru/stores/auchan.png",
      "external_url": "https://auchan.ru",
      "delivery_info": {
        "type": "scheduled",
        "title": "Ближайшая доставка",
        "subtitle": "сегодня 18:00–20:00",
        "date": "2026-03-03",
        "time_from": "18:00",
        "time_to": "20:00",
        "is_today": true
      }
    },
    {
      "id": "store_3",
      "name": "ВкусВилл",
      "logo_url": "https://cdn.shop.ru/stores/vkusvill.png",
      "external_url": "https://vkusvill.ru",
      "delivery_info": {
        "type": "express",
        "title": "Быстрая доставка",
        "subtitle": "от 20 до 60 минут",
        "min_minutes": 20,
        "max_minutes": 60,
        "ui_hint": {
          "subtitle_emphasis": "accent"
        }
      }
    },
    {
      "id": "store_4",
      "name": "ВИКТОРИЯ",
      "logo_url": "https://cdn.shop.ru/stores/victoria-group.png",
      "external_url": "https://victoria-group.ru",
      "delivery_info": {
        "type": "scheduled",
        "title": "Ближайшая доставка",
        "subtitle": "сегодня 17:00–19:00",
        "date": "2026-03-03",
        "time_from": "17:00",
        "time_to": "19:00",
        "is_today": true
      }
    }
  ]
}
```