# 03 Set up the RO client

[繁體中文](../03-client.md) | English

## 1. Obtain the client

Client reference: [ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN).

Current executable:

```text
2021-11-03_Ragexe_patched.exe
```

## 2. Complete the GRF resources

Download complete GRF files individually and copy them into the client folder. Check that the downloads are complete files rather than Git LFS pointer text files.

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

The executable date is November 3, 2021. Set the server's `PACKETVER` to `20211103`, then follow [02 Build the server](02-server.md#4-build-the-server) and restart the server.

## Completion check

1. Keep the Login, Char and Map servers running.
2. Run `2021-11-03_Ragexe_patched.exe` and verify that the login screen opens.
3. Sign in with an existing game account and verify that character selection and a game map can be reached.

Use the actual installation location for the client folder. Detailed resource-merging and game-account creation steps are pending.

[Back to the English index](../../README.en.md)

## License and use

Original teaching text and original diagrams, to the extent the author holds copyright in them, are licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You may share and adapt this material for noncommercial purposes. Credit **rayjhih8263**, link to this repository and the license, and indicate changes. Shared adaptations must use the same license. Commercial use, including selling bundles, paid downloads, or inclusion in paid teaching materials, requires separate permission from the rights holder.

Third-party software, game assets, trademarks, screenshots and images are excluded from this license and remain subject to their respective rights and licenses. This is an unofficial educational guide. Attribution and an educational purpose do not replace permission. See [the license notice](../../LICENSE.md).
