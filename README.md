# Price Data

Единый источник данных прайс-листа для проектов [price](https://github.com/getto-dev/price) и [check](https://github.com/getto-dev/check).

## Использование

### Raw URL
```
https://raw.githubusercontent.com/getto-dev/price-data/main/catalog.json
```

### Пример загрузки

```typescript
const CATALOG_URL = 'https://raw.githubusercontent.com/getto-dev/price-data/main/catalog.json';

// Загрузка при сборке
async function loadCatalog() {
  const response = await fetch(CATALOG_URL);
  const data = await response.json();
  return data;
}
```

## Структура данных

```json
{
  "version": "2026.1",
  "updated": "2025-03-02",
  "categories": [
    { "id": "heating", "name": "Отопление" },
    ...
  ],
  "services": {
    "heating": [
      { "id": "heat_001", "n": "Название", "d": "Описание", "u": "ед.", "p": 1000 },
      ...
    ],
    ...
  }
}
```

### Формат услуги

| Поле | Описание |
|------|----------|
| `id` | Уникальный идентификатор |
| `n` | Название услуги |
| `d` | Описание |
| `u` | Единица измерения |
| `p` | Цена в рублях |

## Категории

- `heating` - Отопление
- `floor_heat` - Теплый пол
- `water` - Водоснабжение
- `boilers` - Котельные
- `chimneys` - Дымоходы
- `sewerage` - Канализация
- `pipes` - Прокладка труб
- `filtration` - Водоочистка
- `automation` - Автоматика
- `grooving` - Штробление
- `service` - Сервис
- `plumbing` - Сантехника

## Обновление

1. Отредактируйте `catalog.json`
2. Обновите поле `updated`
3. При значительных изменениях обновите `version`
