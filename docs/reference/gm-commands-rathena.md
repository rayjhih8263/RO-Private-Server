# Complete rAthena GM command reference / 完整 GM 指令參考

[繁體中文操作手冊](../08-gm-commands.md) | [English guide](../en/08-gm-commands.md)

Copyright (C) 2017 rAthena Development Team. Help text and aliases are adapted from `conf/atcommands.yml`, licensed GPL-3.0-or-later. This formatted derivative is also GPL-3.0-or-later; see [notice](README.md) and [GPL text](GPL-3.0.txt). Formatting changes: alphabetic index, one section per command, aliases and folded help blocks. Original wording is retained.

Source revision: `d4b8e7b8f16061cc2496d377ac8f777ce72a4f39`. This is a source reference, not a guarantee of permissions or client support on a particular server. Custom C++ and script commands are outside this list.

313 registered names; 97 configured aliases. The upstream YAML has a duplicate `refineui` entry; the last entry is used here, matching its identical help.

## Index / 指令索引

| Command / 指令 | Aliases / 別名 | Help / 查詢 |
| --- | --- | --- |
| [@accept](#cmd-accept) | — | `@help accept` |
| [@accinfo](#cmd-accinfo) | `@accountinfo` | `@help accinfo` |
| [@addfame](#cmd-addfame) | `@famepoint`, `@famepoints` | `@help addfame` |
| [@addperm](#cmd-addperm) | — | `@help addperm` |
| [@addwarp](#cmd-addwarp) | — | `@help addwarp` |
| [@adjgroup](#cmd-adjgroup) | — | `@help adjgroup` |
| [@adopt](#cmd-adopt) | — | `@help adopt` |
| [@agi](#cmd-agi) | — | `@help agi` |
| [@agitend](#cmd-agitend) | — | `@help agitend` |
| [@agitend2](#cmd-agitend2) | — | `@help agitend2` |
| [@agitend3](#cmd-agitend3) | — | `@help agitend3` |
| [@agitstart](#cmd-agitstart) | — | `@help agitstart` |
| [@agitstart2](#cmd-agitstart2) | — | `@help agitstart2` |
| [@agitstart3](#cmd-agitstart3) | — | `@help agitstart3` |
| [@alive](#cmd-alive) | — | `@help alive` |
| [@allowks](#cmd-allowks) | — | `@help allowks` |
| [@allskill](#cmd-allskill) | `@allskills`, `@skillall`, `@skillsall` | `@help allskill` |
| [@auction](#cmd-auction) | — | `@help auction` |
| [@autoloot](#cmd-autoloot) | — | `@help autoloot` |
| [@autolootitem](#cmd-autolootitem) | `@alootid` | `@help autolootitem` |
| [@autoloottype](#cmd-autoloottype) | `@aloottype` | `@help autoloottype` |
| [@autotrade](#cmd-autotrade) | `@at` | `@help autotrade` |
| [@ban](#cmd-ban) | `@banish` | `@help ban` |
| [@baselevelup](#cmd-baselevelup) | `@baselevel`, `@baselvl`, `@baselvup`, `@baselvlup`, `@blevel`, `@blvl`, `@lvup` | `@help baselevelup` |
| [@bodystyle](#cmd-bodystyle) | — | `@help bodystyle` |
| [@breakguild](#cmd-breakguild) | — | `@help breakguild` |
| [@broadcast](#cmd-broadcast) | — | `@help broadcast` |
| [@camerainfo](#cmd-camerainfo) | `@viewpointvalue`, `@setcamera` | `@help camerainfo` |
| [@cart](#cmd-cart) | — | `@help cart` |
| [@cartlist](#cmd-cartlist) | — | `@help cartlist` |
| [@cash](#cmd-cash) | — | `@help cash` |
| [@changecharsex](#cmd-changecharsex) | — | `@help changecharsex` |
| [@changedress](#cmd-changedress) | `@nocosplay` | `@help changedress` |
| [@changegm](#cmd-changegm) | — | `@help changegm` |
| [@changeleader](#cmd-changeleader) | — | `@help changeleader` |
| [@changelook](#cmd-changelook) | — | `@help changelook` |
| [@changesex](#cmd-changesex) | — | `@help changesex` |
| [@channel](#cmd-channel) | `@main` | `@help channel` |
| [@char_ban](#cmd-char_ban) | `@charban` | `@help char_ban` |
| [@char_block](#cmd-char_block) | `@block` | `@help char_block` |
| [@char_unban](#cmd-char_unban) | `@charunban` | `@help char_unban` |
| [@char_unblock](#cmd-char_unblock) | `@unblock` | `@help char_unblock` |
| [@charcommands](#cmd-charcommands) | — | `@help charcommands` |
| [@checkquest](#cmd-checkquest) | — | `@help checkquest` |
| [@clanspy](#cmd-clanspy) | — | `@help clanspy` |
| [@cleanarea](#cmd-cleanarea) | `@cleararea` | `@help cleanarea` |
| [@cleanmap](#cmd-cleanmap) | `@clearmap` | `@help cleanmap` |
| [@clearcart](#cmd-clearcart) | — | `@help clearcart` |
| [@cleargstorage](#cmd-cleargstorage) | — | `@help cleargstorage` |
| [@clearstorage](#cmd-clearstorage) | — | `@help clearstorage` |
| [@clearweather](#cmd-clearweather) | — | `@help clearweather` |
| [@clone](#cmd-clone) | — | `@help clone` |
| [@cloneequip](#cmd-cloneequip) | `@eqclone` | `@help cloneequip` |
| [@clonestat](#cmd-clonestat) | `@stclone` | `@help clonestat` |
| [@clouds](#cmd-clouds) | — | `@help clouds` |
| [@clouds2](#cmd-clouds2) | — | `@help clouds2` |
| [@commands](#cmd-commands) | — | `@help commands` |
| [@completequest](#cmd-completequest) | — | `@help completequest` |
| [@con](#cmd-con) | — | `@help con` |
| [@costume](#cmd-costume) | — | `@help costume` |
| [@crt](#cmd-crt) | — | `@help crt` |
| [@day](#cmd-day) | — | `@help day` |
| [@delitem](#cmd-delitem) | — | `@help delitem` |
| [@dex](#cmd-dex) | — | `@help dex` |
| [@disguise](#cmd-disguise) | — | `@help disguise` |
| [@disguiseall](#cmd-disguiseall) | — | `@help disguiseall` |
| [@disguiseguild](#cmd-disguiseguild) | — | `@help disguiseguild` |
| [@displayskill](#cmd-displayskill) | — | `@help displayskill` |
| [@displayskillcast](#cmd-displayskillcast) | — | `@help displayskillcast` |
| [@displayskillunit](#cmd-displayskillunit) | — | `@help displayskillunit` |
| [@displaystatus](#cmd-displaystatus) | — | `@help displaystatus` |
| [@divorce](#cmd-divorce) | — | `@help divorce` |
| [@doom](#cmd-doom) | — | `@help doom` |
| [@doommap](#cmd-doommap) | — | `@help doommap` |
| [@dropall](#cmd-dropall) | — | `@help dropall` |
| [@duel](#cmd-duel) | — | `@help duel` |
| [@dye](#cmd-dye) | `@ccolor` | `@help dye` |
| [@effect](#cmd-effect) | — | `@help effect` |
| [@email](#cmd-email) | — | `@help email` |
| [@enchantgradeui](#cmd-enchantgradeui) | — | `@help enchantgradeui` |
| [@erasequest](#cmd-erasequest) | — | `@help erasequest` |
| [@evilclone](#cmd-evilclone) | — | `@help evilclone` |
| [@exp](#cmd-exp) | — | `@help exp` |
| [@fakename](#cmd-fakename) | — | `@help fakename` |
| [@feelreset](#cmd-feelreset) | — | `@help feelreset` |
| [@fireworks](#cmd-fireworks) | — | `@help fireworks` |
| [@fog](#cmd-fog) | — | `@help fog` |
| [@follow](#cmd-follow) | — | `@help follow` |
| [@font](#cmd-font) | — | `@help font` |
| [@fontcolor](#cmd-fontcolor) | — | `@help fontcolor` |
| [@fullstrip](#cmd-fullstrip) | — | `@help fullstrip` |
| [@gat](#cmd-gat) | — | `@help gat` |
| [@gmotd](#cmd-gmotd) | — | `@help gmotd` |
| [@go](#cmd-go) | — | `@help go` |
| [@grade](#cmd-grade) | — | `@help grade` |
| [@guild](#cmd-guild) | — | `@help guild` |
| [@guildlevelup](#cmd-guildlevelup) | `@glevel`, `@glvl`, `@guildlevel`, `@guildlvl`, `@guildlvlup`, `@guildlvup` | `@help guildlevelup` |
| [@guildrecall](#cmd-guildrecall) | — | `@help guildrecall` |
| [@guildspy](#cmd-guildspy) | — | `@help guildspy` |
| [@guildstorage](#cmd-guildstorage) | `@gstorage` | `@help guildstorage` |
| [@gvgoff](#cmd-gvgoff) | `@gpvpoff` | `@help gvgoff` |
| [@gvgon](#cmd-gvgon) | `@gpvpon` | `@help gvgon` |
| [@hair_color](#cmd-hair_color) | `@haircolor`, `@hcolor` | `@help hair_color` |
| [@hair_style](#cmd-hair_style) | `@hairstyle`, `@hstyle` | `@help hair_style` |
| [@hatch](#cmd-hatch) | — | `@help hatch` |
| [@hatereset](#cmd-hatereset) | — | `@help hatereset` |
| [@heal](#cmd-heal) | — | `@help heal` |
| [@healap](#cmd-healap) | — | `@help healap` |
| [@help](#cmd-help) | `@h` | `@help help` |
| [@hide](#cmd-hide) | — | `@help hide` |
| [@hidenpc](#cmd-hidenpc) | — | `@help hidenpc` |
| [@homevolution](#cmd-homevolution) | `@homevolve` | `@help homevolution` |
| [@homfriendly](#cmd-homfriendly) | — | `@help homfriendly` |
| [@homhungry](#cmd-homhungry) | — | `@help homhungry` |
| [@hominfo](#cmd-hominfo) | — | `@help hominfo` |
| [@homlevel](#cmd-homlevel) | `@hlvl`, `@hlevel`, `@homlvl`, `@homlvup` | `@help homlevel` |
| [@hommutate](#cmd-hommutate) | — | `@help hommutate` |
| [@homshuffle](#cmd-homshuffle) | — | `@help homshuffle` |
| [@homstats](#cmd-homstats) | — | `@help homstats` |
| [@homtalk](#cmd-homtalk) | — | `@help homtalk` |
| [@identify](#cmd-identify) | — | `@help identify` |
| [@identifyall](#cmd-identifyall) | — | `@help identifyall` |
| [@idsearch](#cmd-idsearch) | — | `@help idsearch` |
| [@int](#cmd-int) | — | `@help int` |
| [@invite](#cmd-invite) | — | `@help invite` |
| [@item](#cmd-item) | — | `@help item` |
| [@item2](#cmd-item2) | — | `@help item2` |
| [@itembound](#cmd-itembound) | — | `@help itembound` |
| [@itembound2](#cmd-itembound2) | — | `@help itembound2` |
| [@iteminfo](#cmd-iteminfo) | `@ii` | `@help iteminfo` |
| [@itemlist](#cmd-itemlist) | `@inventorylist` | `@help itemlist` |
| [@itemreset](#cmd-itemreset) | `@clearinventory` | `@help itemreset` |
| [@jail](#cmd-jail) | — | `@help jail` |
| [@jailfor](#cmd-jailfor) | — | `@help jailfor` |
| [@jailtime](#cmd-jailtime) | — | `@help jailtime` |
| [@jobchange](#cmd-jobchange) | `@job` | `@help jobchange` |
| [@joblevelup](#cmd-joblevelup) | `@jlevel`, `@jlvl`, `@joblevel`, `@joblvl`, `@joblvlup`, `@joblvup` | `@help joblevelup` |
| [@join](#cmd-join) | — | `@help join` |
| [@jump](#cmd-jump) | — | `@help jump` |
| [@jumpto](#cmd-jumpto) | `@goto`, `@warpto` | `@help jumpto` |
| [@kami](#cmd-kami) | — | `@help kami` |
| [@kamib](#cmd-kamib) | — | `@help kamib` |
| [@kamic](#cmd-kamic) | — | `@help kamic` |
| [@kick](#cmd-kick) | — | `@help kick` |
| [@kickall](#cmd-kickall) | — | `@help kickall` |
| [@kill](#cmd-kill) | `@die` | `@help kill` |
| [@killable](#cmd-killable) | — | `@help killable` |
| [@killer](#cmd-killer) | — | `@help killer` |
| [@killmonster](#cmd-killmonster) | — | `@help killmonster` |
| [@killmonster2](#cmd-killmonster2) | — | `@help killmonster2` |
| [@ksprotection](#cmd-ksprotection) | `@noks` | `@help ksprotection` |
| [@langtype](#cmd-langtype) | — | `@help langtype` |
| [@leave](#cmd-leave) | — | `@help leave` |
| [@leaves](#cmd-leaves) | — | `@help leaves` |
| [@limitedsale](#cmd-limitedsale) | — | `@help limitedsale` |
| [@lkami](#cmd-lkami) | — | `@help lkami` |
| [@load](#cmd-load) | `@return` | `@help load` |
| [@loadnpc](#cmd-loadnpc) | — | `@help loadnpc` |
| [@localbroadcast](#cmd-localbroadcast) | — | `@help localbroadcast` |
| [@lostskill](#cmd-lostskill) | — | `@help lostskill` |
| [@luk](#cmd-luk) | — | `@help luk` |
| [@macrochecker](#cmd-macrochecker) | — | `@help macrochecker` |
| [@mail](#cmd-mail) | — | `@help mail` |
| [@makeegg](#cmd-makeegg) | — | `@help makeegg` |
| [@makehomun](#cmd-makehomun) | — | `@help makehomun` |
| [@mapexit](#cmd-mapexit) | — | `@help mapexit` |
| [@mapflag](#cmd-mapflag) | — | `@help mapflag` |
| [@mapinfo](#cmd-mapinfo) | — | `@help mapinfo` |
| [@mapmove](#cmd-mapmove) | `@rura`, `@warp` | `@help mapmove` |
| [@marry](#cmd-marry) | — | `@help marry` |
| [@me](#cmd-me) | — | `@help me` |
| [@memo](#cmd-memo) | — | `@help memo` |
| [@misceffect](#cmd-misceffect) | — | `@help misceffect` |
| [@mobinfo](#cmd-mobinfo) | `@monsterinfo`, `@mi` | `@help mobinfo` |
| [@mobsearch](#cmd-mobsearch) | — | `@help mobsearch` |
| [@model](#cmd-model) | — | `@help model` |
| [@monster](#cmd-monster) | `@spawn` | `@help monster` |
| [@monsterbig](#cmd-monsterbig) | — | `@help monsterbig` |
| [@monsterignore](#cmd-monsterignore) | `@battleignore` | `@help monsterignore` |
| [@monstersmall](#cmd-monstersmall) | — | `@help monstersmall` |
| [@mount2](#cmd-mount2) | — | `@help mount2` |
| [@mount_peco](#cmd-mount_peco) | `@mount`, `@mountpeco` | `@help mount_peco` |
| [@mute](#cmd-mute) | — | `@help mute` |
| [@mutearea](#cmd-mutearea) | `@stfu` | `@help mutearea` |
| [@night](#cmd-night) | — | `@help night` |
| [@noask](#cmd-noask) | — | `@help noask` |
| [@npcmove](#cmd-npcmove) | — | `@help npcmove` |
| [@npctalk](#cmd-npctalk) | `@npctalkc` | `@help npctalk` |
| [@nuke](#cmd-nuke) | — | `@help nuke` |
| [@option](#cmd-option) | — | `@help option` |
| [@party](#cmd-party) | — | `@help party` |
| [@partyoption](#cmd-partyoption) | — | `@help partyoption` |
| [@partyrecall](#cmd-partyrecall) | — | `@help partyrecall` |
| [@partysharelvl](#cmd-partysharelvl) | — | `@help partysharelvl` |
| [@partyspy](#cmd-partyspy) | — | `@help partyspy` |
| [@petfriendly](#cmd-petfriendly) | — | `@help petfriendly` |
| [@pethungry](#cmd-pethungry) | — | `@help pethungry` |
| [@petrename](#cmd-petrename) | — | `@help petrename` |
| [@pettalk](#cmd-pettalk) | — | `@help pettalk` |
| [@points](#cmd-points) | — | `@help points` |
| [@pow](#cmd-pow) | — | `@help pow` |
| [@produce](#cmd-produce) | — | `@help produce` |
| [@pvpoff](#cmd-pvpoff) | — | `@help pvpoff` |
| [@pvpon](#cmd-pvpon) | — | `@help pvpon` |
| [@questskill](#cmd-questskill) | — | `@help questskill` |
| [@raise](#cmd-raise) | `@revive` | `@help raise` |
| [@raisemap](#cmd-raisemap) | — | `@help raisemap` |
| [@rates](#cmd-rates) | — | `@help rates` |
| [@recall](#cmd-recall) | — | `@help recall` |
| [@recallall](#cmd-recallall) | — | `@help recallall` |
| [@refine](#cmd-refine) | — | `@help refine` |
| [@refineui](#cmd-refineui) | — | `@help refineui` |
| [@refresh](#cmd-refresh) | — | `@help refresh` |
| [@refreshall](#cmd-refreshall) | — | `@help refreshall` |
| [@reject](#cmd-reject) | — | `@help reject` |
| [@reload](#cmd-reload) | — | `@help reload` |
| [@reloadachievementdb](#cmd-reloadachievementdb) | — | `@help reloadachievementdb` |
| [@reloadatcommand](#cmd-reloadatcommand) | — | `@help reloadatcommand` |
| [@reloadattendancedb](#cmd-reloadattendancedb) | — | `@help reloadattendancedb` |
| [@reloadbarterdb](#cmd-reloadbarterdb) | — | `@help reloadbarterdb` |
| [@reloadbattleconf](#cmd-reloadbattleconf) | — | `@help reloadbattleconf` |
| [@reloadcashdb](#cmd-reloadcashdb) | `@reloadcashshop` | `@help reloadcashdb` |
| [@reloadinstancedb](#cmd-reloadinstancedb) | — | `@help reloadinstancedb` |
| [@reloaditemdb](#cmd-reloaditemdb) | — | `@help reloaditemdb` |
| [@reloadlogconf](#cmd-reloadlogconf) | — | `@help reloadlogconf` |
| [@reloadmobdb](#cmd-reloadmobdb) | — | `@help reloadmobdb` |
| [@reloadmotd](#cmd-reloadmotd) | — | `@help reloadmotd` |
| [@reloadmsgconf](#cmd-reloadmsgconf) | — | `@help reloadmsgconf` |
| [@reloadnpcfile](#cmd-reloadnpcfile) | `@reloadnpc` | `@help reloadnpcfile` |
| [@reloadpcdb](#cmd-reloadpcdb) | — | `@help reloadpcdb` |
| [@reloadquestdb](#cmd-reloadquestdb) | — | `@help reloadquestdb` |
| [@reloadscript](#cmd-reloadscript) | — | `@help reloadscript` |
| [@reloadskilldb](#cmd-reloadskilldb) | — | `@help reloadskilldb` |
| [@reloadstatusdb](#cmd-reloadstatusdb) | — | `@help reloadstatusdb` |
| [@repairall](#cmd-repairall) | — | `@help repairall` |
| [@request](#cmd-request) | — | `@help request` |
| [@reset](#cmd-reset) | — | `@help reset` |
| [@resetcooltime](#cmd-resetcooltime) | `@resetcooldown` | `@help resetcooltime` |
| [@resetskill](#cmd-resetskill) | `@skreset` | `@help resetskill` |
| [@resetstat](#cmd-resetstat) | `@streset` | `@help resetstat` |
| [@resurrect](#cmd-resurrect) | — | `@help resurrect` |
| [@rmvperm](#cmd-rmvperm) | — | `@help rmvperm` |
| [@roulette](#cmd-roulette) | — | `@help roulette` |
| [@sakura](#cmd-sakura) | — | `@help sakura` |
| [@save](#cmd-save) | — | `@help save` |
| [@send](#cmd-send) | — | `@help send` |
| [@servertime](#cmd-servertime) | `@date`, `@serverdate`, `@time` | `@help servertime` |
| [@set](#cmd-set) | — | `@help set` |
| [@setbattleflag](#cmd-setbattleflag) | — | `@help setbattleflag` |
| [@setcard](#cmd-setcard) | — | `@help setcard` |
| [@setquest](#cmd-setquest) | — | `@help setquest` |
| [@showdelay](#cmd-showdelay) | — | `@help showdelay` |
| [@showexp](#cmd-showexp) | — | `@help showexp` |
| [@showmobs](#cmd-showmobs) | — | `@help showmobs` |
| [@shownpc](#cmd-shownpc) | — | `@help shownpc` |
| [@showrate](#cmd-showrate) | — | `@help showrate` |
| [@showzeny](#cmd-showzeny) | — | `@help showzeny` |
| [@size](#cmd-size) | — | `@help size` |
| [@sizeall](#cmd-sizeall) | — | `@help sizeall` |
| [@sizeguild](#cmd-sizeguild) | — | `@help sizeguild` |
| [@skillid](#cmd-skillid) | — | `@help skillid` |
| [@skilloff](#cmd-skilloff) | — | `@help skilloff` |
| [@skillon](#cmd-skillon) | — | `@help skillon` |
| [@skillpoint](#cmd-skillpoint) | `@skpoint` | `@help skillpoint` |
| [@skilltree](#cmd-skilltree) | — | `@help skilltree` |
| [@slaveclone](#cmd-slaveclone) | — | `@help slaveclone` |
| [@snow](#cmd-snow) | — | `@help snow` |
| [@soulball](#cmd-soulball) | — | `@help soulball` |
| [@sound](#cmd-sound) | — | `@help sound` |
| [@speed](#cmd-speed) | — | `@help speed` |
| [@spiritball](#cmd-spiritball) | — | `@help spiritball` |
| [@spl](#cmd-spl) | — | `@help spl` |
| [@sta](#cmd-sta) | — | `@help sta` |
| [@stat_all](#cmd-stat_all) | `@allstat`, `@allstats`, `@statall`, `@statsall` | `@help stat_all` |
| [@stats](#cmd-stats) | — | `@help stats` |
| [@statuspoint](#cmd-statuspoint) | `@stpoint` | `@help statuspoint` |
| [@stockall](#cmd-stockall) | — | `@help stockall` |
| [@storage](#cmd-storage) | — | `@help storage` |
| [@storagelist](#cmd-storagelist) | — | `@help storagelist` |
| [@storeall](#cmd-storeall) | — | `@help storeall` |
| [@str](#cmd-str) | — | `@help str` |
| [@stylist](#cmd-stylist) | — | `@help stylist` |
| [@summon](#cmd-summon) | — | `@help summon` |
| [@tonpc](#cmd-tonpc) | — | `@help tonpc` |
| [@trade](#cmd-trade) | — | `@help trade` |
| [@trait_all](#cmd-trait_all) | `@alltrait`, `@alltraits`, `@traitall`, `@traitsall` | `@help trait_all` |
| [@traitpoint](#cmd-traitpoint) | `@trpoint` | `@help traitpoint` |
| [@unban](#cmd-unban) | `@unbanish` | `@help unban` |
| [@undisguise](#cmd-undisguise) | — | `@help undisguise` |
| [@undisguiseall](#cmd-undisguiseall) | — | `@help undisguiseall` |
| [@undisguiseguild](#cmd-undisguiseguild) | — | `@help undisguiseguild` |
| [@unjail](#cmd-unjail) | `@discharge` | `@help unjail` |
| [@unloadnpc](#cmd-unloadnpc) | — | `@help unloadnpc` |
| [@unloadnpcfile](#cmd-unloadnpcfile) | — | `@help unloadnpcfile` |
| [@unmute](#cmd-unmute) | — | `@help unmute` |
| [@uptime](#cmd-uptime) | — | `@help uptime` |
| [@users](#cmd-users) | — | `@help users` |
| [@useskill](#cmd-useskill) | — | `@help useskill` |
| [@version](#cmd-version) | — | `@help version` |
| [@vip](#cmd-vip) | — | `@help vip` |
| [@vit](#cmd-vit) | — | `@help vit` |
| [@where](#cmd-where) | — | `@help where` |
| [@whereis](#cmd-whereis) | — | `@help whereis` |
| [@who](#cmd-who) | `@whois` | `@help who` |
| [@who2](#cmd-who2) | — | `@help who2` |
| [@who3](#cmd-who3) | — | `@help who3` |
| [@whodrops](#cmd-whodrops) | — | `@help whodrops` |
| [@whogm](#cmd-whogm) | — | `@help whogm` |
| [@whomap](#cmd-whomap) | — | `@help whomap` |
| [@whomap2](#cmd-whomap2) | — | `@help whomap2` |
| [@whomap3](#cmd-whomap3) | — | `@help whomap3` |
| [@wis](#cmd-wis) | — | `@help wis` |
| [@zeny](#cmd-zeny) | — | `@help zeny` |

## Detailed help / 完整參數與用途

English upstream text is preserved below. Params = 參數; required = 必填; optional = 可選.

<a id="cmd-accept"></a>

### @accept

```text
Accepts an invitation to a duel.
```

<a id="cmd-accinfo"></a>

### @accinfo

Aliases / 別名: `@accountinfo`

```text
Params: <char name>. Searches for a character with the name <char name>. You may use % as a placeholder.
Params: <account ID>. Searches login information for the account <account ID>.
Displays basic information about the account with the account ID <account ID> or with the character <char name> on it.
```

<a id="cmd-addfame"></a>

### @addfame

Aliases / 別名: `@famepoint`, `@famepoints`

```text
Params: <amount>.
Adds or reduces the player's fame points by <amount>.
```

<a id="cmd-addperm"></a>

### @addperm

```text
Params: <permission_name>
Temporarily add a permission to a player.
```

<a id="cmd-addwarp"></a>

### @addwarp

```text
Params: <map name> <x coord> <y coord> <NPC name>
```

<a id="cmd-adjgroup"></a>

### @adjgroup

```text
Params: <level> <char name>
Do a temporary adjustment of the group level of a player.
```

<a id="cmd-adopt"></a>

### @adopt

```text
Params: <char name>
Adopts the specified player <char name>.
```

<a id="cmd-agi"></a>

### @agi

```text
Params: <amount>
Raises AGI by given amount.
```

<a id="cmd-agitend"></a>

### @agitend

```text
End War of Emperium
```

<a id="cmd-agitend2"></a>

### @agitend2

```text
End War of Emperium SE
```

<a id="cmd-agitend3"></a>

### @agitend3

```text
End War of Emperium TE
```

<a id="cmd-agitstart"></a>

### @agitstart

```text
Starts War of Emperium
```

<a id="cmd-agitstart2"></a>

### @agitstart2

```text
Starts War of Emperium SE
```

<a id="cmd-agitstart3"></a>

### @agitstart3

```text
Starts War of Emperium TE
```

<a id="cmd-alive"></a>

### @alive

```text
Revives yourself from death.
```

<a id="cmd-allowks"></a>

### @allowks

```text
Enables or disables kill stealing on this map.
```

<a id="cmd-allskill"></a>

### @allskill

Aliases / 別名: `@allskills`, `@skillall`, `@skillsall`

```text
Give you all skills.
```

<a id="cmd-auction"></a>

### @auction

```text
Opens the auction window.
```

<a id="cmd-autoloot"></a>

### @autoloot

```text
Params: <on|off|#>
Makes items go straight into your inventory.
```

<a id="cmd-autolootitem"></a>

### @autolootitem

Aliases / 別名: `@alootid`

```text
Params: None. Shows a short help.
Params: +<Item ID> to add an item ID
Params: -<Item ID> to remove an item ID
Params: reset to remove all item IDs
Makes items of this specific item ID go straight into your inventory.
```

<a id="cmd-autoloottype"></a>

### @autoloottype

Aliases / 別名: `@aloottype`

```text
Params: None. Shows a short help.
Params: +<type name/ID> to add an item type
Params: -<type name/ID> to remove an item type
Params: reset to remove all item types
Makes items of this specific item type go straight into your inventory.
Type List:
  healing = 0, usable = 2, etc = 3, weapon = 4, armor = 5,
  card = 6, petegg = 7, petarmor = 8, ammo = 10
```

<a id="cmd-autotrade"></a>

### @autotrade

Aliases / 別名: `@at`

```text
Allows you to vend while you are offline.
```

<a id="cmd-ban"></a>

### @ban

Aliases / 別名: `@banish`

```text
Params: <time> <name>\n" "Temporarily ban an account.
time usage: adjustment (+/- value) and element (y/a, m, d/j, h, mn, s)
Example: @ban +1m-2mn1s-6y testplayer
```

<a id="cmd-baselevelup"></a>

### @baselevelup

Aliases / 別名: `@baselevel`, `@baselvl`, `@baselvup`, `@baselvlup`, `@blevel`, `@blvl`, `@lvup`

```text
Params: <number of levels>
Raises your base level the desired number of levels.
```

<a id="cmd-bodystyle"></a>

### @bodystyle

```text
Params: <job ID>
Params: off. Restores default job bodystyle.
Changes the character's bodystyle to <job ID>.
```

<a id="cmd-breakguild"></a>

### @breakguild

```text
Breaks the guild of the attached character.
You must be the guildmaster to use this command.
```

<a id="cmd-broadcast"></a>

### @broadcast

```text
Params: <message>
Broadcasts a message with your name (in yellow).
```

<a id="cmd-camerainfo"></a>

### @camerainfo

Aliases / 別名: `@viewpointvalue`, `@setcamera`

```text
Shows or updates the client's camera settings.
```

<a id="cmd-cart"></a>

### @cart

```text
Params: <cart ID>
Gives or removes a cart to a player and also change the cart skin.
Available cart IDs:
    0: remove cart
  1-5: normal carts
  6-9: new carts
```

<a id="cmd-cartlist"></a>

### @cartlist

```text
Displays a list of items in the cart.
```

<a id="cmd-cash"></a>

### @cash

```text
Params: <amount> - Gives you the specified amount of cash points.
```

<a id="cmd-changecharsex"></a>

### @changecharsex

```text
Changes your character's gender.
```

<a id="cmd-changedress"></a>

### @changedress

Aliases / 別名: `@nocosplay`

```text
Removes all character costumes.
```

<a id="cmd-changegm"></a>

### @changegm

```text
Params: <charname>
Changes the leader of your guild (You must be guild leader)
```

<a id="cmd-changeleader"></a>

### @changeleader

```text
Params: <charname>
Changes the leader of your party (You must be party leader)
```

<a id="cmd-changelook"></a>

### @changelook

```text
Params: <position> <view ID>
Changes the player's appearance to the specified view ID.
Available positions:
  1: Top
  2: Middle
  3: Bottom
  4: Weapon
  5: Shield
  6: Shoes
  7: Robe
  8: Bodystyle
```

<a id="cmd-changesex"></a>

### @changesex

```text
Changes your account's gender.
```

<a id="cmd-channel"></a>

### @channel

Aliases / 別名: `@main`

```text
If you run this command without any parameters, you will get a more detailed help information.
```

<a id="cmd-char_ban"></a>

### @char_ban

Aliases / 別名: `@charban`

```text
Params: <time> <name>
Temporarily ban a character.
time usage: adjustment (+/- value) and element (y/a, m, d/j, h, mn, s)
Example: @char_ban +1m-2mn1s-6y testplayer
```

<a id="cmd-char_block"></a>

### @char_block

Aliases / 別名: `@block`

```text
Params: <char name>
Permanently blocks an account.
```

<a id="cmd-char_unban"></a>

### @char_unban

Aliases / 別名: `@charunban`

```text
Params: <name>
Unban a character
```

<a id="cmd-char_unblock"></a>

### @char_unblock

Aliases / 別名: `@unblock`

```text
Params: <char name>
Unblocks an account.
```

<a id="cmd-charcommands"></a>

### @charcommands

```text
Displays a list of charcommands that you can use.
```

<a id="cmd-checkquest"></a>

### @checkquest

```text
Params: <quest ID>
Shows status information for the quest with quest ID <quest ID>.
```

<a id="cmd-clanspy"></a>

### @clanspy

```text
Params: <clan name|id>
You will receive all messages of the clan chat (Chat logging must be enabled)
```

<a id="cmd-cleanarea"></a>

### @cleanarea

Aliases / 別名: `@cleararea`

```text
Deletes floor items in sight range.
```

<a id="cmd-cleanmap"></a>

### @cleanmap

Aliases / 別名: `@clearmap`

```text
Deletes floor items on the current map.
```

<a id="cmd-clearcart"></a>

### @clearcart

```text
Deletes all items in the cart.
```

<a id="cmd-cleargstorage"></a>

### @cleargstorage

```text
Deletes all items in the guild storage.
```

<a id="cmd-clearstorage"></a>

### @clearstorage

```text
Deletes all items in the storage.
```

<a id="cmd-clearweather"></a>

### @clearweather

```text
Stops all weather effects on the current map.
```

<a id="cmd-clone"></a>

### @clone

```text
Params: <charname>
Spawns a supportive clone of the given player.
```

<a id="cmd-cloneequip"></a>

### @cloneequip

Aliases / 別名: `@eqclone`

```text
Params: <char name>
Params: <char ID>
Copies the equipment of player <char name/char ID>.
```

<a id="cmd-clonestat"></a>

### @clonestat

Aliases / 別名: `@stclone`

```text
Params: <char name>
Params: <char ID>
Copies the status values of player <char name/char ID>.
```

<a id="cmd-clouds"></a>

### @clouds

```text
Makes all maps to have the cloudy weather effect.
```

<a id="cmd-clouds2"></a>

### @clouds2

```text
Makes all maps to have another cloudy weather effect.
```

<a id="cmd-commands"></a>

### @commands

```text
Displays a list of atcommands that you can use.
```

<a id="cmd-completequest"></a>

### @completequest

```text
Params: <quest ID>
Completes the quest with quest ID <quest ID>.
```

<a id="cmd-con"></a>

### @con

```text
Params: <amount>
Raises CON by given amount.
```

<a id="cmd-costume"></a>

### @costume

```text
Params: <costume>
Changes the player's visible appearance to that of the selected <costume>.
Available costumes:
  Hanbok
  Oktoberfest
  Summer
  Wedding
  Xmas
```

<a id="cmd-crt"></a>

### @crt

```text
Params: <amount>
Raises CRT by given amount.
```

<a id="cmd-day"></a>

### @day

```text
Disables night mode and restores regular lighting, all characters are affected.
```

<a id="cmd-delitem"></a>

### @delitem

```text
Params: <item name> <amount>
Params: <item ID> <amount>
Deletes <amount> of the specified item <item name/ID> from the player's inventory.
```

<a id="cmd-dex"></a>

### @dex

```text
Params: <amount>
Raises DEX by given amount.
```

<a id="cmd-disguise"></a>

### @disguise

```text
Params: <monster name|ID>
Change your appearence to other players to a mob.
```

<a id="cmd-disguiseall"></a>

### @disguiseall

```text
Params: <monster name|ID>
Disguises all online characters.
```

<a id="cmd-disguiseguild"></a>

### @disguiseguild

```text
Params: <monster name|ID>
Disguises all online characters of a guild.
```

<a id="cmd-displayskill"></a>

### @displayskill

```text
Params: <skill ID> {<skill level>}
Displays the skill animation of a skill without really using the skill.
```

<a id="cmd-displayskillcast"></a>

### @displayskillcast

```text
Params: <skill ID> {<skill level> <ground target flag> <cast time>}
Displays the cast animation of a skill without really casting the skill.
```

<a id="cmd-displayskillunit"></a>

### @displayskillunit

```text
Params: <skill unit ID> {<skill level> <range>}
Displays the skill unit animation of a skill unit without really using the skill.
```

<a id="cmd-displaystatus"></a>

### @displaystatus

```text
Params: <status ID> <flag> <tick> {<val1> <val2> <val3>}
Displays the status animation of a status change without really having the status change.
```

<a id="cmd-divorce"></a>

### @divorce

```text
Divorce player.
```

<a id="cmd-doom"></a>

### @doom

```text
Kills all NON GM chars on the server.
```

<a id="cmd-doommap"></a>

### @doommap

```text
Kills all non GM characters on the map.
```

<a id="cmd-dropall"></a>

### @dropall

```text
Params: [<item type>]
Throws all your possession on the ground. No type specified will drop all items.
```

<a id="cmd-duel"></a>

### @duel

```text
Starts a duel.
```

<a id="cmd-dye"></a>

### @dye

Aliases / 別名: `@ccolor`

```text
Params: <clothes palette no.>
Changes your characters clothes color.
```

<a id="cmd-effect"></a>

### @effect

```text
Params: <effect id> [<flag>]
Give an effect to your character.
```

<a id="cmd-email"></a>

### @email

```text
Params: <current email> <new email>
Changes your account e-mail address.
```

<a id="cmd-enchantgradeui"></a>

### @enchantgradeui

```text
Opens the enchantgrade UI.
```

<a id="cmd-erasequest"></a>

### @erasequest

```text
Params: <quest ID>
Removes the quest <quest ID> from the quest log.
```

<a id="cmd-evilclone"></a>

### @evilclone

```text
Params: <charname>
Spawns an aggressive clone of the given player.
```

<a id="cmd-exp"></a>

### @exp

```text
Displays current levels and % progress.
```

<a id="cmd-fakename"></a>

### @fakename

```text
Params: <name>
Changes your name to your choice temporarily.
```

<a id="cmd-feelreset"></a>

### @feelreset

```text
Resets a Star Gladiator's marked maps.
```

<a id="cmd-fireworks"></a>

### @fireworks

```text
Makes all maps to have the fireworks weather effect.
```

<a id="cmd-fog"></a>

### @fog

```text
Makes all maps to have the fog weather effect.
```

<a id="cmd-follow"></a>

### @follow

```text
Params: <char name>
Follow a player.
```

<a id="cmd-font"></a>

### @font

```text
Params: <type> - value between 0-9
Sets the client font to <type>.
Available types:
  0: Default
  1: RixLoveangel
  2: RixSquirrel
  3: NHCgogo
  4: RixDiary
  5: RixMiniHeart
  6: RixFreshman
  7: RixKid
  8: RixMagic
  9: RixJJangu
```

<a id="cmd-fontcolor"></a>

### @fontcolor

```text
Params: <color_name>
Sets channel chat font color for the invoking character only.
```

<a id="cmd-fullstrip"></a>

### @fullstrip

```text
Params: <char name>
Unequips all items currently equipped by <char name>.
```

<a id="cmd-gat"></a>

### @gat

```text
For debugging (you inspect around gat)
```

<a id="cmd-gmotd"></a>

### @gmotd

```text
Broadcasts the Message of The Day to all players.
```

<a id="cmd-go"></a>

### @go

```text
Params: <city name|number>
Warps you to a city.
-3: (Memo point 2)  14: louyang         31: mora
-2: (Memo point 1)  15: start point     32: dewata
-1: (Memo point 0)  16: prison/jail     33: malangdo island
 0: prontera              17: jawaii             34: malaya port
 1: morocc                18: ayothaya       35: eclage
 2: geffen                  19: einbroch       36: lasagna
 3: payon                  20: lighthalzen
 4: alberta                 21: einbech
 5: izlude                   22: hugel
 6: aldebaran           23: rachel
 7: xmas (lutie)        24: veins
 8: comodo               25: moscovia
 9: yuno                     26: midgard camp
10: amatsu               27: manuk
11: gonryun              28: splendide
12: umbala               29: brasilis
13: niflheim              30: el dicastes
```

<a id="cmd-grade"></a>

### @grade

```text
Params: <equip position> <+/- amount>
```

<a id="cmd-guild"></a>

### @guild

```text
Params: <guild_name>
Create a guild.
```

<a id="cmd-guildlevelup"></a>

### @guildlevelup

Aliases / 別名: `@glevel`, `@glvl`, `@guildlevel`, `@guildlvl`, `@guildlvlup`, `@guildlvup`

```text
Params: <# of levels>
Raise Guild by desired number of levels
```

<a id="cmd-guildrecall"></a>

### @guildrecall

```text
Params: <guild name|ID>
Warps all online characters of a guild to you.
```

<a id="cmd-guildspy"></a>

### @guildspy

```text
Params: <guild name|id>
You will receive all messages of the guild chat (Chat logging must be enabled)
```

<a id="cmd-guildstorage"></a>

### @guildstorage

Aliases / 別名: `@gstorage`

```text
Opens guild storage.
```

<a id="cmd-gvgoff"></a>

### @gvgoff

Aliases / 別名: `@gpvpoff`

```text
Disables GvG on the current map
```

<a id="cmd-gvgon"></a>

### @gvgon

Aliases / 別名: `@gpvpon`

```text
Enables GvG on the current map
```

<a id="cmd-hair_color"></a>

### @hair_color

Aliases / 別名: `@haircolor`, `@hcolor`

```text
Params <hair palette no.>
Changes your hair color.
```

<a id="cmd-hair_style"></a>

### @hair_style

Aliases / 別名: `@hairstyle`, `@hstyle`

```text
Params: <hairstyle no.>
Changes your hair style.
```

<a id="cmd-hatch"></a>

### @hatch

```text
Create a pet from your inventory eggs list.
```

<a id="cmd-hatereset"></a>

### @hatereset

```text
Resets a Star Gladiator's marked monsters.
```

<a id="cmd-heal"></a>

### @heal

```text
Params: [<HP> <SP>]
Heals the desired amount of HP and SP. No value specified will do a full heal.
```

<a id="cmd-healap"></a>

### @healap

```text
Params: [<AP>]
Heals the desired amount of AP. No value specified will do a full AP heal.
```

<a id="cmd-help"></a>

### @help

Aliases / 別名: `@h`

```text
Params: <command>
Shows help for specified command.
```

<a id="cmd-hide"></a>

### @hide

```text
Makes you character invisible (GM invisibility). Type again to become visible.
```

<a id="cmd-hidenpc"></a>

### @hidenpc

```text
Params: <NPC name>
Disable a NPC.
```

<a id="cmd-homevolution"></a>

### @homevolution

Aliases / 別名: `@homevolve`

```text
Evolves your homunculus, if possible.
```

<a id="cmd-homfriendly"></a>

### @homfriendly

```text
Params: <level of intimacy> - value between 0-1000
Sets your homunculus intimacy level to the desired value.
```

<a id="cmd-homhungry"></a>

### @homhungry

```text
Params: <level of hunger> - value between 0-100
Sets your homunculus hunger level to the desired value.
```

<a id="cmd-hominfo"></a>

### @hominfo

```text
Displays homunculus stats.
```

<a id="cmd-homlevel"></a>

### @homlevel

Aliases / 別名: `@hlvl`, `@hlevel`, `@homlvl`, `@homlvup`

```text
Params: <level>
Increases the homunculus level by <level>.
```

<a id="cmd-hommutate"></a>

### @hommutate

```text
Params: <mutated homunculus ID>
Mutates your homunculus to <mutated homunculus ID>, if possible.
```

<a id="cmd-homshuffle"></a>

### @homshuffle

```text
Recalculates the homunculus stats, as if the homunculus was leveled again from level 1.
```

<a id="cmd-homstats"></a>

### @homstats

```text
Displays homunculus stats.
```

<a id="cmd-homtalk"></a>

### @homtalk

```text
Params: <message>
Let the player's homunculus say the text <message>.
```

<a id="cmd-identify"></a>

### @identify

```text
Opens the identification window if any unidentified items are in your inventory.
```

<a id="cmd-identifyall"></a>

### @identifyall

```text
Any unidentified items in your inventory will automatically be identified.
```

<a id="cmd-idsearch"></a>

### @idsearch

```text
Params: <part_of_item_name>
Search all items that name have part_of_item_name
```

<a id="cmd-int"></a>

### @int

```text
Params: <amount>
Raises INT by given amount.
```

<a id="cmd-invite"></a>

### @invite

```text
Invites a player to a duel.
```

<a id="cmd-item"></a>

### @item

```text
Params: <item name or ID> <quantity>
Gives you the desired item.
```

<a id="cmd-item2"></a>

### @item2

```text
Params: <item name or ID> <quantity> <identified_flag> <refine> <broken_flag> <Card1> <Card2> <Card3> <Card4>
Gives you the desired item.
```

<a id="cmd-itembound"></a>

### @itembound

```text
Params: <item name or ID> <quantity> <bound type>
Creates an item bounded to the character.
The items cannot be dropped, sold, vended, auctioned, or mailed, and in some cases cannot be traded or stored.
Available bound types:
  1: Account
  2: Guild
  3: Party
  4: Character
```

<a id="cmd-itembound2"></a>

### @itembound2

```text
Params: <item name or ID> <quantity> <identified_flag> <refine> <broken_flag> <Card1> <Card2> <Card3> <Card4> <bound type>
Creates an item bounded to the character.
The items cannot be dropped, sold, vended, auctioned, or mailed, and in some cases cannot be traded or stored.
Available bound types:
  1: Account
  2: Guild
  3: Party
  4: Character
```

<a id="cmd-iteminfo"></a>

### @iteminfo

Aliases / 別名: `@ii`

```text
Params: <item name|ID>
Shows item info (type, price etc).
```

<a id="cmd-itemlist"></a>

### @itemlist

Aliases / 別名: `@inventorylist`

```text
Displays a list of items in the inventory.
```

<a id="cmd-itemreset"></a>

### @itemreset

Aliases / 別名: `@clearinventory`

```text
Remove all your items.
```

<a id="cmd-jail"></a>

### @jail

```text
Params: <char name>
Sends specified character in jails.
```

<a id="cmd-jailfor"></a>

### @jailfor

```text
Params: <time> <char name>
Sends specified character in jails for the given <time>.
```

<a id="cmd-jailtime"></a>

### @jailtime

```text
Displays remaining jail time.
```

<a id="cmd-jobchange"></a>

### @jobchange

Aliases / 別名: `@job`

```text
Params: <job name|ID>
Changes your job.
----- Novice / 1st Class -----
   0 Novice              1 Swordman            2 Magician            3 Archer
   4 Acolyte              5 Merchant               6 Thief
----- 2nd Class -----
   7 Knight               8 Priest                     9 Wizard               10 Blacksmith
  11 Hunter           12 Assassin            14 Crusader          15 Monk
  16 Sage              17 Rogue                 18 Alchemist         19 Bard
  20 Dancer
----- High Novice / High 1st Class -----
4001 Novice High     4002 Swordman High    4003 Magician High    4004 Archer High
4005 Acolyte High     4006 Merchant High       4007 Thief High
----- Transcendent 2nd Class -----
4008 Lord Knight      4009 High Priest             4010 High Wizard      4011 Whitesmith
4012 Sniper               4013 Assassin Cross   4015 Paladin              4016 Champion
4017 Professor         4018 Stalker                    4019 Creator               4020 Clown
4021 Gypsy
----- 3rd Class (Regular) -----
4054 Rune Knight    4055 Warlock                 4056 Ranger            4057 Arch Bishop
4058 Mechanic         4059 Guillotine Cross  4066 Royal Guard   4067 Sorcerer
4068 Minstrel            4069 Wanderer              4070 Sura                 4071 Genetic
4072 Shadow Chaser
----- 3rd Class (Transcendent) -----
4060 Rune Knight    4061 Warlock                 4062 Ranger             4063 Arch Bishop
4064 Mechanic         4065 Guillotine Cross  4073 Royal Guard    4074 Sorcerer
4075 Minstrel            4076 Wanderer              4077 Sura                  4078 Genetic
4079 Shadow Chaser
----- 4th Class -----
4252 Dragon Knight    4253 Meister                    4254 Shadow Cross     4255 Arch Mage
4256 Cardinal               4257 Windhawk              4258 Imperial Guard     4259 Biolo
4260 Abyss Chaser     4261 Elemental Master 4262 Inquisitor               4263 Troubadour
4264 Trouvere
----- Expanded Class -----
     23 Super Novice      24 Gunslinger              25 Ninja                 4045 Super Baby
4046 Taekwon           4047 Star Gladiator     4049 Soul Linker
4190 Ex. Super Novice  4191 Ex. Super Baby
4211 Kagerou            4212 Oboro             4215 Rebellion        4218 Summoner
4239 Star Emperor   4240 Soul Reaper
4302 Sky Emperor    4303 Soul Ascetic         4304 Shinkiro                 4305 Shiranui
4306 Night Watch     4307 Hyper Novice        4308 Spirit Handler
----- Baby Novice And Baby 1st Class -----
4023 Baby Novice      4024 Baby Swordman    4025 Baby Magician   4026 Baby Archer
4027 Baby Acolyte      4028 Baby Merchant       4029 Baby Thief
---- Baby 2nd Class ----
4030 Baby Knight     4031 Baby Priest         4032 Baby Wizard         4033 Baby Blacksmith
4034 Baby Hunter    4035 Baby Assassin   4037 Baby Crusader    4038 Baby Monk
4039 Baby Sage       4040 Baby Rogue        4041 Baby Alchemist   4042 Baby Bard
4043 Baby Dancer
---- Baby 3rd Class ----
4096 Baby Rune Knight  4097 Baby Warlock     4098 Baby Ranger           4099 Baby Arch Bishop
4100 Baby Mechanic       4101 Baby Glt. Cross  4102 Baby Royal Guard  4103 Baby Sorcerer
4104 Baby Minstrel          4105 Baby Wanderer   4106 Baby Sura             4107 Baby Genetic
4108 Baby Shadow Chaser
---- Expanded Baby Class ----
4220 Baby Summoner        4222 Baby Ninja        4223 Baby Kagero         4224 Baby Oboro
4225 Baby Taekwon       4226 Baby Star Glad    4227 Baby Soul Linker    4228 Baby Gunslinger
4229 Baby Rebellion   4241 Baby Star Emperor    4242 Baby Soul Reaper
```

<a id="cmd-joblevelup"></a>

### @joblevelup

Aliases / 別名: `@jlevel`, `@jlvl`, `@joblevel`, `@joblvl`, `@joblvlup`, `@joblvup`

```text
Params: <number of levels>
Raises your job level the desired number of levels.
```

<a id="cmd-join"></a>

### @join

```text
Params: <#channel_name> {<password>}
Joins the specified channel <#channel_name>, if necessary by using the supplied <password>.
```

<a id="cmd-jump"></a>

### @jump

```text
Params: [<x> [<y>]]
Randomly warps you like a flywing.
```

<a id="cmd-jumpto"></a>

### @jumpto

Aliases / 別名: `@goto`, `@warpto`

```text
Params: <char name>
Warps you to selected character.
```

<a id="cmd-kami"></a>

### @kami

```text
Params: <message>
Broadcasts a message without your name (in yellow).
```

<a id="cmd-kamib"></a>

### @kamib

```text
Params: <message>
Broadcasts a message without your name (in blue).
```

<a id="cmd-kamic"></a>

### @kamic

```text
Params: <color> <message> - color is a hexadecimal value
Broadcasts a message without your name in the color <color>.
```

<a id="cmd-kick"></a>

### @kick

```text
Params: <char name>
Kicks specified character off the server
```

<a id="cmd-kickall"></a>

### @kickall

```text
Kick all characters off the server
```

<a id="cmd-kill"></a>

### @kill

Aliases / 別名: `@die`

```text
Kills player.
```

<a id="cmd-killable"></a>

### @killable

```text
Allows other players to attack you outside of PvP.
```

<a id="cmd-killer"></a>

### @killer

```text
Allows you to attack other players outside of PvP.
```

<a id="cmd-killmonster"></a>

### @killmonster

```text
Params: <map>
Kill all monsters of the map (they drop)
```

<a id="cmd-killmonster2"></a>

### @killmonster2

```text
Kills all monsters of your map (without drops).
```

<a id="cmd-ksprotection"></a>

### @ksprotection

Aliases / 別名: `@noks`

```text
Params: None. Disables kill stealing protection or displays a help message.
Params: self. Enables kill stealing protection against any other players.
Params: party. Enables kill stealing protection against any other players not in your party.
Params: guilds. Enables kill stealing protection against any other players not in your guild.
Prevents other players from kill stealing.
```

<a id="cmd-langtype"></a>

### @langtype

```text
Params: <language>
Changes your language setting.
```

<a id="cmd-leave"></a>

### @leave

```text
Leaves a duel.
```

<a id="cmd-leaves"></a>

### @leaves

```text
Makes all maps to have the leaves weather effect.
```

<a id="cmd-limitedsale"></a>

### @limitedsale

```text
Opens the limited sale window.
```

<a id="cmd-lkami"></a>

### @lkami

```text
Params: <message>
Broadcasts a message without your name on the current map (in yellow).
```

<a id="cmd-load"></a>

### @load

Aliases / 別名: `@return`

```text
Warps you to your save point.
```

<a id="cmd-loadnpc"></a>

### @loadnpc

```text
Params: <path to script>
Load the specified script file path.
```

<a id="cmd-localbroadcast"></a>

### @localbroadcast

```text
Params: <message>
Broadcasts a message with your name (in yellow) only on your map.
```

<a id="cmd-lostskill"></a>

### @lostskill

```text
Params: <#>
Takes away the specified quest skill from you
Novice = 142: First Aid, 143: Act Dead
Archer = 147: Create Arrow, 148: Charge Arrow
Swordman = 144: Moving HP Recovery, 145: Attack Weak Point, 146: Auto Berserk
Acolyte = 156: Holy Light
Thief = 149: Throw Sand, 150: Back Sliding, 151: Take Stone, 152: Throw Stone
Merchant = 153: Cart Revolution, 154: Change Cart, 155: Crazy Uproar, 2535: Open Buying Store
Magician = 157: Energy Coat
Hunter = 1009: Phantasmic Arrow
Bard = 1010: Pang Voice
Dancer = 1011: Wink of Charm
Knight = 1001: Charge Attack
Crusader = 1002: Shrink
Priest = 1014: Redemptio
Monk = 1015: Ki Translation, 1016: Ki Explosio
Assassin = 1003: Sonic Acceleration, 1004: Throw Venom Knife
Rogue = 1005: Close Confine
Blacksmith = 1012: Unfair Trick, 1013: Greed
Alchemist = 238: Basis of Life
Wizard = 1006: Sight Blaster
Sage = 1007: Create Elemental Converter, 1008: Elemental Change (Water), 1017: Elemental Change (Earth), 1018: Elemental Change (Fire), 1019: Elemental Change (Wind)
```

<a id="cmd-luk"></a>

### @luk

```text
Params: <amount>
Raises LUK by given amount.
```

<a id="cmd-macrochecker"></a>

### @macrochecker

```text
Params: <mapname>
Trigger a macro detection on all players of the given map.
```

<a id="cmd-mail"></a>

### @mail

```text
Open mail box.
```

<a id="cmd-makeegg"></a>

### @makeegg

```text
Params: <pet_id>
Gives pet egg for monster number in pet DB
```

<a id="cmd-makehomun"></a>

### @makehomun

```text
Params: <homunculus ID>
Creates a homunculus with the given <homunculus ID>.
```

<a id="cmd-mapexit"></a>

### @mapexit

```text
Kick all players and shut down map-server.
```

<a id="cmd-mapflag"></a>

### @mapflag

```text
Params: None - Shows mapflags that are active on the current map.
Params: "available" - Shows a list of possible mapflags.
Params: <name> - Activates mapflag <name> on the current map.
```

<a id="cmd-mapinfo"></a>

### @mapinfo

```text
Params: [<0-3> [map]]
Give information about a map (general info +: 0: no more, 1: players, 2: NPC, 3: chatrooms).
```

<a id="cmd-mapmove"></a>

### @mapmove

Aliases / 別名: `@rura`, `@warp`

```text
Params: <mapname> [<x> <y>]
Warps you to the selected map and position.
```

<a id="cmd-marry"></a>

### @marry

```text
Params: <player name>
Marry another player.
```

<a id="cmd-me"></a>

### @me

```text
Params: <message>
Displays normal text as a message in this format: *name message* (like /me in mIRC).
```

<a id="cmd-memo"></a>

### @memo

```text
Params: [memo position]
Set/change a memo location (no position: display memo points).
```

<a id="cmd-misceffect"></a>

### @misceffect

```text
Params: <effect ID>
Does some visual effect on the character.
Available effect IDs:
  0 = base level up
  1 = job level up
  2 = refine failure
  3 = refine success
  4 = game over
  5 = pharmacy success
  6 = pharmacy failure
  7 = base level up (super novice)
  8 = job level up (super novice)
  9 = base level up (taekwon)
```

<a id="cmd-mobinfo"></a>

### @mobinfo

Aliases / 別名: `@monsterinfo`, `@mi`

```text
Params: <monster name|ID>
Shows monster info (stats, exp, drops etc).
```

<a id="cmd-mobsearch"></a>

### @mobsearch

```text
Params: <monster name|ID>
Shows the location of a certain mob on the current map.
```

<a id="cmd-model"></a>

### @model

```text
Params:  <hair ID: 0-17> <hair color: 0-8> <clothes color: 0-4> - Changes your characters appearence.
```

<a id="cmd-monster"></a>

### @monster

Aliases / 別名: `@spawn`

```text
Params: <monster name|ID> [<number to spawn> [<desired_monster_name> [<x coord> [<y coord>]]]]
@monster2 <desired_monster_name> <monster name|ID> [<number to spawn> [<x coord> [<y coord>]]]
@spawn/@monster/@summon/@monster2 "desired monster name" <monster name|ID> [<number to spawn> [<x coord> [<y coord>]]]
@spawn/@monster/@summon/@monster2 <monster name|ID> "desired monster name" [<number to spawn> [<x coord> [<y coord>]]]
Spawns the desired monster with any desired name.
```

<a id="cmd-monsterbig"></a>

### @monsterbig

```text
Params: <monster name|ID>
Spawns a larger version of a monster.
```

<a id="cmd-monsterignore"></a>

### @monsterignore

Aliases / 別名: `@battleignore`

```text
Makes the player unattackable by monsters, other players, etc.
```

<a id="cmd-monstersmall"></a>

### @monstersmall

```text
Params: <monster name|ID>
Spawns a smaller version of a monster.
```

<a id="cmd-mount2"></a>

### @mount2

```text
Give/remove a cash mount.
```

<a id="cmd-mount_peco"></a>

### @mount_peco

Aliases / 別名: `@mount`, `@mountpeco`

```text
Give/remove a job-based mount (class is required, but not the skill).
```

<a id="cmd-mute"></a>

### @mute

```text
Params: <char name>
Mutes the player <char name> (prevents talking, usage of skills, and commands).
```

<a id="cmd-mutearea"></a>

### @mutearea

Aliases / 別名: `@stfu`

```text
Params: <time> amount of minutes to mute the players
Mutes every player on screen for the specified time (prevents talking, usage of skills, and commands).
```

<a id="cmd-night"></a>

### @night

```text
Enables night mode on all maps, all characters are affected.
```

<a id="cmd-noask"></a>

### @noask

```text
Auto rejects deals/invites.
```

<a id="cmd-npcmove"></a>

### @npcmove

```text
Params: <x coord> <y coord> <NPC name>
Move a NPC.
```

<a id="cmd-npctalk"></a>

### @npctalk

Aliases / 別名: `@npctalkc`

```text
Params: <NPC name> <message>
Forces a NPC to display a message in normal chat.
```

<a id="cmd-nuke"></a>

### @nuke

```text
Params: <char name>
Blow somebody up, including those surrounding them.
```

<a id="cmd-option"></a>

### @option

```text
Params: <param1> <param2>(stackable) <param3>(stackable)
Adds different visual effects on or around your character.
 <param1>       <param2>        <param3>
01: Stone      01: Sight       01: Sight          512: Cart Lv. 4
02: Frozen     02: Curse       02: Hiding        1024: Cart Lv. 5
03: Stun       04: Silence     04: Cloaking      2048: Orc Head
04: Sleep      08: Signum      08: Cart Lv. 1    4096: Wedding
06: Petrify    16: Blind       16: Falcon        8192: Ruwach
07: Burning    32: Angelus     32: Riding       16384: Chasewalk
08: Imprison   64: Bleeding    64: Invisible
16: (Nothing) 128: D. Poison  128: Cart Lv. 2
32: (Nothing) 256: Fear       256: Cart Lv. 3
```

<a id="cmd-party"></a>

### @party

```text
Params: <party_name>
Create a party.
```

<a id="cmd-partyoption"></a>

### @partyoption

```text
Params: <item sharing> <item distribution> - yes/no
Changes party options for item sharing and item distribution.
```

<a id="cmd-partyrecall"></a>

### @partyrecall

```text
Params: <party name|ID>
Warps all online characters of a party to you.
```

<a id="cmd-partysharelvl"></a>

### @partysharelvl

```text
Params: <level difference>
Temporarily adjusts the party share level range to <level difference>.
```

<a id="cmd-partyspy"></a>

### @partyspy

```text
@partyspy <party name|id> - You will receive all messages of the party channel (Chat logging must be enabled)
```

<a id="cmd-petfriendly"></a>

### @petfriendly

```text
Params: <#>
Set pet friendly amount (0-1000) 1000 = Max
```

<a id="cmd-pethungry"></a>

### @pethungry

```text
Params: <#>
Set pet hungry amount (0-100) 100 = Max
```

<a id="cmd-petrename"></a>

### @petrename

```text
Re-enable pet rename
```

<a id="cmd-pettalk"></a>

### @pettalk

```text
Params: <message>
Makes your pet say a message.
```

<a id="cmd-points"></a>

### @points

```text
Params: <amount> - Gives you the specified amount of Kafra Points.
```

<a id="cmd-pow"></a>

### @pow

```text
Params: <amount>
Raises POW by given amount.
```

<a id="cmd-produce"></a>

### @produce

```text
Params: <equip name or equip ID> <element> <# of very's>
Element: 0=None 1=Ice 2=Earth 3=Fire 4=Wind
You can add up to 3 Star Crumbs and 1 element
```

<a id="cmd-pvpoff"></a>

### @pvpoff

```text
Disables PvP on the current map
```

<a id="cmd-pvpon"></a>

### @pvpon

```text
Enables PvP on the current map
```

<a id="cmd-questskill"></a>

### @questskill

```text
Params: <#>
Gives you the specified quest skill
Novice = 142: First Aid, 143: Act Dead
Archer = 147: Create Arrow, 148: Charge Arrow
Swordman = 144: Moving HP Recovery, 145: Attack Weak Point, 146: Auto Berserk
Acolyte = 156: Holy Light
Thief = 149: Throw Sand, 150: Back Sliding, 151: Take Stone, 152: Throw Stone
Merchant = 153: Cart Revolution, 154: Change Cart, 155: Crazy Uproar, 2535: Open Buying Store, 2544: Decorate Cart
Magician = 157: Energy Coat
Hunter = 1009: Phantasmic Arrow
Bard = 1010: Pang Voice
Dancer = 1011: Wink of Charm
Knight = 1001: Charge Attack
Crusader = 1002: Shrink
Priest = 1014: Redemptio
Monk = 1015: Ki Translation, 1016: Ki Explosio
Assassin = 1003: Sonic Acceleration, 1004: Throw Venom Knife
Rogue = 1005: Close Confine
Blacksmith = 1012: Unfair Trick, 1013: Greed
Alchemist = 238: Basis of Life
Wizard = 1006: Sight Blaster
Sage = 1007: Create Elemental Converter, 1008: Elemental Change (Water), 1017: Elemental Change (Earth), 1018: Elemental Change (Fire), 1019: Elemental Change (Wind)
```

<a id="cmd-raise"></a>

### @raise

Aliases / 別名: `@revive`

```text
Params: <char name>
Revives target character.
```

<a id="cmd-raisemap"></a>

### @raisemap

```text
Resurrects all characters on the map.
```

<a id="cmd-rates"></a>

### @rates

```text
Displays the server's current rates.
```

<a id="cmd-recall"></a>

### @recall

```text
Params: <char name>
Warps target character to you.
```

<a id="cmd-recallall"></a>

### @recallall

```text
Warps every character online to you.
```

<a id="cmd-refine"></a>

### @refine

```text
Params: <equip position> <+/- amount>
```

<a id="cmd-refineui"></a>

### @refineui

```text
Opens the refine UI.
```

<a id="cmd-refresh"></a>

### @refresh

```text
Synchronizes the position and state between client and server.
```

<a id="cmd-refreshall"></a>

### @refreshall

```text
Synchronizes the position and state of all players between client and server.
```

<a id="cmd-reject"></a>

### @reject

```text
Automatically reject duel invitations.
```

<a id="cmd-reload"></a>

### @reload

```text
Params: <type>
Reload a database or a configuration file.
itemdb               mobdb               skilldb
atcommand         battleconf          statusdb
pcdb                  motd                 script
questdb             msgconf             packetdb
cashdb               logconf
```

<a id="cmd-reloadachievementdb"></a>

### @reloadachievementdb

```text
Reload achievement database.
```

<a id="cmd-reloadatcommand"></a>

### @reloadatcommand

```text
Reload atcommand settings.
```

<a id="cmd-reloadattendancedb"></a>

### @reloadattendancedb

```text
Reload attendance database.
```

<a id="cmd-reloadbarterdb"></a>

### @reloadbarterdb

```text
Reload the barter database.
```

<a id="cmd-reloadbattleconf"></a>

### @reloadbattleconf

```text
Reload battle settings.
```

<a id="cmd-reloadcashdb"></a>

### @reloadcashdb

Aliases / 別名: `@reloadcashshop`

```text
Reload cash shop database.
```

<a id="cmd-reloadinstancedb"></a>

### @reloadinstancedb

```text
Reload instance database.
```

<a id="cmd-reloaditemdb"></a>

### @reloaditemdb

```text
Reload item database.
```

<a id="cmd-reloadlogconf"></a>

### @reloadlogconf

```text
Reload the log settings.
```

<a id="cmd-reloadmobdb"></a>

### @reloadmobdb

```text
Reload monster database.
```

<a id="cmd-reloadmotd"></a>

### @reloadmotd

```text
Reload Message of the Day.
```

<a id="cmd-reloadmsgconf"></a>

### @reloadmsgconf

```text
Reload message configuration.
```

<a id="cmd-reloadnpcfile"></a>

### @reloadnpcfile

Aliases / 別名: `@reloadnpc`

```text
Params: <path> - path to script
Unloads and loads a script file from <path>.
```

<a id="cmd-reloadpcdb"></a>

### @reloadpcdb

```text
Reload player settings.
```

<a id="cmd-reloadquestdb"></a>

### @reloadquestdb

```text
Reload quest database.
```

<a id="cmd-reloadscript"></a>

### @reloadscript

```text
Reload all scripts.
```

<a id="cmd-reloadskilldb"></a>

### @reloadskilldb

```text
Reload skills definition database.
```

<a id="cmd-reloadstatusdb"></a>

### @reloadstatusdb

```text
Reload status settings.
```

<a id="cmd-repairall"></a>

### @repairall

```text
Repair all items of your inventory
```

<a id="cmd-request"></a>

### @request

```text
Params: <message>
Sends a message to all connected GMs (via the gm whisper system)
```

<a id="cmd-reset"></a>

### @reset

```text
Resets the player's status and skill points.
```

<a id="cmd-resetcooltime"></a>

### @resetcooltime

Aliases / 別名: `@resetcooldown`

```text
Resets the cooldown of all skills of the player and if active also of the homunculus or the mercenary.
```

<a id="cmd-resetskill"></a>

### @resetskill

Aliases / 別名: `@skreset`

```text
Resets the player's skill points.
```

<a id="cmd-resetstat"></a>

### @resetstat

Aliases / 別名: `@streset`

```text
Resets the player's status points.
```

<a id="cmd-resurrect"></a>

### @resurrect

```text
Resurrects a player, if the necessary conditions (items in inventory or status changes) are fulfilled.
```

<a id="cmd-rmvperm"></a>

### @rmvperm

```text
Params: <permission_name>
Temporarily remove a permission from a player.
```

<a id="cmd-roulette"></a>

### @roulette

```text
Opens the roulette UI.
```

<a id="cmd-sakura"></a>

### @sakura

```text
Makes all maps to have the sakura weather effect.
```

<a id="cmd-save"></a>

### @save

```text
Sets respawn point to current spot.
```

<a id="cmd-send"></a>

### @send

```text
Params: <Hex Number> [<value>]
For debugging (packet variety)
```

<a id="cmd-servertime"></a>

### @servertime

Aliases / 別名: `@date`, `@serverdate`, `@time`

```text
Shows the date and time of the server.
```

<a id="cmd-set"></a>

### @set

```text
Params: <variable name> {<value>}
Shows the value of the variable <variable name>.
If a <value> is provided, it changes the variable <variable name> to the given value.
```

<a id="cmd-setbattleflag"></a>

### @setbattleflag

```text
Params: <battle config name> <value> {<reload>}
Changes <battle config name> to <value> without rebooting the server.
If <reload> is specified, the monster database will also be reloaded.
```

<a id="cmd-setcard"></a>

### @setcard

```text
Adds a card or enchant to the specific slot of the equipment.
```

<a id="cmd-setquest"></a>

### @setquest

```text
Params: <quest ID>
Activates the quest with quest ID <quest ID>.
```

<a id="cmd-showdelay"></a>

### @showdelay

```text
Shows/hides the "There is a delay after this skill" message.
```

<a id="cmd-showexp"></a>

### @showexp

```text
Displays/hides experience gained.
```

<a id="cmd-showmobs"></a>

### @showmobs

```text
Params: <monster ID>
Params: <monster name>
Locates and displays the position of a certain mob on your mini-map.
This shows up as a small white cross (+).
```

<a id="cmd-shownpc"></a>

### @shownpc

```text
Params: <NPC name>
Enable a NPC.
```

<a id="cmd-showrate"></a>

### @showrate

```text
Enable or disable to show the rate information on every mapchange.
```

<a id="cmd-showzeny"></a>

### @showzeny

```text
Displays/hides Zeny gained.
```

<a id="cmd-size"></a>

### @size

```text
Params:  <0-2> Changes your size (0-Normal 1-Small 2-Large)
```

<a id="cmd-sizeall"></a>

### @sizeall

```text
Changes the size of all players.
```

<a id="cmd-sizeguild"></a>

### @sizeguild

```text
Changes the size of all online characters of a guild.
```

<a id="cmd-skillid"></a>

### @skillid

```text
Params: <name>
Look up a skill by name
```

<a id="cmd-skilloff"></a>

### @skilloff

```text
Turn skills off for a map.
```

<a id="cmd-skillon"></a>

### @skillon

```text
Turn skills on for a map.
```

<a id="cmd-skillpoint"></a>

### @skillpoint

Aliases / 別名: `@skpoint`

```text
Params: <number of points> - Gives you the desired number of skill points.
```

<a id="cmd-skilltree"></a>

### @skilltree

```text
Params: <skillnum> <charname>
Prints the skill tree needed to get a skill for the target player.
```

<a id="cmd-slaveclone"></a>

### @slaveclone

```text
Params: <charname>
Spawns a supportive clone of the given player that follows the creator around.
```

<a id="cmd-snow"></a>

### @snow

```text
Makes all maps to have the snow weather effect.
```

<a id="cmd-soulball"></a>

### @soulball

```text
Params: <amount> - value between 0-20
Summons the specified <amount> of soul spheres around you.
```

<a id="cmd-sound"></a>

### @sound

```text
Params: <path to file in data folder or GRF file>
Plays a sound from the data folder or GRF file located on the client.
```

<a id="cmd-speed"></a>

### @speed

```text
Params: <1-1000>
Changes you walking speed. 1 being the fastest and 1000 the slowest. Default is 150.
```

<a id="cmd-spiritball"></a>

### @spiritball

```text
Params: <1-100>
Gives you "spirit spheres" like from the skill "Call Spirits".
```

<a id="cmd-spl"></a>

### @spl

```text
Params: <amount>
Raises SPL by given amount.
```

<a id="cmd-sta"></a>

### @sta

```text
Params: <amount>
Raises STA by given amount.
```

<a id="cmd-stat_all"></a>

### @stat_all

Aliases / 別名: `@allstat`, `@allstats`, `@statall`, `@statsall`

```text
Params: <value>
Adds value in all stats (maximum if no value).
```

<a id="cmd-stats"></a>

### @stats

```text
Displays the stats of the player in your chat.
```

<a id="cmd-statuspoint"></a>

### @statuspoint

Aliases / 別名: `@stpoint`

```text
Params: <number of points> - Gives you the desired number of stat points.
```

<a id="cmd-stockall"></a>

### @stockall

```text
Params: [<item type>]
Transfer items from cart to your inventory. No type specified will transfer all items.
```

<a id="cmd-storage"></a>

### @storage

```text
Opens storage.
```

<a id="cmd-storagelist"></a>

### @storagelist

```text
Displays a list of items in the storage.
```

<a id="cmd-storeall"></a>

### @storeall

```text
Puts all your possessions in storage.
```

<a id="cmd-str"></a>

### @str

```text
Params: <amount>
Raises STR by given amount.
```

<a id="cmd-stylist"></a>

### @stylist

```text
Opens the stylist user interface.
```

<a id="cmd-summon"></a>

### @summon

```text
Params: <monster name/ID> {<duration>}
Spawns the monster with <monster name/ID> and let it treat you as their master.
If a duration is specified, it will stay with you until the duration has ended.
```

<a id="cmd-tonpc"></a>

### @tonpc

```text
Params: <NPC name>
Warps to the specified NPC.
```

<a id="cmd-trade"></a>

### @trade

```text
Params: <char name> - Open a trade window with a another player
```

<a id="cmd-trait_all"></a>

### @trait_all

Aliases / 別名: `@alltrait`, `@alltraits`, `@traitall`, `@traitsall`

```text
Params: <value>
Adds value in all traits (maximum if no value).
```

<a id="cmd-traitpoint"></a>

### @traitpoint

Aliases / 別名: `@trpoint`

```text
Params: <number of points> - Gives you the desired number of trait stat points.
```

<a id="cmd-unban"></a>

### @unban

Aliases / 別名: `@unbanish`

```text
Params: <name> - Unban an account
```

<a id="cmd-undisguise"></a>

### @undisguise

```text
Restore your normal appearance.
```

<a id="cmd-undisguiseall"></a>

### @undisguiseall

```text
Restore the normal appearance of all connected players.
```

<a id="cmd-undisguiseguild"></a>

### @undisguiseguild

```text
Restore the normal appearance of all characters of a guild.
```

<a id="cmd-unjail"></a>

### @unjail

Aliases / 別名: `@discharge`

```text
Params: <char name>
Discharges specified character/prisoner
```

<a id="cmd-unloadnpc"></a>

### @unloadnpc

```text
Params: <NPC name>
Unload the specified NPC according to name.
```

<a id="cmd-unloadnpcfile"></a>

### @unloadnpcfile

```text
Params: <path>
Unload the specified script file path.
```

<a id="cmd-unmute"></a>

### @unmute

```text
Params: <char name>
Unmutes the player <char name>.
```

<a id="cmd-uptime"></a>

### @uptime

```text
Displays how long the server has been online.
```

<a id="cmd-users"></a>

### @users

```text
Displays the distribution of players on the server per map.
```

<a id="cmd-useskill"></a>

### @useskill

```text
Params: <skillid> <skillv> <target>
Use a skill on target
```

<a id="cmd-version"></a>

### @version

```text
Displays SVN version of the server.
```

<a id="cmd-vip"></a>

### @vip

```text
Params: <+/- time> <char name>
Set a player in VIP mode for a limited time.
Time elements: y/a, m, d/j, h, mn, s
```

<a id="cmd-vit"></a>

### @vit

```text
Params: <amount>
Raises VIT by given amount.
```

<a id="cmd-where"></a>

### @where

```text
Params: <char name>
Tells you the location of a character.
```

<a id="cmd-whereis"></a>

### @whereis

```text
Params: <monster name/ID>
Displays the maps in which monster <monster name/ID> normally spawns.
```

<a id="cmd-who"></a>

### @who

Aliases / 別名: `@whois`

```text
Params: [<name>]
Shows a list of online players and their party and guild.
```

<a id="cmd-who2"></a>

### @who2

```text
Params: [<name>]
Shows a list of online players and their job.
```

<a id="cmd-who3"></a>

### @who3

```text
Params: [<name>]
Shows a list of online players and their location.
```

<a id="cmd-whodrops"></a>

### @whodrops

```text
Params: <item name|ID>
Shows who drops an item (monster with highest drop rates).
```

<a id="cmd-whogm"></a>

### @whogm

```text
Params: [match_text] - Like @who+@who2+who3, but only for GM.
```

<a id="cmd-whomap"></a>

### @whomap

```text
Params: <mapname>
Like @who but only for specified map <mapname>.
```

<a id="cmd-whomap2"></a>

### @whomap2

```text
Params: <mapname>
Like @who2 but only for specified map <mapname>.
```

<a id="cmd-whomap3"></a>

### @whomap3

```text
Params: <mapname>
Like @who3 but only for specified map <mapname>.
```

<a id="cmd-wis"></a>

### @wis

```text
Params: <amount>
Raises WIS by given amount.
```

<a id="cmd-zeny"></a>

### @zeny

```text
Params: <amount> - Gives you desired amount of Zeny.
```

