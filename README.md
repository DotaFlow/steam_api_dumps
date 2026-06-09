# [DotaFlow](https://dotaflow.com)

## Folders
### { Dota 2 | Deadlock | Counter-Strike 2 }/{ experimental | public | staging }
- **_VersionsHistory.json**: saved history of APP Client updates (dota2, deadlock)
- **GetClientVersion.json**: latest response from IGCVersion_\*/GetClientVersion steam API (dota2, deadlock)
- **GetServerVersion.json**: latest response from IGCVersion_\*/GetServerVersion steam API (dota2, deadlock)
- **GetHeroes.json**: latest response from IEconDOTA2_\*/GetHeroes steam API (dota2)
- **GetStoreMetaData.json**: latest response from IEconItems_\*/GetStoreMetaData steam API (dota2, cs2)
- **GetAssetPrices.json**: latest response from ISteamEconomy/GetAssetPrices steam API (dota2 public, cs2 public)
- **GetSDRConfig.json**: latest response from ISteamApps/GetSDRConfig steam API (dota2 public, deadlock public, cs2 public)
- **GetAssetClassInfo** dir: parsed assets via GetAssetClassInfo (files asset%classId%.json in folder; dota, cs)
- **_SteamAppInfo.json** latest dump from SteamCMD (app_info_print) (dota, cs; deadlock all apps)
____


___Checked app IDs___
- Dota 2 
- - Experimental - 247040
- - Staging - 2305270
- - Public - 570
- Deadlock 
- - Public - 1422450
- - Experimental - 3488080
- Counter-Strike 2 
- - Public - 730
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
- - **\_NeutralItems.json**: latest response from /datafeed/neutralitems dota2 API
- - ...All items passed through /datafeed/itemdata from the itemlist (**item_blink.json** for example)
____
- #### patches
- - **\_PatchesList.json**: latest response from /datafeed/patchnoteslist dota2 API
- - ...All patches passed through /datafeed/patchnotes from the patchnoteslist (**7.08.json** for example)
____
- #### other
- - **_DotaUniqueUsers.json**: latest response from /datafeed/uniqueusers dota2 API
____
- #### steamEvents (570, 730, 1422450 folders)
- - **\_News\_russian.json**: latest response from ajaxgetpartnereventspageable (all news) for app on russian language
- - **\_News\_english.json**: latest response from ajaxgetpartnereventspageable (all news) for app on russian language
- - **\_News\_DumpWithValveEmployee.json**: saved dump from ajaxgetpartnereventspageable with valve_access_log field (now is deleted), valve authors of news
- - **\_NewsValveAuthors.txt**: parsed valve authors of news with names and links
____

## Links
- Telegram with updates notifications: [t.me/dotaflowupdates](https://t.me/dotaflowupdates)
- Telegram with news/datamine: [t.me/DotaFlowNews](https://t.me/DotaFlowNews)
- Our website: [dotaflow.com](https://dotaflow.com)
- Contact: contact@dotaflow.com