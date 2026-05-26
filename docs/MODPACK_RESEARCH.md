# Modpack Research

Дата проверки: 2026-05-21.

Цель: изучить существующие HBM/tech-сборки и понять, какие идеи можно безопасно перенести в `HBM's TATARIN Edition` для онлайн-сервера.

## Evaluation Rules

Для нашего сервера важны не только моды, но и возможность стабильно запустить dedicated server:

1. База должна быть совместима с Minecraft `1.12.2` + Forge.
2. Клиентские моды не должны попадать в server pack.
3. Worldgen-моды фиксируются до старта публичного мира.
4. Квесты, CraftTweaker/scripts и configs должны быть синхронизированы между сервером и клиентом.
5. HBM-аддоны допускаются только если явно совместимы с NTM:CE.
6. Тяжелые tech/magic/space-моды берем только после HBM CE boot-test.

## Techmadness

Source: Minecraft Inside, `Techmadness [1.12.2]`.

### Observed Mod Themes

Основные моды:

- `IC2` + addons
- `Mekanism` + addons
- `NuclearCraft`
- `HBM Nuclear Tech`
- `Applied Energistics 2`
- `Draconic Evolution`
- `Galacticraft` + addons
- `FTB Quests`
- `Thermal` family

Вспомогательные моды:

- `The One Probe`
- `JEI`
- `Reap`
- `JourneyMap`
- `Phosphor`
- `Inventory Tweaks`
- `CraftTweaker`
- `Chisel`
- `Controlling`
- `OptiFine`
- `TATW`
- `Uncrafting Table`
- `Iron Backpacks`
- `FoamFix`
- `BetterFps`
- `NoFog`
- `Item Filters`

### What We Can Reuse

| Idea | Decision | Notes |
| --- | --- | --- |
| `Mekanism` alongside HBM | keep | User research confirms compatibility; still watch progression balance. |
| `AE2` | keep | Strong late-game storage and automation. |
| `Thermal` family | candidate | Useful logistics/power ecosystem, but can flatten HBM progression. |
| `FTB Quests` | candidate | Useful if we build guided progression. Requires server/client config discipline. |
| `CraftTweaker` | candidate | Useful for balancing recipes after the base mod list stabilizes. |
| `Chisel` | optional | Nice building mod, low gameplay risk. |
| `Item Filters` | candidate | Usually needed by quest/filter systems. |
| `Phosphor`, `FoamFix`, `BetterFps` | candidate | Optimization ideas, but test one stack at a time. |

### What Not To Copy Directly

| Mod / Pattern | Reason |
| --- | --- |
| Full Techmadness stack | Too large for a small server and hard to debug. |
| `OptiFine` in server plan | Client-only; never put in dedicated server mods. |
| `JourneyMap` in server plan | Client-only for our current plan. |
| `NoFog` | Client-only cosmetic. |
| `Draconic Evolution` | Very high power creep; can trivialize HBM progression. |
| `NuclearCraft` | Nuclear overlap with HBM; only consider if we intentionally want parallel nuclear systems. |
| `Galacticraft + ExtraPlanets` | Heavy worldgen/dimension stack; test much later. |
| `IC2 + addons` | Adds another full tech progression; defer until HBM + Mekanism balance is clear. |
| `Uncrafting Table` | Can create dupe/balance problems in tech packs. |

### Server Notes

Techmadness depends on `scripts` and `config` folders, according to user comments on the page. That means it is not just a mods-folder reference: its progression likely depends on CraftTweaker/config changes. Copying only mod names would not reproduce the intended balance.

For our server, Techmadness is a source of candidate ideas, not a base pack.

## NTM Standard Pack

Source: CurseForge `NTM Standard Pack`.

This is the strongest reference for our direction because it is explicitly built around:

- `NTM:CE`
- `NTM Space`
- multiplayer viability
- quests
- coherent progression
- server use

The pack description mentions integration of:

- `AE2`
- `OpenComputers`
- `SFM`
- `MCHeliCE`
- `Warforge Remaintained`
- NTM Space Addon
- large CraftTweaker/recipe changes

### What We Can Reuse

| Idea | Decision | Notes |
| --- | --- | --- |
| `NTM CE + NTM Space` test profile | useful | Confirms CE Space is a real CE-compatible direction, but not for boot profile. |
| Quest-guided progression | candidate | Good for teaching HBM, but requires maintenance. |
| AE2 recipe rebalance | later | Useful if AE2 becomes too easy relative to HBM. |
| OpenComputers | candidate | Strong automation theme, server-compatible. |
| SFM | candidate | Useful factory automation if stable on server. |
| MCHeliCE / Warforge | optional | Combat/vehicles can fit warfare servers, but add client/server complexity. |

### Cautions

- The pack uses heavy recipe changes; do not copy mod list without scripts.
- It mentions Java 25 in its own pack template. Our baseline remains Java 8 for Forge `1.12.2` boot-test unless we intentionally move to a Cleanroom/modern-Java path later.
- It is a curated pack with in-house mods/resources. We should treat it as design inspiration, not as a dependency source.

## NukclearTek Server

Source: Planet Minecraft server listing.

This is a useful minimal real-server reference. Required join mods listed:

- Forge `1.12.2`
- `Chat Censor`
- `Immersive Vehicles`
- Immersive Vehicles official content pack
- `HBM Nuclear Tech Mod: Community Edition`

### Takeaways

| Idea | Decision | Notes |
| --- | --- | --- |
| Minimal HBM CE server is viable | supports our boot plan | Confirms a small HBM CE server does not need a massive tech stack. |
| `Immersive Vehicles` | optional | Could fit warfare/transport, but not needed for first phase. |
| Chat moderation mod | optional | Only needed for public server. |

## HBM Hamster Reloaded Modpack

Source: 9Minecraft mirror page.

This is based on `Hbm's Nuclear Tech - Hamster Reloaded`, not NTM:CE. It is useful only as a general HBM survival reference.

Not a direct source for our pack because:

- different HBM fork;
- OptiFine is listed as required;
- server files are mirror-hosted;
- not aligned with NTM:CE addon policy.

## Nuclear Tech New Horizons

Source: CurseForge.

This is a `1.7.10` Forge pack inspired by GT:NH and NT:I. It is multiplayer/quest/tech focused, but not directly compatible with our `1.12.2` CE plan.

Useful as a design reference for:

- quest-based onboarding;
- long progression;
- strict recipe gating.

Not useful as a mod list source for the current server.

## Proposed Additions To Our Candidate Pool

These are not automatically accepted into the main pack. They are candidates discovered from existing packs:

| Mod | Side | Status | Reason |
| --- | --- | --- | --- |
| `FTB Quests` | client + server | candidate | Guided HBM onboarding. |
| `CraftTweaker` | client + server | candidate | Recipe balancing and progression control. |
| `Chisel` | client + server | optional | Building/decorative support. |
| `Item Filters` | client + server | candidate | Often needed by quests/filtering systems. |
| `OpenComputers` | client + server | candidate | Advanced automation, seen in NTM Standard Pack. |
| `SFM` | client + server | candidate | Factory automation, seen in NTM Standard Pack. |
| `MCHeliCE` | client + server | optional | Vehicles/combat; test only if server theme needs it. |
| `Warforge Remaintained` | client + server | optional | Warfare content; likely too much for early server. |
| `IC2` | client + server | deferred | Another full tech stack; wait until HBM + Mekanism is stable. |
| `NuclearCraft` | client + server | deferred | Nuclear overlap with HBM. |
| `Draconic Evolution` | client + server | rejected for now | High power creep. |
| `Uncrafting Table` | client + server | rejected for now | Balance/dupe risk. |

## Current Recommendation

For online play, keep our current plan small:

1. HBM CE boot profile.
2. Add QoL and diagnostics.
3. Add Mekanism, Pam's HarvestCraft, Cooking for Blockheads, Spice of Life: Carrot Edition.
4. Add AE2 and Storage Drawers.
5. Add FTB Quests, FTB Library and Item Filters for guided progression.
6. Add CraftTweaker scripts only for concrete balance/recipe problems.
7. Only after that test CE Space, ModTweaker and larger automation mods.

Techmadness supports our inclusion of `Mekanism`, `AE2`, `Thermal`, `Phosphor`, `FoamFix`, `BetterFps`, `CraftTweaker` and questing ideas, but it is too broad to use as-is.

NTM Standard Pack is the best CE-specific design reference, especially for `NTM Space`, quests and multiplayer progression.
