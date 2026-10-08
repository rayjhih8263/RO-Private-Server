# 03 Set up the RO client

[繁體中文](../03-client.md) | English

This chapter assumes the client and server are tested on the same Windows computer.

## 1. Download the client with Git

Source: [ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN).

Open Git Bash and enter:

```bash
cd /c/RO-Server
git clone https://github.com/rAthenaCN/ROClientFullCN.git RO-Client
```

This guide uses:

```text
C:\RO-Server\RO-Client
```

Check that the folder contains:

```text
2021-11-03_Ragexe_patched.exe
Setup_Plus.exe
DATA.INI
data.grf
data\
System\
```

If Git LFS reports a download failure, check which client files are already present, then complete the large GRFs in the next step. A partially downloaded resource folder is not ready to run.

## 2. Complete the five large GRFs manually

Required files:

| Order | Filename | Source page |
| --- | --- | --- |
| 1 | `luafiles.grf` | [luafiles.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/luafiles.grf) |
| 2 | `map.grf` | [map.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/map.grf) |
| 3 | `sprite.grf` | [sprite.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/sprite.grf) |
| 4 | `texture_01.grf` | [texture_01.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/texture_01.grf) |
| 5 | `texture_02.grf` | [texture_02.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/texture_02.grf) |

1. Open each file page above and use **Download / Download raw file** to obtain the actual file.
2. Copy the completed downloads into `C:\RO-Server\RO-Client`, alongside the client executable. Replace same-name files.
3. Check that all five large files are complete. A roughly 1 KB file containing `version https://git-lfs.github.com/spec/v1` when opened in a text editor is an LFS pointer, not a complete GRF.
4. If the source reports an LFS quota or download restriction, wait for it to recover or obtain complete files you are authorized to use. Renaming pointer files does not supply the resources.

**Also keep the `data.grf` included in the Git download.** In this source it is a small GRF (769 B), separate from the five large resource files. Do not delete it or replace it with a different client's same-name file just because it is small.

## 3. Check DATA.INI

Open in a text editor:

```text
C:\RO-Server\RO-Client\DATA.INI
```

Check the source's loading order:

```ini
[Data]
0=data.grf
1=luafiles.grf
2=map.grf
3=sprite.grf
4=texture_01.grf
5=texture_02.grf
```

**0–5 are GRF loading indexes**; preserve them. Filenames must match the actual files in the client folder. Press **Ctrl + S** to save.

[Reference: source DATA.INI](https://github.com/rAthenaCN/ROClientFullCN/blob/master/DATA.INI)

## 4. Configure Setup_Plus.exe

1. Run `Setup_Plus.exe` in the client folder.
2. Select **Primary Display Driver [Direct3D HAL]** as the display device (Chinese interface: **主顯示器驅動程式 [Direct3D HAL]**).
3. Choose a resolution supported by your primary display.
4. Click **Apply / OK** to save, then close the setup window.

## 5. Configure the local connection

The connection file included in this source is:

```text
C:\RO-Server\RO-Client\data\sclientinfo.xml
```

Open it in a text editor. Locate `<address>` and `<port>` in the `<connection>` block and set:

```xml
<address>127.0.0.1</address>
<port>6900</port>
```

Preserve the remaining XML and press **Ctrl + S** to save. If your client version names its configuration `clientinfo.xml`, edit the file that version actually reads; do not rename it simply to match this guide.

[Reference: source sclientinfo.xml](https://github.com/rAthenaCN/ROClientFullCN/blob/master/data/sclientinfo.xml)

## 6. Check the server and game account

1. For `2021-11-03_Ragexe_patched.exe`, use server `PACKETVER` **20211103**. See [02 Build the server](02-server.md#4-build-the-server).
2. Start `login-server.exe` → `char-server.exe` → `map-server.exe` in order. Check for connection errors and keep them running.
3. Complete [Create a GameMaster account](02-server.md#8-create-a-gamemaster-gm-account). Sign in with the GM game account, not MariaDB's root or database account.

## 7. Run the client and verify

Run this file in the client folder:

```text
2021-11-03_Ragexe_patched.exe
```

Completion checks:

1. The login screen opens.
2. Sign in with the game account you created.
3. Reach character selection, create or select a character, and enter a game map.
4. No missing GRF, map or texture errors appear. If files are missing, recheck the complete files in step 2 and the loading order in step 3.

Back up the entire client folder, including GRFs, configuration files and resource folders.

[Next: Third jobs and Eden Group](04-third-jobs-eden.md) | [Back to the index](../../README.en.md)

## License and use

Original teaching text and original diagrams, to the extent the author holds copyright in them, are licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You may share and adapt this material for noncommercial purposes. Credit **rayjhih8263**, link to this repository and the license, and indicate changes. Shared adaptations must use the same license. Commercial use, including selling bundles, paid downloads, or inclusion in paid teaching materials, requires separate permission from the rights holder.

Third-party software, game assets, trademarks, screenshots and images are excluded from this license and remain subject to their respective rights and licenses. This is an unofficial educational guide. Attribution and an educational purpose do not replace permission. See [the license notice](../../LICENSE.md).
