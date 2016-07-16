![Background Music icon](Images/README/icon.png)

# ⚠⚠⚠⚠ Work in progress, this doesn't work yet! ⚠⚠⚠⚠
If you want a Mac version, try the original [Background Music](https://github.com/kyleneideck/BackgroundMusic).

#   Background Music for Windows
##### A Windows version of the macOS/OS X audio utility

todo: add screenshot here

- Automatically pauses your music player when other audio starts playing and unpauses it afterwards
- Per-application volume, boost quiet apps
- No restart required to install
- Record system audio

## Auto-pause music

Background Music can pause your music player app when other audio starts playing and unpause it afterwards. The idea is
that when I'm listening to music and pause it to watch a video or something I always forget to unpause it afterwards. So
this keeps me from wearing headphones for hours listening to nothing.

## Supported music players

None at the moment

## App volumes

Background Music has a volume slider for each app running on the system. I mostly use this to boost quiet apps above
their normal maximum volume.

## Recording system audio

Use [WASAPI](http://manual.audacityteam.org/man/tutorial_recording_computer_playback_on_windows.html#wasapi) or something

## Install

Work in progress

MSI installer

Or use a zip file

## Known issues (test on Windows)

- VLC automatically pauses iTunes/Spotify when it starts playing something, but that stops Background Music from
  unpausing your music afterwards. To workaround it, open VLC's preferences, click `Show All`, go `Interface` > `Main
  interfaces` > `macosx` and change `Control external music players` to either `Do nothing` or `Pause and resume
  iTunes/Spotify`.

  Similarly, Skype pauses iTunes during calls. If you want to disable that, uncheck `Pause iTunes during calls` on the
  General tab of Skype's preferences.
- Plugging in or unplugging headphones when Background Music isn't running can silence system audio. To fix it, go to
  the Sound section in System Preferences, click the Output tab and change your default output device to something other
  than Background Music Device. Alternatively, you may Option+Click on the Sound icon in the menu bar to select a different output device.

  This happens when macOS/OS X remembers that Background Music Device was your default audio device the last time you last
  used (or didn't use) headphones.
- [A recent Chrome bug](https://bugs.chromium.org/p/chromium/issues/detail?id=557620) can stop Chrome from switching to
  Background Music Device after you open Background Music. Chrome's audio will still play, but Background Music won't be
  aware of it.
- Some apps play notification sounds that are only just long enough to trigger an auto-pause. The only workaround right
  now is to increase the `kPauseDelayMSecs` constant in `BGMApp/BGMAutoPauseMusic.mm`. That will make your music overlap
  the other audio for longer, though, so you don't want to increase it too much. See
  [#5](https://github.com/kyleneideck/BackgroundMusic/issues/5) for details.
- Plenty more. Some are in listed in TODO.md.

## License

Though the original Background Music is licensed under [GPL v2](http://choosealicense.com/licenses/gpl-2.0/) or [later](http://choosealicense.com/licenses/gpl-3.0/), this is a "clean-room reimplementation" of the original Background Music (i.e. I have never looked at the original code). This version is licensed under [the MIT License](http://choosealicense.com/licenses/mit/).
