# DotaFlow API dumps

JSON snapshots from Steam Web API, SteamCMD (`steam-user`), and Dota 2 web datafeed.  
Auto-updated by [DotaFlow](https://dotaflow.com) parsers, published to [github.com/DotaFlow/steam_api_dumps](https://github.com/DotaFlow/steam_api_dumps).

---

## Tree

```
parsing/
├── Dota2/              Steam API + SteamCMD (Dota 2)
│   ├── public/
│   ├── staging/
│   └── experimental/
├── Deadlock/           Steam API + SteamCMD
│   ├── public/
│   └── experimental/
├── CounterStrike2/     Steam API + SteamCMD
│   └── public/
└── web/                dota2.com datafeed + site static mirrors
    ├── abilities/
    ├── heroes/
    ├── items/
    ├── patches/
    ├── other/
    ├── steamEvents/
    └── static/
```

**Path pattern (Steam):** `parsing/{Game}/{env}/{file}`  
`Game` = `Dota2` | `Deadlock` | `CounterStrike2`, `env` = `public` | `staging` | `experimental`.

**Path pattern (web):** `parsing/web/{section}/…` — Dota 2 only.

---

## App IDs

| Game | Env | Steam app ID |
|------|-----|--------------|
| Dota 2 | public | 570 |
| Dota 2 | staging | 2305270 |
| Dota 2 | experimental | 247040 |
| Deadlock | public | 1422450 |
| Deadlock | experimental | 3488080 |
| Counter-Strike 2 | public | 730 |

---

## Steam branches (`Dota2/`, `Deadlock/`, `CounterStrike2/`)

Files in each `{Game}/{env}/` folder. Availability per game:

| File / dir | Dota 2 | Deadlock | CS2 | Notes |
|------------|:------:|:--------:|:---:|-------|
| `GetClientVersion.json` | ✓ | ✓ | — | `IGCVersion_*/GetClientVersion` |
| `GetServerVersion.json` | ✓ | ✓ | — | `IGCVersion_*/GetServerVersion` |
| `GetHeroes.json` | ✓ | — | — | `IEconDOTA2_*/GetHeroes` |
| `GetStoreMetaData.json` | ✓ | — | ✓ | `IEconItems_*/GetStoreMetaData` |
| `GetAssetPrices.json` | public | — | public | `ISteamEconomy/GetAssetPrices` |
| `GetSDRConfig.json` | public | public | public | `ISteamApps/GetSDRConfig` |
| `GetAssetClassInfo/` | ✓ | — | ✓ | one file per class: `asset{classId}.json` |
| `_SteamAppInfo.json` | ✓ | ✓ | ✓ | SteamCMD `app_info_print` dump |
| `_VersionsHistory.json` | ✓ | ✓ | — | append-only client version changelog (derived) |
| `cvarlist/` | public | — | — | parsed console variable lists |

`GetClientVersion` / `GetServerVersion` / `_VersionsHistory` — Dota 2 and Deadlock only.  
CS2 and economy files — public env only where marked.

---

## Web branch (`web/`)

Dota 2 [datafeed](https://www.dota2.com/datafeed/) responses and related assets. Updated by `web_parser` (~hourly).

### Index files (`_*.json`)

| Path | Source |
|------|--------|
| `abilities/_AbilityList.json` | `/datafeed/abilitylist` |
| `heroes/_HeroesList.json` | `/datafeed/herolist` |
| `items/_ItemsList.json` | `/datafeed/itemlist` |
| `items/_NeutralItems.json` | `/datafeed/neutralitems` |
| `patches/_PatchesList.json` | `/datafeed/patchnoteslist` |
| `other/_DotaUniqueUsers.json` | `/datafeed/uniqueusers` |

### Per-entity files

Built from list endpoints + detail fetches:

| Dir | List drives | Detail endpoint | Example file |
|-----|-------------|-----------------|--------------|
| `abilities/` | `_AbilityList.json` | `/datafeed/abilitydata` | `arc_warden_flux.json` |
| `heroes/` | `_HeroesList.json` | `/datafeed/herodata` | `npc_dota_hero_axe.json` |
| `items/` | `_ItemsList.json` | `/datafeed/itemdata` | `item_blink.json` |
| `patches/` | `_PatchesList.json` | `/datafeed/patchnotes` | `7.38.json` |

### `steamEvents/{app_id}/`

Cached Steam partner news (public apps **570**, **730**, **1422450**):

| File | Content |
|------|---------|
| `_News_russian.json` | Full news dump, `lang=russian` |
| `_News_english.json` | Full news dump, `lang=english` |
| `_News_DumpWithValveEmployee.json` | Historical dump with Valve employee metadata |
| `_NewsValveAuthors.txt` | Parsed author names + profile links |

### `static/`

Mirrors of dota2.com frontend bundles (`manifest.js`, `content/*.js`, `content/*.css`) — used for datamine / asset diff tracking.

---

## Conventions

- **`_` prefix** — aggregate or derived file (list, history, app info dump).
- **No prefix** — single entity or raw API response snapshot.
- Bodies are mostly **raw API JSON** as returned by Steam / datafeed; `_VersionsHistory.json` and a few helpers are parser-maintained.
- Files appear/update only when the parser detects a change (diff-based commits).

---

## Links

- Site: [dotaflow.com](https://dotaflow.com)
- Updates: [t.me/dotaflowupdates](https://t.me/dotaflowupdates)
- News / datamine: [t.me/DotaFlowNews](https://t.me/DotaFlowNews)
- Contact: contact@dotaflow.com
