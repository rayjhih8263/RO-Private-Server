# 04 GM command guide

[繁體中文](../08-gm-commands.md) | English | [Index](../../README.en.md)

## 1. Check GM permissions

Create the account using [the GameMaster account procedure](02-server.md), then enter commands in the in-game chat box and press Enter.

In the standard configuration, group 99 is Admin and has `Permissions: all_commands: true` in `conf/groups.yml`. Imports in `conf/import/groups.yml`, map restrictions, character state, server build mode and client support can still affect execution.

This guide covers all built-in commands registered in the cited rAthena revision, not every possible installation. Custom C++ commands and script-bound commands are excluded. A 2021 client may not support newer interfaces or jobs.

## 2. Check commands available on your server

1. Run `@commands` to list your available @ commands.
2. Run `@charcommands` to list your available # commands.
3. Run `@help item`; replace `item` with the command you need.
4. Use Ctrl + F in your browser to search the complete reference in section 5.

@ commands generally use your character as the executing character; some take a target name themselves. # commands select another character as the executing target:

```text
#command "Character Name" parameters
#heal "Test Player"
```

Check `@charcommands` first. Do not blindly substitute # for @: command-specific targets and restrictions still apply. The default symbols are @ and # but servers can customize them.

`<...>` marks required parameters; `[...]` marks optional parameters. Do not type those brackets literally. Replace character names and job IDs with actual values.

## 3. Common commands and examples

| Category | Example | Purpose |
| --- | --- | --- |
| Lookup | `@commands` | List your available @ commands |
| Lookup | `@charcommands` | List your available # commands |
| Lookup | `@help item` | Show help for item |
| Lookup | `@rates` | Show experience and drop rates |
| Lookup | `@who` | List online players |
| Lookup | `@where CharacterName` | Find a character |
| Travel | `@warp prontera 150 150` | Warp to the specified Prontera coordinates |
| Travel | `@go 0` | Warp to Prontera |
| Travel | `@load` | Return to your save point |
| Character | `@heal` | Fully restore your HP and SP |
| Character | `@alive` | Revive yourself |
| Character | `@raise CharacterName` | Revive a named character |
| Character | `@blvl 10` | Increase Base level by 10; this is an increment |
| Character | `@jlvl 10` | Increase Job level by 10; this is an increment |
| Character | `@jobchange JobID` | Change job; requires server and client support |
| Character | `@allskill` | Grant skills; client support is still required |
| Character | `@reset` | Reset stats and skills |
| Character | `@resetstat` | Reset stat points |
| Character | `@resetskill` | Reset skill points |
| Character | `@speed 150` | Set walking speed; default 150, smaller is faster |
| Character | `@hide` | Toggle GM invisibility |
| Items | `@item 501 10` | Create 10 Red Potions |
| Items | `@zeny 100000` | Add 100000 Zeny |
| Items | `@storage` | Open storage |
| Monsters | `@monster 1002 1` | Spawn one Poring nearby |
| Moderation | `@kick CharacterName` | Disconnect a character |
| Moderation | `@jail CharacterName` | Jail a character |
| Moderation | `@unjail CharacterName` | Release a character from jail |
| Reload | `@reloadscript` | Reload NPC scripts; active interactions may be interrupted |
| Reload | `@reloadbattleconf` | Reload battle settings |
| Reload | `@reloadatcommand` | Reload command settings |

## 4. Administration and reload notes

1. Item, Zeny, level and skill commands change game data. Use a separate test character where practical.
2. `@kickall` disconnects all characters. Check targets and parameters before account moderation, item deletion or monster-clearing commands.
3. Reload the relevant data after editing scripts or settings. C++, PACKETVER and build-mode changes still require rebuilding.
4. For Unknown Command, check spelling, source version and GM permissions. Being listed here does not guarantee access for the current character.

## 5. Complete command reference

All 313 built-in registered names and configured aliases are included. The complete reference preserves upstream English help and parameters. Help can differ from implementation; use matching source and in-game results as the authority.

- [Complete names, aliases, parameters and help](../reference/gm-commands-rathena.md)
- [Original help snapshot](../reference/rathena-atcommands.yml)

## 6. Sources and licensing

- [Command registry and implementation](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/src/map/atcommand.cpp)
- [Help and aliases](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/conf/atcommands.yml)
- [GM group permissions](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/conf/groups.yml)

Source revision: `d4b8e7b8f16061cc2496d377ac8f777ce72a4f39`.

The upstream-derived reference and snapshot remain GPL-3.0-or-later and are excluded from the noncommercial teaching license. See [source and license notice](../reference/README.md). Original guide prose follows [the teaching license](../../LICENSE.md).
