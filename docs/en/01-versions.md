# 01 Check versions

[繁體中文](../01-versions.md) | English

Versions and settings used in this guide:

| Item | Version or setting | Reference |
| --- | --- | --- |
| Operating system | Windows 11 | — |
| Server | rAthena; source commit not recorded | [rAthena](https://github.com/rathena/rathena) |
| RO Client | ROClientFullCN | [ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN) |
| Current client executable | 2021-11-03_Ragexe_patched.exe | Same source |
| GRF resources | Downloaded individually by hand, then copied into the client folder | Same source |
| Server PACKETVER | **20211103 (configured for the current client)** | [02 Build the server](02-server.md#4-build-the-server) / [rAthena configuration notes](https://github.com/rathena/rathena/blob/master/src/config/packets.hpp) |
| Build tools | Visual Studio Community 2026 | [Visual Studio Community](https://visualstudio.microsoft.com/vs/community/) |
| Build configuration | Release / x64 | — |
| Database | MariaDB 11.8.9 | [MariaDB downloads](https://mariadb.org/download/) |

## Full client executable name

```text
2021-11-03_Ragexe_patched.exe
```

The owner confirmed this as the current executable after reviewing the setup conversation on October 3, 2026.

## Before building

The client date is **November 3, 2021**, so this guide sets the following in `src/custom/defines_pre.hpp`:

```cpp
#define PACKETVER 20211103
```

Follow [02 Set up the server → 4. Build the server](02-server.md#4-build-the-server) for the exact position, saving and build sequence.

The original conversation included testing with `20220406`. The final value on the original computer has not been read and verified. Therefore, `20211103` in the table is this guide's configuration target, not confirmation that the original computer has already been changed.

Download pages may show newer releases. Check against the versions above.

[Next: Set up the server](02-server.md)

## License and use

Original teaching text and original diagrams, to the extent the author holds copyright in them, are licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You may share and adapt this material for noncommercial purposes. Credit **rayjhih8263**, link to this repository and the license, and indicate changes. Shared adaptations must use the same license. Commercial use, including selling bundles, paid downloads, or inclusion in paid teaching materials, requires separate permission from the rights holder.

Third-party software, game assets, trademarks, screenshots and images are excluded from this license and remain subject to their respective rights and licenses. This is an unofficial personal learning record. Attribution and an educational purpose do not replace permission. See [the license notice](../../LICENSE.md).
