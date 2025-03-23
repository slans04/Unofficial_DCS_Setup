---
title: Common Troubleshooting
layout: home
nav_order: 4
---

1. TOC
{:toc}

# Authorisation Failed, DLC Disabled

## No numerical error codes

Check you're logged into an account which has a valid licence (either paid for or with an active trial) for the module that's been disabled.

The most likely cause is that your antivirus is interfering with the game files. Files in game often get mistakenly flagged as malicous, in DCS' case the most commonly affected files are `.dll`s.
1. Create a antivirus exclusion for the entire game install folder, `DCS World`.
2. Then, run a repair using the game's own repair tool (search "Repair DCS World" in your start menu) if you're using the standalone version (or if not, use Steam's "verify integrity of game files" feature).

> [Official DCS support link: Authorisation error](https://www.digitalcombatsimulator.com/en/support/faq/authorization/#3315427)

## Error code 403

This error code means your Steam account is linked to a DCS account, so you cannot use any of your DCS modules purchased from Steam in the Steam version of the game (since they're now to be used on the standalone version).

You can fix this issue either by; 
- Using the standalone version of the game with the account you linked your Steam account to.
- Or, by disconnecting the accounts from one another.

> [Official DCS support link: Error 403](https://www.digitalcombatsimulator.com/en/support/faq/steam/#3333133)

## Error code 500

The date and time on your PC need to be synchronised to the correct timezone for your network. You can synchronise your clock in Windows settings by right clicking on your clock and selecting "Adjust date/time".

If you're still recieving this error after synchronising, ask Google "what time is it", and set your clock to that time rather than your actual time. This may occur if you use a VPN, for example.

> [Official DCS support link: Error 500](https://www.digitalcombatsimulator.com/en/support/faq/authorization/#3314963)

## Other error codes

Error codes such as 203 may occur for various reasons, but you can attempt to fix them by flushing your DNS, and changing your DNS server to ones that are more likely to be up-to-date.

1. To flush your DNS, open "Command Prompt" (`cmd.exe`), and run the command `ipconfig /flushdns`.
2. A good DNS server to use would be `8.8.8.8`, with the alternate set to `8.8.4.4`. These are Google's Public DNS servers.

# Game is running badly or crashing

## Using your log file

Your crashlogs, `dcs.log-12345678-123456.zip`, (`C:\Users\<user>\Saved Games\DCS\Logs`) files are generated when you game crashes, and includes additional data. Find a crashlog that was generated at the time your game crashed (replicate the crash if you need to be sure).

> If it seems to be failing to generate a proper crashlog then the file `dcs.log` records data about your last session, provided you haven't re-opened the game since the crash occurred. If you have file extensions hidden, your `dcs.log` will instead simply be called `dcs`, for example.

You can read the log manually if you wish, but this may be difficult since the log contains many red-herrings (things that look bad, but are actually normal). If you do try this, look for the start of the stack trace, indicated by the line `ERROR   APP (Main): Stack trace:`; this is where the game realised it had crashed and decided to store as much information as it could.

The [Official "DCS by Eagle Dynamics" Discord server](https://discord.gg/YtZZwkxz) has a [log-analyser](https://discord.com/channels/542985647502393346/1179171301651402802) channel, in which Special K's bot operates and can assist with troubleshooting and can provide other technical advice. In fact, you wouldn't be reading this if it wasn't for their dedication.

If you find yourself stuck, despite this guide, you're welcome to ask for pointers in the [help-room](https://discord.com/channels/542985647502393346/551106084157390874) on that same Discord server.

> Of course, the official Eagle Dynamics support can be reached either by [creating a ticket](https://www.digitalcombatsimulator.com/en/support/), or by emailing them at `support@digitalcombatsimulator.com` or `eagledynamics.service@gmail.com`.

### Common identifiable crashes
<details>
  <summary>Aircraft mods</summary>
  
```
ERROR   APP (Main): Stack trace:
INFO    EDCORE (Main): try to write dump information
INFO    EDCORE (Main): # -------------- 20250323-050035 --------------
INFO    EDCORE (Main): DCS/2.9.14.8222 (x86_64; MT; Windows NT 10.0.26100)
INFO    EDCORE (Main): 
INFO    EDCORE (Main): # C0000005 ACCESS_VIOLATION at 00007ff6fbf5f471 00:00000000
INFO    EDCORE (Main): SymInit: Symbol-SearchPath: 'C:\Program Files\Eagle Dynamics\DCS World\bin-mt;', symOptions: 532, UserName: '<user>'
INFO    EDCORE (Main): OS-Version: 10.0.26100 () 0x300-0x1
INFO    EDCORE (Main): 0x00007ff6fbf5f471 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000095daefd320 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000095daeff550 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x000000000114c1a8 (DCS): SW + 0xB35E88
INFO    EDCORE (Main): 0x0000025d05a6eaf8 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x0000000000000001 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000095daefb8a0 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0xffffff6a2510479f ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000095daefb860 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000095daefbed0 ((module-name not available)): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x0000000000004160 (VCRUNTIME140_1): __CxxFrameHandler4 + 0x1F0
INFO    EDCORE (Main): 0x0000000000002572 (VCRUNTIME140_1): (function-name not available) + 0x0
INFO    EDCORE (Main): 0x00000000001238c6 (ntdll): RtlCaptureContext2 + 0x4A6
INFO    EDCORE (Main): 0x00000000026109fc (DCS): AmdPowerXpressRequestHighPerformance + 0x11319F8
INFO    EDCORE (Main): 0x00000000010a64be (DCS): SW + 0xA9019E
INFO    EDCORE (Main): 0x000000000002e8d7 (KERNEL32): BaseThreadInitThunk + 0x17
```

</details>


## Typical troubleshooting path

I would advise testing after each step you take, so you can be more aware as to what caused the issue once you manage to fix it, should it occur again.

### Step 0: Lucky guesses

- Check you have plenty of free space on your storage devices. This is important because below 10% free space, your computer will no longer automatically assign disk space to your pagefile. This can lead to your PC running out of memory.
- Install/update/repair your [Visual C++ Redistributables](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version) version; X64 for 64bit machines. Restart your PC afterwards.

### Step 1: Restoring game files

- Remove (or disable, if using a mod manager) any and all mods you've installed, both in the main install folder `DCS World` and in the `Saved Games\DCS` folder.
- Delete the shader cache folders; `fxo` and `metashaders2`, from within the `Saved Games\DCS` folder. These can become old and require regenerating. It's a good idea to do this every time you update the game, update your graphics drivers, or have some issues with the game.
- Delete the temporary files, `%temp%\DCS` and `%localAppData%\DCS`. This is rarely required but is generally worthwhile, just to be safe.
- Run a repair of the game files, using the game's own repair tool (search "Repair DCS World" in your start menu) if you're using the standalone version (or if not, use Steam's "verify integrity of game files" feature).

Your game files are now largely restored to how they were when you downloaded the game, with the exception of the contents of the `Saved Games\DCS` folder.

- As a somewhat more extreme (but often required) step is to rename the `Saved Games\DCS` folder (to something such as `DCS.old`, for example). This will preserve all your settings, controls, missions, ect, in the renamed folder, but force the game to generate a new one for you when you next load it. After doing this, your game should be entirely as it was when you first downloaded it. This step might be particularly important if the crashlog seems to point to files inside these folders.

### Step 2: 
