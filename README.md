# [DotaFlow](https://dotaflow.online)

## Folders
### { Dota 2 | Deadlock }/{ experimental | public | staging }
- **_VersionsHistory.json**: saved history of APP Client updates (dota2, deadlock)
- **GetClientVersion.json**: latest response from IGCVersion_\*/GetClientVersion steam API (dota2, deadlock)
- **GetServerVersion.json**: latest response from IGCVersion_\*/GetServerVersion steam API (dota2, deadlock)
- **GetHeroes.json**: latest response from IEconDOTA2_\*/GetHeroes steam API (dota2)
- **GetStoreMetaData.json**: latest response from IEconItems_\*/GetStoreMetaData steam API (dota2)
- **GetAssetPrices.json**: latest response from ISteamEconomy/GetAssetPrices steam API (dota2, only for public 570)
- **GetSDRConfig.json**: latest response from ISteamApps/GetSDRConfig steam API (for all dota apps, but response is same)
____
- - ___Checked app IDs___
- - - Dota 2 Experimental - 247040
- - - Dota 2 Staging - 2305270
- - - Dota 2 Public - 570
- - - Deadlock Public - 1422450
- - - Deadlock Experimental - 3488080
____
### web
- #### abilities
- - **\_AbilityList.json**: latest response from /datafeed/abilitylist dota2 API
- - ...All abilities passed through /datafeed/abilitydata from the abilitylist (**arc_warden_flux.json** for example)
____
- #### heroes
- - **\_HeroesList.json**: latest response from /datafeed/herolist dota2 API
- - ...All heroes passed through /datafeed/herodata from the herolist (**npc_dota_hero_axe.json** for example)
____
- #### items
- - **\_ItemsList.json**: latest response from /datafeed/itemlist dota2 API
- - ...All items passed through /datafeed/itemdata from the itemlist (**item_blink.json** for example)
____
- #### patches
- - **\_PatchesList.json**: latest response from /datafeed/patchnoteslist dota2 API
- - ...All patches passed through /datafeed/patchnotes from the patchnoteslist (**7.08.json** for example)
____
- #### other
- - **_DotaUniqueUsers.json**: latest response from /datafeed/uniqueusers dota2 API
____
- #### steamEvents
- - **\_News%app_id%\_%language%.json**: all steam news events for cs, dota and deadlock apps (files for two languages: russian, english)
____

## Links
- Telegram with updates notifications: [t.me/dotaflowupdates](https://t.me/dotaflowupdates)
- Telegram with news/datamine: [t.me/DotaFlowNews](https://t.me/DotaFlowNews)
- Our website: [dotaflow.online](https://dotaflow.online)
- Contact: contact@dotaflow.online (or [t.me/notrenuit](https://t.me/notrenuit) for some private staff)