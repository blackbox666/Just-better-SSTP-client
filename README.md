# Just better SSTP

**English** · [Русский](README.ru.md)

An SSTP VPN client for Windows. Choose which traffic goes through the VPN and connect to several networks at once, even when they use the same private addresses. The interface is currently in Russian.

**[Download 0.1 for Windows x64 →](https://github.com/blackbox666/Just-better-SSTP-client/releases/tag/v0.1)**

![Just better SSTP with demo profiles](desktop.png)

- Control each VPN connection independently.
- Choose a full IPv4 tunnel, private networks only, or specific routes.
- Assign automatic or manual aliases to overlapping remote subnets.
- Import Windows SSTP profiles, store credentials securely on your device, and create encrypted backups.
- Discover devices on the configured networks of a connected profile.
- Drag profiles to reorder them. The app remembers their order, routing switches, and window placement.
- View incoming and outgoing traffic in bytes, KB, MB, GB, and larger units.

## Getting started

1. Open [release 0.1](https://github.com/blackbox666/Just-better-SSTP-client/releases/tag/v0.1), download `Just-better-SSTP-0.1-windows-x64.zip` from **Assets**, and extract the entire archive.
2. If the Visual C++ runtime is missing, install the [Microsoft Visual C++ Redistributable x64](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/).
3. Run `sstp_client.exe` as administrator so the app can create the VPN adapter and configure routes.
4. Add a profile or choose **Settings → Import from Windows** (**Настройки → Импорт из Windows**). Then connect to the profile.

Windows import reads the system VPN profiles on this PC. Enter the username and password at the first connection. A Windows profile with the **Automatic** tunnel type can be imported as SSTP after confirmation if the server supports SSTP.

**Automatic mode** uses the remote subnet from the profile and chooses the visible alias. Turn it off to use the saved manual alias in **Selected addresses**. **Private networks only** takes precedence over profile routes and aliases, including when automatic mode is on.

## Move profiles to another PC

1. Open **Settings → Store profiles in the app folder** (**Настройки → Хранить профили в папке приложения**) and set a password. The app saves your current profiles and future changes in the encrypted `sstp-profiles.sstpvault` file next to `sstp_client.exe`.
2. Close the app and copy the entire folder, including the `.sstpvault` file, to the other Windows PC.
3. Launch `sstp_client.exe`, select **Open profiles** (**Открыть профили**), and enter the same password.

The Windows x64 build is unsigned and was tested on Windows 10. Builds for macOS, iOS, and Windows ARM64 are pending. This repository distributes ready-to-run builds.

Report bugs in [Issues](https://github.com/blackbox666/Just-better-SSTP-client/issues). Keep passwords, backup files, and private server details out of reports.
