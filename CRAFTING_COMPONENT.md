# Компонент CraftingRecipe

Компонент для отображения крафтов Minecraft в современном тёмном стиле.

## Характеристики

- ✨ Современный тёмный дизайн с чёткими ячейками
- 🎮 Поддержка всех типов крафтов (shaped, shapeless, smelting и др.)
- 📱 Адаптивный дизайн для мобильных устройств
- 🖼️ Автоматическая загрузка иконок предметов
- 💡 Подсказки при наведении на предметы

## Использование

### Фигурные крафты (Shaped)

Для крафтов с определённым расположением предметов в сетке 3x3:

```mdx
<CraftingRecipe
  type="shaped"
  pattern={[
    [null, "blaze_powder", null],
    [null, "paper", null],
    [null, "sweet_berries", null]
  ]}
  result="cigarette"
/>
```

### Бесформенные крафты (Shapeless)

Для крафтов, где порядок предметов не важен:

```mdx
<CraftingRecipe
  type="shapeless"
  ingredients={["ender_pearl", "blaze_powder"]}
  result="ender_eye"
/>
```

### Плавка в печи (Smelting)

Для крафтов с использованием печи:

```mdx
<CraftingRecipe
  type="smelting"
  ingredient="iron_ore"
  result="iron_ingot"
  fuel="coal"
/>
```

## Примеры из вики

### Сигарета

```mdx
<CraftingRecipe
  type="shaped"
  pattern={[
    [null, "blaze_powder", null],
    [null, "paper", null],
    [null, "sweet_berries", null]
  ]}
  result="cigarette"
/>
```

### Пачка сигарет

```mdx
<CraftingRecipe
  type="shaped"
  pattern={[
    ["paper", "paper", "paper"],
    ["paper", null, "paper"],
    ["paper", "paper", "paper"]
  ]}
  result="cigarette_pack_empty"
/>
```

### Наручники

```mdx
<CraftingRecipe
  type="shaped"
  pattern={[
    ["iron_ingot", null, "iron_ingot"],
    ["iron_ingot", "chain", "iron_ingot"],
    ["iron_ingot", null, "iron_ingot"]
  ]}
  result="handcuffs"
/>
```

### Дымовая шашка

```mdx
<CraftingRecipe
  type="shaped"
  pattern={[
    ["iron_ingot", "iron_ingot", "iron_ingot"],
    ["kelp", "gray_concrete_powder", "kelp"],
    ["iron_ingot", "spectral_arrow", "iron_ingot"]
  ]}
  result="smoke_bomb"
/>
```

## Параметры

### Shaped Recipe

- `type`: `"shaped"` - тип крафта
- `pattern`: `(string | null)[][]` - сетка 3x3 с ID предметов или null для пустых ячеек
- `result`: `string` - ID результирующего предмета
- `resultCount?`: `number` - количество получаемых предметов (опционально)

### Shapeless Recipe

- `type`: `"shapeless"` - тип крафта
- `ingredients`: `string[]` - массив ID предметов
- `result`: `string` - ID результирующего предмета
- `resultCount?`: `number` - количество получаемых предметов (опционально)

### Smelting Recipe

- `type`: `"smelting" | "blasting" | "smoking" | "campfire"` - тип плавки
- `ingredient`: `string` - ID исходного предмета
- `result`: `string` - ID результирующего предмета
- `fuel?`: `string` - ID топлива (опционально, по умолчанию "coal")

## Источники иконок

Компонент автоматически загружает иконки предметов из двух источников:

1. **Кастомные иконки**: `windmc-wiki/items/{item}.png`
2. **Стандартные иконки**: Minecraft assets из PrismarineJS

Если иконка не найдена, отображаются первые 3 буквы ID предмета.

## Стиль

Компонент использует тёмный стиль с:
- Фон контейнера: `#0d0d0d`
- Фон сетки: `#141414`
- Фон ячеек: `#1a1a1a`
- Границы: `#2a2a2a` и `#252525`
- Эффект hover для лучшей интерактивности

## Дополнительные типы крафтов

### Плавильная печь (Blasting)

```mdx
<CraftingRecipe
  type="blasting"
  ingredient="ancient_debris"
  result="netherite_scrap"
/>
```

### Коптильня (Smoking)

```mdx
<CraftingRecipe
  type="smoking"
  ingredient="raw_chicken"
  result="cooked_chicken"
/>
```

### Костёр (Campfire)

```mdx
<CraftingRecipe
  type="campfire"
  ingredient="raw_cod"
  result="cooked_cod"
/>
```

## Тестовая страница

Полный список примеров доступен на [тестовой странице](/test).
