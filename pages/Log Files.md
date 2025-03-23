---
title: Log Files
layout: home
parent: Common Troubleshooting
nav_order: 2
---

1. TOC
{:toc}

# Using log files

Your crashlogs, `dcs.log-12345678-123456.zip`, (`C:\Users\<user>\Saved Games\DCS\Logs`) files are generated when you game crashes, and includes additional data. Find a crashlog that was generated at the time your game crashed (replicate the crash if you need to be sure).

> If you can't find your `Saved Games` folder, you can type `shell:savedgames` into either the address bar of your File Explorer, or the "Run" function (LWin+R).

If it seems to be failing to generate a proper crashlog then the file `dcs.log` records data about your last session, provided you haven't re-opened the game since the crash occurred. If you have file extensions hidden, your `dcs.log` will instead simply be called `dcs`, for example.

You can read the log manually if you wish, but this may be difficult since the log contains many red-herrings (things that look bad, but are actually normal). If you do try this, look for the start of the stack trace, indicated by the line `ERROR   APP (Main): Stack trace:`; this is where the game realised it had crashed and decided to store as much information as it could.

The [official "DCS by Eagle Dynamics" Discord server](https://discord.gg/YtZZwkxz) has a [log-analyser](https://discord.com/channels/542985647502393346/1179171301651402802) channel, in which Special K's bot operates. You can send [log files](https://slans04.github.io/Unofficial_DCS_Setup/pages/Common%20Troubleshooting.html#using-your-log-file) to that channel, and the bot will respond in order to assist with troubleshooting. It can provide other technical advice too, such as suggested settings. In fact, you wouldn't be reading this if it wasn't for their dedication.

If you find yourself stuck, despite this guide, you're welcome to ask for pointers in the [help-room](https://discord.com/channels/542985647502393346/551106084157390874) on that same Discord server.

> Of course, the official Eagle Dynamics support can be reached either by [creating a ticket](https://www.digitalcombatsimulator.com/en/support/), or by emailing them at `support@digitalcombatsimulator.com` or `eagledynamics.service@gmail.com`.

# Using DxDiag reports

Sometimes a log from the game isn't enough; the game may fail to realise it's crashing or the crash might be totally unrelated to the game. The `DxDiag.txt` can be generated in order to share more in-depth diagnostic  information regarding the device with others, including a small portion of the Windows Error Reporting. This in particular can be used to hone in on other issues with the device such as bluescreens.

These are often included automatically in crashlogs (`dcs.log-12345678-123456.zip`).

> [Generating a `DxDiag.txt`.](https://www.intel.com/content/www/us/en/support/articles/000022556/graphics.html)

# Troubleshooting checklist



# Common and identifiable crashes

