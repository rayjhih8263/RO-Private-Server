# 03 Set up the RO client

[繁體中文](../03-client.md) | English

## 1. Obtain the client

Recorded source: [ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN).

Current executable:

```text
2021-11-03_Ragexe_patched.exe
```

## 2. Complete the GRF resources

After encountering problems with Git LFS downloads, the owner downloaded complete GRF files individually and copied them into the client folder.

Keep the actual resource files in your backup, along with the executable.

## 3. Configure a local connection

When the client and server run on the same computer, open this file in the client folder:

```text
data\clientinfo.xml
```

Set the address and port:

```xml
<address>127.0.0.1</address>
<port>6900</port>
```

Save the file.

## 4. Check the server packet version

The executable date is November 3, 2021, corresponding to `20211103`. The server was previously changed to `20220406`. Its current value still needs checking; a change back has not been confirmed.

## Completion check

The later setup conversation was cross-checked for October 1, 2026 (Taiwan time):

- 08:24: ROClientFullCN was being used; its ZIP contained `2021-11-03_Ragexe_patched.exe`.
- 09:17–09:23: `luafiles.grf` and `map.grf` were downloaded manually and copied over the existing files. Other GRF file sizes were also checked later.
- 10:51: The owner reported successfully entering the game.

**This client has a recorded successful game login.**

The current folder path and full resource-merging details still need checking. Earlier tests using a 2022-04-06 executable and WARP are excluded from the steps for this current executable.

[Back to the English index](../../README.en.md)

## License and use

Original teaching text and original diagrams, to the extent the author holds copyright in them, are licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You may share and adapt this material for noncommercial purposes. Credit **rayjhih8263**, link to this repository and the license, and indicate changes. Shared adaptations must use the same license. Commercial use, including selling bundles, paid downloads, or inclusion in paid teaching materials, requires separate permission from the rights holder.

Third-party software, game assets, trademarks, screenshots and images are excluded from this license and remain subject to their respective rights and licenses. This is an unofficial personal learning record. Attribution and an educational purpose do not replace permission. See [the license notice](../../LICENSE.md).
