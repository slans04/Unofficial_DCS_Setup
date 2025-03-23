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

The most likely cause is that your antivirus is interfering with the game files. Files in game often get mistakenly flagged as malicous, in DCS' case the most commonly affected are `.dll` files.
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

# Diagnostic tools

## Using log files

Your crashlogs, `dcs.log-12345678-123456.zip`, (`C:\Users\<user>\Saved Games\DCS\Logs`) files are generated when you game crashes, and includes additional data. Find a crashlog that was generated at the time your game crashed (replicate the crash if you need to be sure).

If it seems to be failing to generate a proper crashlog then the file `dcs.log` records data about your last session, provided you haven't re-opened the game since the crash occurred. If you have file extensions hidden, your `dcs.log` will instead simply be called `dcs`, for example.

You can read the log manually if you wish, but this may be difficult since the log contains many red-herrings (things that look bad, but are actually normal). If you do try this, look for the start of the stack trace, indicated by the line `ERROR   APP (Main): Stack trace:`; this is where the game realised it had crashed and decided to store as much information as it could.

The [official "DCS by Eagle Dynamics" Discord server](https://discord.gg/YtZZwkxz) has a [log-analyser](https://discord.com/channels/542985647502393346/1179171301651402802) channel, in which Special K's bot operates. You can send [log files](https://slans04.github.io/Unofficial_DCS_Setup/pages/Common%20Troubleshooting.html#using-your-log-file) to that channel, and the bot will respond in order to assist with troubleshooting. It can provide other technical advice too, such as suggested settings. In fact, you wouldn't be reading this if it wasn't for their dedication.

If you find yourself stuck, despite this guide, you're welcome to ask for pointers in the [help-room](https://discord.com/channels/542985647502393346/551106084157390874) on that same Discord server.

> Of course, the official Eagle Dynamics support can be reached either by [creating a ticket](https://www.digitalcombatsimulator.com/en/support/), or by emailing them at `support@digitalcombatsimulator.com` or `eagledynamics.service@gmail.com`.

## Using DxDiag reports

Sometimes a log from the game isn't enough; the game may fail to realise it's crashing or the crash might be totally unrelated to the game. The `DxDiag.txt` can be generated in order to share more in-depth diagnostic  information regarding the device with others, including a small portion of the Windows Error Reporting. This in particular can be used to hone in on other issues with the device that may be affecting the game negatively.

These are often included automatically in crashlogs (`dcs.log-12345678-123456.zip`).

> [Generating a `DxDiag.txt`.](https://www.intel.com/content/www/us/en/support/articles/000022556/graphics.html)

# Troubleshooting checklist



# Common and identifiable crashes

