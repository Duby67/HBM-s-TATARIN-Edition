# Quest And Progression Plan

Цель: взять полезное из Techmadness, NTM Standard Pack и других HBM/tech-сборок, но сохранить сборку пригодной для маленького dedicated server.

## Selected Quest Stack

| Mod | Side | Status | Purpose |
| --- | --- | --- | --- |
| `FTB Quests` | client + server | selected | Основной quest book. |
| `FTB Library` | client + server | required dependency | Библиотека для FTB Quests на `1.12.2`. |
| `Item Filters` | client + server | required dependency | Фильтры предметов для FTB Quests и задач на группы предметов. |
| `CraftTweaker` | client + server | selected after base boot | Скрипты рецептов и баланс прогрессии. |
| `ModTweaker` | client + server | candidate | Интеграции CraftTweaker с модовыми машинами. Добавлять только когда появятся конкретные рецепты для машин. |

Не берем `Better Questing` как основную систему: в референсах для `1.12.2` чаще встречается FTB Quests, а NTM Standard Pack и Techmadness дают нам направление именно в сторону FTB-style questing.

## Server Rules

1. Quest configs должны быть одинаковыми у клиента и сервера.
2. CraftTweaker scripts должны быть одинаковыми у клиента и сервера.
3. Квесты не должны требовать client-only предметы или команды.
4. Награды не должны выдавать endgame HBM/Mekanism предметы раньше прогрессии.
5. Командные rewards отключать или использовать только после проверки на dedicated server.
6. Все quest/script изменения версионировать в git.

## Proposed Quest Chapters

| Chapter | Goal | Example Tasks |
| --- | --- | --- |
| 0. Bootcamp | Объяснить правила сервера и базовые инструменты | Прочитать intro, получить стартовую книгу/еду, найти укрытие. |
| 1. Survival And Food | Ввести Pam's HarvestCraft, Cooking for Blockheads и SolCarrot | Собрать первые культуры, приготовить блюда, получить первые бонусные сердца. |
| 2. Mining And Radiation Safety | Подвести к HBM без резкого скачка сложности | Добыть базовые руды, собрать защиту, объяснить радиацию и опасные предметы. |
| 3. HBM Early Industry | Первые HBM машины и материалы | Базовая переработка, ранние генераторы, первые компоненты. |
| 4. Mekanism Integration | Ввести Mekanism как параллельную инженерную ветку | Осмий, базовые Mekanism machines, кабели, energy bridge rules. |
| 5. Storage And Logistics | AE2, Storage Drawers, Iron Chests | Drawer wall, первые ME-компоненты, базовая автоматизация. |
| 6. Power And Automation | Стабильная энергия и factory loops | HBM/Mekanism energy production, автоматизация переработки. |
| 7. Advanced HBM | Реакторы, опасные материалы, high-tier crafting | Контролируемые milestones вместо бесплатных rewards. |
| 8. Optional Space | CE Space только после отдельного теста | MixinBooter, NTM Space, gated dimension progression. |

## Reward Policy

Разрешенные награды:

- еда;
- базовые материалы;
- небольшие currency-like items, если позже появится экономика внутри квестов;
- одноразовые QoL-предметы низкого уровня;
- декоративные блоки;
- loot crates только с прозрачным loot table.

Запрещенные награды:

- HBM weapons/nukes;
- высокоуровневые Mekanism machines;
- AE2 controllers, drives и rare components в early game;
- creative-only items;
- предметы, которые обходят gated recipes;
- случайные rewards, способные сломать баланс.

## CraftTweaker Policy

Скрипты добавляем только для реальных проблем:

1. Конфликт рецептов.
2. Слишком ранний доступ к сильной машине.
3. Слишком дешевый energy/power path.
4. Интеграция HBM + Mekanism + AE2.
5. Quest gating, если простых квестовых условий недостаточно.

Не переписываем рецепты заранее. Сначала запускаем сборку, смотрим реальные конфликты и только потом правим scripts.

## Files

Планируемая структура:

```text
profiles/common/config/ftbquests/
  .gitkeep
profiles/common/scripts/
  .gitkeep
```

При сборке server/client pack эти каталоги должны копироваться в соответствующие runtime-профили.
