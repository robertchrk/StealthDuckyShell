# StealthDuckyShell
StealthDuckyShell is a USB rubber ducky payload for Ubuntu systems. 
It installs a persistent Python reverse shell &amp; takes care of .bash_history.

##Prerequisites

[USB Rubber Ducky](https://edutech-hakshop.myshopify.com/products/usb-rubbery-ducky)

##Setup

It uses a Base64 encoded string to carry the backdoor script, just decode it and adjust IP address & port. A cronjob starts our reverse shell every 30 minutes, I think that's not too suspicious, but of course you can increase that. On Ubuntu 16.04 it's hard to get a reliable source of idle time, so I played with "xinput test-xi2 --root" to wait until the user is idle. Maybe I'll implement it later.

Everything you or your ducky types in a terminal window get's recorded in .bash_history, don't worry there's a workaround! Just append "&& history -d $((HISTCMD-1))" to every command to delete the current line.
