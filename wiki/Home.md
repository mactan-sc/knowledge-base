# Welcome, Space Penguins!

This wiki is a collection of information on how to run Star Citizen on Linux, as well as our tips and tricks!  
We welcome contributions. Feel free to fork this repo and submit a PR.  

🐧 Join us! https://robertsspaceindustries.com/orgs/LUG  

🗨 Discord: https://discord.gg/meCFYPj  
😎 Matrix space: https://matrix.to/#/#SCLUG:matrix.org  

## Contents
* [Quick-Start Guide](Quick-Start-Guide)
* [Manual Installation](Manual-Installation)
* [Troubleshooting](Troubleshooting)
* [Performance Tuning](Performance-Tuning)
* [Tips and Tricks](Tips-and-Tricks)
* [Sticks, Throttles, & Pedals](Sticks,-Throttles,-&-Pedals)
* [Head Tracking](Head-Tracking)

## News

### Game Updates
> [!tip]
> (Aug 24, 2024) **Launcher 2.0 Migration**
> - There are still some isses with the 2.0 launcher. The old launcher will continue to work while those issues get sorted out. If you want to try the 2.0 launcher anyway, you can use the steps below
> - Requires standard Wine 9.4+ or Proton GE 9-13+ runner
>   - Recent Wine versions can be easily installed from the Kron4ek runner source in the [LUG Helper](https://github.com/starcitizen-lug/lug-helper)
> - If using standard Wine, requires the latest git release of winetricks for the powershell patches
>   - Run `WINEPREFIX={your prefix} winetricks powershell` to install it
> - If using standard Wine, CLI mode must be enabled in Lutris
>   - Right click the game -> Configure -> System options -> CLI mode
> - Launcher 2.0 is unable to verify files. Use the install button instead for now
> - The 2.0 Launcher may need to be installed manually. See [our wiki](https://github.com/starcitizen-lug/knowledge-base/wiki/Troubleshooting#rsi-launcher-doesnt-auto-update) for instructions

> [!important]
> (Aug 23, 2024) **Vulkan Beta: Limited performance with KDE on Wayland**
> - Vulkan renderer on kde wayland may result in your [gpu utilisation being limited to less than 75%](https://bugs.kde.org/show_bug.cgi?id=492051), causing low framerates
>   - To fix: either use Gamescope, switch to another desktop, or run KDE's x11 session


### General News
> [!warning]
> (Sept 10, 2024) **Wine-staging crashes PTU**
> - We recommend using standard Wine instead of Wine-staging
> - Recent Wine versions can be easily installed from the Kron4ek runner source in the [LUG Helper](https://github.com/starcitizen-lug/lug-helper)

> [!note]
> (Sept 1, 2024) **`GE Proton (Latest)` is the new umu proton**
> - If you wish to use the new Proton integration in Lutris, see below for umu Proton migration steps
> - Note that [umu](https://github.com/Open-Wine-Components/umu-launcher/releases) has not yet seen a stable release
> - We currently recommend using either your `system Wine` or a standard Wine installed using [our Helper](https://github.com/starcitizen-lug/lug-helper)
> - If switching to standard Wine from a GE runner, CLI mode must be enabled in Lutris
>   - Right click the game -> Configure -> System options -> CLI mode

> [!tip]
> (Aug 25, 2024) **Lutris umu Proton/Protonfixes Migration**
> - Install Lutris v0.5.17 or later
> - Right click the game, select Configure, and then adjust settings as follows:
> - In System options, add the following environment variables:
>   - `EOS_USE_ANTICHEATCLIENTNULL: 1`
>   - `GAMEID: umu-starcitizen`
>   - `STORE: none`
>   - `PROTONPATH: GE-Proton`
> - Other environment variables can be updated/removed if desired by comparing against those set for a new install in our [install json](https://github.com/starcitizen-lug/lug-helper/blob/main/lib/lutris-starcitizen.json)
> - If using Lutris v0.5.17, in System options, add the following to "Command prefix":
>   - `GAMEID=umu-starcitizen STORE=none`
> - In System options, disable `CLI mode`
> - In Runner options, set Wine version to `GE-Proton (Latest)`
> - In Runner options, disable `Use system winetricks`

> [!warning]
> (May 4, 2024) **Game Crash on launch from main menu**
> - Linux kernel 6.8.9 can result in a crash when launching from main menu, may be accompanied by a popup including text "Assertion failed!"
>   - To fix: revert to kernel 6.8.8, update to 6.9+, or enable ReBar if your hardware supports it

> [!warning]
> (Jan 15, 2024) **Installer Error Code 256**
> - Lutris version [5.15 had a critical bug](https://github.com/lutris/lutris/releases/tag/v0.5.16)  preventing successful installations of games
>   - To fix: update to latest Lutris 5.17

> [!important]
> (Nov 11, 2023) **Failed to Initialize Dependencies**
> - If you are on a rolling release distro and using Gamescope, you may receive this error due to a bug in Gamescope v3.12.7. See [this Github issue](https://github.com/ValveSoftware/gamescope/issues/984) for more info.
>   - To fix: Install the git release of Gamescope or downgrade to 3.12.5 until the fix is released to stable.


### AMD News
> [!note]
> (Apr 29, 2024) **Vulkan Beta**
> - Bright flickering lights at edges of ingame RTT display panels
>   - To fix: Add environment variable `radv_zero_vram=true`


### Nvidia News
> [!warning]
> (Apr 29, 2024) **Vulkan Beta**
> - Game fails to launch with vulkan renderer enabled
>   - Use latest wine-GE 8-26+
>   - Add environment variable `WINE_HIDE_NVIDIA_GPU=1`
> - There is an [issue with LibCUDA](https://github.com/jp7677/dxvk-nvapi/issues/174#issuecomment-2227462795) that prevents DLSS from working on linux. See [instructions](https://github.com/starcitizen-lug/knowledge-base/wiki/Troubleshooting#dlssdeep-learning-super-sampling--vulkan) to patch libcuda to enable DLSS

> [!caution]
> (Oct 9, 2023) **Crash when taking shield damage in-game**
> - There is a shield rendering bug that causes the game to crash. It seems to affect 1000 series cards.
> - There is currently no known workaround other than switching cards. We recommend AMD.


### Easy Anti-Cheat
> [!note]
> (Feb 12, 2022) **Easy Anti-Cheat is live.**
> - CIG is aware of the problem but there is still no ETA. There are currently no consequences that we are aware of for using the workaround, but CIG has suggested that eventually people will be kicked for tripping EAC. The workaround is automatically configured for new installs through Lutris.
