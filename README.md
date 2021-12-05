# LTT Linux daily driver challenge issues

A list of issues Linus and Luke experienced during the LTT Linux Daily Driver Challenge,
along with several observations from a stupid person named iczero.

## The issues

Note: Some of these may be subjective, and some may have been fixed without my knowledge.

### Part 1

- [ ] [Searching "Best Linux distro for gaming" on Google brings up really bad websites.](https://www.youtube.com/watch?v=0506yDSgU7M&t=67s)
  - **Possible fix:** Make some good lists and use SEO to get them to show first.
  - Note(iczero): This is unfortunate and I don't think it'll be easily fixable, especially since most Linux users can't agree on this anyways.
- [ ] [The Mint USB behaved strangely with Luke's monitors the first time.](https://youtu.be/0506yDSgU7M?t=398)
  - Note(iczero): Most likely a nvidia issue. Can be mitigated but unlikely to get fixed unless nvidia does something about it (which they are
    quite frankly known to _not_)
- [ ] [Mouse acceleration is on by default.](https://youtu.be/0506yDSgU7M?t=541)
  - **Possible fix:** Turn it off by default.
  - Note(iczero): Highly subjective. Most users prefer mouse acceleration. I don't believe this is an issue.
- [ ] [GoXLR acts as an input when configured as an output device.](https://youtu.be/0506yDSgU7M?t=552)
  - Note(iczero): Without vendor support this is unlikely to get fixed without significant community effort (reverse engineering, etc).
    At least nvidia shows willingness to support Linux, the GoXLR vendor has not.
- [ ] [Pop!\_OS doesn't have a noob-friendly way of checking what hardware is connected and whether the drivers work.](https://youtu.be/0506yDSgU7M?t=579)
  - **Possible fix:** Make it ship with Hardinfo installed.
  - Note(iczero): Simple fix but probably not necessary for most users. Up to distro maintainers.
- [x] [Installing Steam uninstalls essential packages and it isn't clear that this is bad.](https://youtu.be/0506yDSgU7M?t=607) ([Fix](https://github.com/pop-os/apt/pull/1))
  - Note(iczero): This was a temporary issue with Pop and likely existed for less than a day at most.
    It may be better to introduce an apt configuration value to explicitly prevent uninstalling essential packages.
- [ ] [USB errors on boot.](https://youtu.be/0506yDSgU7M?t=870)
  - Note(iczero): Splash screen (`plymouth(8)`) should cover this, and usually does. I'm not sure why plymouth didn't start.
    I haven't encountered this myself with any recent distro.
- [ ] [Installing Steam from Mint Software Manager shows "Removing...".](https://youtu.be/0506yDSgU7M?t=921)
  - Note(iczero): GUI package managers overall need much love. Unfortunately they're often neglected simply because
    most users don't use them anyways.
- [ ] [Linus doesn't like KDE Plasma's settings design.](https://youtu.be/0506yDSgU7M?t=982)
  - Note(iczero): Not an issue. KDE is not Windows. There are several other desktop environemnts available (though I prefer KDE).
- [ ] [The check boxes under "Hardware Configuration" look like radio buttons.](https://youtu.be/0506yDSgU7M?t=991)
  - Note(iczero): Likely a simple fix. That UI looks like it was thrown together rather quickly.
- [ ] [Cave Story+ looks weird.](https://youtu.be/0506yDSgU7M?t=1101)
  - Note(iczero): Likely an issue with either wine or proton. Valve is doing great work on this, chances are
    they'll fix it soon. Valve should really be thanked for their work on wine.
- [ ] [Linus's controller doesn't work in Cave Story+.](https://youtu.be/0506yDSgU7M?t=1105)
  - Note(iczero): This may be an issue with Steam and device permissions. Steam seems to silently eat such errors,
    only showing them on the console.

### Part 2

- [ ] [Using apt or apt-get on Manjaro doesn't warn you that you're using the wrong package manager.](https://youtu.be/3E8IGy6I9Wo?t=107)
  - **Possible fix:** Maybe command-not-found can show a warning for it?
  - Note(iczero): Not an issue. Running `msiexec` on Mac OS X doesn't get you a special error and quite frankly shouldn't.
    I'm not sure why this is even a complaint; most users would not jump straight to the terminal, and even if they did,
    a quick Google search yields several results pointing to `pacman`.
- [ ] [NVENC doesn't show up as an option in OBS.](https://youtu.be/3E8IGy6I9Wo?t=160)
  - Note(iczero): This has never been an issue for me. I'm not sure how they got that.
- [ ] [NVIDIA X Server Settings is lacking.](https://youtu.be/3E8IGy6I9Wo?t=183)
  - Note(iczero): Again, vendor issue with nvidia.
- [ ] [OBS requires a restart (or something) for some things to work correctly, but doesn't say so.](https://youtu.be/3E8IGy6I9Wo?t=224)
  - Note(iczero): Again, this has never been an issue for me.
- [ ] [The option to show Snap, Flatpak, and AUR packages in Pamac is "hidden".](https://youtu.be/3E8IGy6I9Wo?t=540)
  - Note(iczero): They're really not "hidden". They're in the standard settings menu and clearly visible.
- [ ] [Scrolling with the mouse wheel in KDE's volume mixer applet scrolls through both devices and levels of devices.](https://youtu.be/3E8IGy6I9Wo?t=573)
  - Note(iczero): This could be a toggle in settings, but it's standard functionality in KDE. Scrolling on the scroll bar
    will scroll the audio device list.

### Part 3

- [ ] [The "Moving" Dolphin notification is easy to miss on a large screen.](https://youtu.be/TtsglXhbxno?t=163)
  - **Possible fix:** Hide the file (dot prefix) until it's done moving.
  - Note(iczero): I'm not too sure how Linus managed to miss the notification, but a tip for new users on the
    placement of the progress notification may be helpful.
- [ ] [Okular's dialog about "no available signing certificates" refers to a manual, which Linus completely ignored for some reason.](https://youtu.be/TtsglXhbxno?t=281)
  - Note(iczero): Digital signatures are completely different from ordinary signatures. If Linus followed that guide
    to the end, he would have a PKI certificate from a CA and would have gotten nowhere. Okular has annotation features
    rather visible in the menu bar. A warning on the digital signature box may be useful.
- [ ] [LibreOffice Calc didn't export the bottom and right edges of a chart.](https://youtu.be/TtsglXhbxno?t=440) [Sgt-Miller](https://github.com/Sgt-Miller) says it did for them.
  - Note(iczero): Works for me.
- [ ] [You can't drag a folder of fonts onto Linux Mint's font previewer to install them.](https://youtu.be/TtsglXhbxno?t=455)
  - Note(iczero): I really don't think this is an issue, but implementing it shouldn't be too hard.
- [ ] [Something about Ark?](https://youtu.be/TtsglXhbxno?t=499)
  - Note(iczero): I have tried exactly what Linus tried in that video and Ark extracted a file into a subdirectory in
    Dolphin with no issues whatsoever. He may have missed the target folder. I think he's a bit too quick to blame
    Dolphin for all his issues.
- [ ] [Compression appears to finish instantly when, in fact, it does not.](https://youtu.be/TtsglXhbxno?t=732)
  - **Possible fix:** Hide the archive (dot prefix) until it's done compressing.
  - Note(iczero): He again missed the progress indicator in the notification area.
- [ ] [Right-click drag doesn't work in Dolphin.](https://youtu.be/TtsglXhbxno?t=1024)
  - Note(iczero): Dolphin (and KDE) are not in fact Windows. I don't believe this is an issue. Dolphin already
    provides similar functionality for plain drag-and-drop.
- [ ] [Fullscreen doesn't work in MPlayer.](https://youtu.be/TtsglXhbxno?t=1234)
  - Note(iczero): I shall shill mpv.
- [ ] [Window movement in Mint while a game is open is laggy.](https://youtu.be/TtsglXhbxno?t=1294)
  - Note(iczero): This is fixed under Wayland. Unfortunately, Wayland breaks a lot more than it fixes. I expect
    Wayland will eventually reach feature parity with X but it is currently simply not there yet. The Steam Deck was
    announced to use Wayland so this shouldn't be an issue on SteamOS 3.0.
- [ ] [Dolphin refuses to work as root.](https://youtu.be/TtsglXhbxno?t=1496)
  - Note(iczero): KIO/PolicyKit integration is in the works and this should be fixed soon.

### WAN show

- [ ] [The "show desktop" button in KDE doesn't minimize all windows by default.](https://youtu.be/fJB9fdXWiiw?t=497)
  - **Possible fix:** Replace it with the "Minimize all Windows" applet.
  - Note(iczero): Again, KDE is not Windows. I prefer the KDE behavior.
- [ ] [The application names don't represent the jobs of those applications (e.g. "Kate").](https://youtu.be/fJB9fdXWiiw?t=702)
  - **Possible fix:** Put the applications' descriptions in parentheses next to their names (e.g. "Kate (text editor)").
  - Note(iczero): This already exists. In the application launcher or krunner, descriptions of applications are already
    shown.
- [ ] [Luke's system locks up when his TV turns on.](https://youtu.be/sS25mCLyQyk?t=416)
  - Note(iczero): Unfortunately, likely yet another nvidia issue. See above.

## Some other suggestions for developers based on this challenge

- [ ] [Sgt-Miller](https://github.com/Sgt-Miller)
  > If Fastboot is turned on in Windows, the partition is mounted as read-only in Ubuntu. When copying, the error message says "no permission". Please make the error message more descriptive, like for NTFS systems it can say "It was mounted in read-only mode. To write to disk, ensure fast boot is disabled.
- [ ] [Sgt-Miller](https://github.com/Sgt-Miller)
  > Please turn on "Create link" option in Nautilus by default. Or provide creating shortcut by drag+ctrl+shift.
- [ ] [Sgt-Miller](https://github.com/Sgt-Miller)
  > I think gnome-tweaks should be installed by default. User shouldn't have to install an extra tool to change system fonts and to create startup programs.

## Contributing

If you have a fix for one of these issues or you can describe it better than is described here, please [create an issue](https://github.com/glibg10b/ltt-linux-challenge-issues/issues/new/choose) or submit a pull request.

## Other users' experience

- [#1](https://github.com/glibg10b/ltt-linux-challenge-issues/issues/1)
