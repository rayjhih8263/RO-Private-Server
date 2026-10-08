# 02 Set up the server

[繁體中文](../02-server.md) | English

Follow the steps in order. This chapter assumes **the client and server are tested on the same Windows computer**. The database commands below are intended for a fresh, empty database.

## 1. Install Git

Download: [Git for Windows](https://gitforwindows.org/).

Click **Download**, download the Windows installer and complete installation. Git Bash will be used to download the source code.

## 2. Install the build tools

Download: [Visual Studio Community](https://visualstudio.microsoft.com/vs/community/).

1. Find **Visual Studio Community** and click **Free download** in that column.
2. Run the downloaded installer.
3. Open the **Workloads** screen in Visual Studio Installer.
4. Select **Desktop development with C++** and keep the default MSVC build tools and Windows SDK selected.
5. Click **Install** and wait for completion.

Download-page reference: choose **Community → Free download** on the left. The saved screenshot shows the Traditional Chinese interface.

![Visual Studio Community free download](../../assets/vs-community-free-download.jpg)

Completion check: Visual Studio opens.

Workload reference from Microsoft documentation; the appearance may differ between versions:

![Select Desktop development with C++](https://learn.microsoft.com/zh-tw/cpp/get-started/media/vs-2026/visual-studio-installer-cpp-workload.png)

[Microsoft installation instructions](https://learn.microsoft.com/en-us/cpp/build/vscpp-step-0-installation)

## 3. Prepare rAthena

Source: [rAthena on GitHub](https://github.com/rathena/rathena).

Create `C:\RO-Server`. Right-click an empty area in that folder → **Show more options** → **Open Git Bash here**, then enter:

```bash
cd /c/RO-Server
git clone https://github.com/rathena/rathena.git
```

The source will be in:

```text
C:\RO-Server\rathena
```

The command above downloads the current version. Keep the source or record its commit to use the same version on another computer.

Completion check: `rAthena.sln` exists in the folder. After downloading, run the following in Git Bash and record the commit hash so you can reproduce the same source version later:

```bash
cd /c/RO-Server/rathena
git rev-parse HEAD
```

[rAthena Windows installation guide](https://github.com/rathena/rathena/wiki/Install-on-Windows)

## 4. Build the server

The current client is `2021-11-03_Ragexe_patched.exe`. This guide uses packet version `20211103`. Follow these steps in order:

1. **Check the default version in `src/config/packets.hpp`**. Open this file in a text editor:

   ```text
   C:\RO-Server\rathena\src\config\packets.hpp
   ```

   Press **Ctrl + F**, search for `#ifndef PACKETVER`, and locate the default definition below it:

   ```cpp
   #ifndef PACKETVER
       // Official explanatory comments appear here.
       #define PACKETVER 20211103
   #endif
   ```

   **Check this section without editing it.** The official comments instruct Windows users to set a custom version in `defines_pre.hpp`, as shown in step 2. Even if the default date differs, set the desired version in step 2.

2. **Set `20211103` in `src/custom/defines_pre.hpp`**. Open:

   ```text
   C:\RO-Server\rathena\src\custom\defines_pre.hpp
   ```

   Press **Ctrl + F** and search for `#define PACKETVER`. If it already exists (for example, with `20220406`), change the date to:

   ```cpp
   #define PACKETVER 20211103
   ```

   If it does not exist, add the line **above** the final `#endif /* CONFIG_CUSTOM_DEFINES_PRE_HPP */`, like this:

   ```cpp
   #define PACKETVER 20211103

   #endif /* CONFIG_CUSTOM_DEFINES_PRE_HPP */
   ```

   Preserve the existing file contents. Keep only one active `#define PACKETVER` line, without `//` in front of it. Press **Ctrl + S** to save.

3. **Open the solution in Visual Studio**:

   ```text
   C:\RO-Server\rathena\rAthena.sln
   ```

4. **Select `Release` → `x64`**. Verify these values in the two dropdowns at the top.

5. **Build the solution**: choose **Build → Build Solution**, or press **Ctrl + Shift + B** (Visual Studio's default shortcut). After changing PACKETVER, a successful build is required to update the executables. If the old servers are still running, close all three server windows before building.

6. **Check the build result** in Visual Studio's **Output** window. Example of a successful build output:

   ```text
   15 succeeded, 0 failed
   ```

   Verify **0 failed** and check for these files in `C:\RO-Server\rathena`:

   ```text
   login-server.exe
   char-server.exe
   map-server.exe
   ```

   The number of successful projects may differ with another source version.

Verify that the client date matches `PACKETVER`; see [01 Check versions](01-versions.md) for the version table.

References: [rAthena packets.hpp](https://github.com/rathena/rathena/blob/master/src/config/packets.hpp) / [defines_pre.hpp](https://github.com/rathena/rathena/blob/master/src/custom/defines_pre.hpp) / [Visual Studio shortcuts](https://learn.microsoft.com/en-us/visualstudio/ide/default-keyboard-shortcuts-in-visual-studio)

## 5. Install the database

Download: [MariaDB Server](https://mariadb.org/download/).

Version used in this guide: **11.8.9**. Select:

1. MariaDB Server Version: **11.8.9**.
2. Operating System: **Windows**.
3. Architecture: **x86_64**.
4. Package Type: **MSI Package**.
5. Click **Download**, then run `mariadb-11.8.9-winx64.msi`.

Download-page reference:

![MariaDB 11.8.9 Windows MSI options](../../assets/mariadb-download-options-11-8-9.jpg)

During installation:

- **Service Name**: customizable, for example `MariaDB` or `RODatabase`. This identifies the service in Windows Services; it is separate from the in-game server name and database username.
- **TCP port: 3306**: the usual default port for MariaDB/MySQL. Keeping it makes the later connection settings consistent. If you change it, update all database ports in step 9 as well. If another database already uses 3306, choose an unused port.
- Set your own root password.
- Select **Install as service** and **Enable networking**.

Completion check: the MariaDB client appears in the Start menu.

Reference screens from MariaDB's official documentation:

**Root password**

![MariaDB root password settings](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-9a33617da161fc206c87b5bfc620c2bad5297f36%2FDatabaseProperties_1_New.png?alt=media)

**Service name and port**

![MariaDB service name and port](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-2e4b4eee2d20b741a9ee1cda8b5c9cfcf0495537%2FDatabaseProperties_2_New.png?alt=media)

These screenshots identify the fields and show MariaDB 10.6. Customize the service name, preferably keep port **3306**, and use your own password.

**Red-box field guide (an explanatory diagram, not an installer screenshot):**

![Customizable MariaDB fields](../../assets/mariadb-custom-fields.en.svg)

[Official MariaDB Windows installer guide](https://mariadb.com/docs/server/server-management/install-and-upgrade-mariadb/installing-mariadb/binary-packages/installing-mariadb-msi-packages-on-windows)

## 6. Create the databases

Open **MySQL Client (MariaDB)** and enter the root password set during installation. This administrator password serves a different purpose from the database password used by rAthena below.

Check the actual installed version and port first. If the port is different from 3306, use the reported value in step 9:

```sql
SELECT VERSION(), @@port;
```

**The database username is customizable.** Replace `YOUR_DB_USER` and `YOUR_DB_PASSWORD` with your own username and password before running these commands (for example, username `ro_user`). Use the same username in all three relevant lines.

This account is for rAthena's database connection, separate from a game login account. `localhost` restricts it to local connections. This guide keeps database names `ragnarok` and `ragnarok_log`.

**Field colors: blue bold italic = username; red bold italic = password.** The image illustrates the fields. Copy the SQL block below and replace the placeholders before running it.

![Create databases and user: highlighted username and password](../../assets/mariadb-create-user-highlight.svg)

```sql
CREATE DATABASE ragnarok CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE DATABASE ragnarok_log CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'YOUR_DB_USER'@'localhost' IDENTIFIED BY 'YOUR_DB_PASSWORD';
GRANT ALL PRIVILEGES ON ragnarok.* TO 'YOUR_DB_USER'@'localhost';
GRANT ALL PRIVILEGES ON ragnarok_log.* TO 'YOUR_DB_USER'@'localhost';
FLUSH PRIVILEGES;
```

Completion check: each statement completes without `ERROR`. If a database or user already exists, check whether this step was already performed rather than deleting existing data.

## 7. Import the tables

In the same MariaDB client window, still logged in as root, run these commands in order. Use **your actual source folder path** after `SOURCE` if it differs. Import SQL files from the same source version used to build the server:

```sql
USE ragnarok;
SOURCE C:/RO-Server/rathena/sql-files/main.sql;
SHOW TABLES;
USE ragnarok_log;
SOURCE C:/RO-Server/rathena/sql-files/logs.sql;
SHOW TABLES;
```

Reference table counts: **56** in `ragnarok` and **10** in `ragnarok_log`. Counts may differ with another source version; use the required tables and absence of import errors below as your checks.

Completion check: `ragnarok` contains tables such as `login` and `char`; `ragnarok_log` contains `loginlog`; and the import reports no `ERROR`. If a file cannot be opened, check its `SOURCE` path.

## 8. Create a GameMaster (GM) account

A GM is a game administrator account, separate from the database account in step 6.

1. **Open MySQL Client (MariaDB)**, enter the root password and select the game database:

   ```sql
   USE ragnarok;
   ```

2. **Check password storage settings**. Open `conf/login_athena.conf` and search for `use_MD5_passwords`. The main command below uses the default:

   ```text
   use_MD5_passwords: no
   ```

   If `conf/import/login_conf.txt` also defines this setting, use the effective value after overrides. If it is `yes`, replace the password value in step 4 with `MD5('YOUR_GM_PASSWORD')`. Do not change an existing password-storage setting just to create this account.

3. **Check whether the username already exists**. Replace `YOUR_GM_USER` with the desired game username:

   ```sql
   SELECT account_id, userid, sex, group_id
   FROM login
   WHERE userid = 'YOUR_GM_USER';
   ```

   Continue only if the result is `Empty set`. If an account exists, choose a different username to avoid duplicates.

4. **Create the GM account**. Replace the username and password before running:

   ```sql
   INSERT INTO login (userid, user_pass, sex, email, group_id)
   VALUES ('YOUR_GM_USER', 'YOUR_GM_PASSWORD', 'M', '', 99);
   ```

   - `YOUR_GM_USER`: your game username, up to 23 characters.
   - `YOUR_GM_PASSWORD`: your game password, up to 32 characters for this plaintext example. Escape a single quote by writing two single quotes `''` in SQL.
   - `M`: male character account; use `F` for a female character account. Do not use `S`, which is reserved for inter-server accounts.
   - `99`: rAthena's default **Admin** group with administrator permissions. If groups have been customized, check `conf/groups.yml` and `conf/import/groups.yml`.
   - The database generates `account_id` automatically.

5. **Verify creation**. Run the query in step 3 again. It should return one row with `group_id` **99** and the selected `sex` **M/F**.

   After completing [03 Set up the RO client](03-client.md), sign in using this **GM game username and password**. Log out and back in if permissions were changed while the account was logged in.

References: [rAthena login table](https://github.com/rathena/rathena/blob/master/sql-files/main.sql) / [Password settings](https://github.com/rathena/rathena/blob/master/conf/login_athena.conf) / [Administrator group](https://github.com/rathena/rathena/blob/master/conf/groups.yml)

## 9. Configure the database connection

Open:

```text
C:\RO-Server\rathena\conf\inter_athena.conf
```

Update all **six groups of connection fields**, including the easily missed `ipban_db` group:

| IP | Port | Account | Password | Database | Value |
| --- | --- | --- | --- | --- | --- |
| `login_server_ip` | `login_server_port` | `login_server_id` | `login_server_pw` | `login_server_db` | `ragnarok` |
| `ipban_db_ip` | `ipban_db_port` | `ipban_db_id` | `ipban_db_pw` | `ipban_db_db` | `ragnarok` |
| `char_server_ip` | `char_server_port` | `char_server_id` | `char_server_pw` | `char_server_db` | `ragnarok` |
| `map_server_ip` | `map_server_port` | `map_server_id` | `map_server_pw` | `map_server_db` | `ragnarok` |
| `web_server_ip` | `web_server_port` | `web_server_id` | `web_server_pw` | `web_server_db` | `ragnarok` |
| `log_db_ip` | `log_db_port` | `log_db_id` | `log_db_pw` | `log_db_db` | `ragnarok_log` |

In each group, set the IP to `127.0.0.1`, the port to the value from step 5 (default `3306`), and the username/password to those chosen in step 6. Set each database name according to the table. Keep `log_login_db: loginlog`.

**Check overrides**: `inter_athena.conf` loads `conf/import/inter_conf.txt` at the end. If that file already contains the same settings, edit them there so they do not override your main-file changes. New custom settings can also be placed in this import file. Save and restart the server.

[Field reference: rAthena inter_athena.conf](https://github.com/rathena/rathena/blob/master/conf/inter_athena.conf)

Database credentials differ from the credentials used between servers. The `userid`/`passwd` values in `char_athena.conf` and `map_athena.conf` correspond to the server account with `sex = 'S'` in `ragnarok.login`; **do not replace them with the database username from step 6**. This chapter covers local testing only. Before allowing external connections, replace the default inter-server credentials and update both the matching configuration and database row.

Save the file.

## 10. Start the server

Run in this order:

```text
login-server.exe
char-server.exe
map-server.exe
```

Successful startup indicators:

- Login: ready, port 6900
- Char: ready, port 6121
- Map: online, port 5121
- No database connection errors

**Completion check: all three servers remain running without database or inter-server connection errors.** This passes the startup check for this chapter; a game login still requires the client setup in the next chapter.

[Next: Set up the RO client](03-client.md)

## Image sources

Installer images are from the Microsoft and MariaDB official sites and documentation linked above. The red-box field guide was created for this guide.

## License and use

Original teaching text and original diagrams, to the extent the author holds copyright in them, are licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You may share and adapt this material for noncommercial purposes. Credit **rayjhih8263**, link to this repository and the license, and indicate changes. Shared adaptations must use the same license. Commercial use, including selling bundles, paid downloads, or inclusion in paid teaching materials, requires separate permission from the rights holder.

Third-party software, game assets, trademarks, screenshots and images are excluded from this license and remain subject to their respective rights and licenses. This is an unofficial educational guide. Attribution and an educational purpose do not replace permission. See [the license notice](../../LICENSE.md).
