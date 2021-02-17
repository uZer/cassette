# minitel-av

A small Audio Visual Minitel project.

This repository is here to share some research on an audio-visual multiscreen
audio-reactive setup, using obsolete devices like the Minitel. It contains
resources and explanations that may help you build a similar project.

We are not professionals, just hobbyists working on this project on our spare
time. Feel free to open PR or issues to improve the content and fix misleading
or false information we may have shared.

## Introduction

With [anee-molly](https://github.com/anee-molly), we've got a fascination for
old computers aesthetics. After digging into the [CBM 8032
AV](https://www.roberthenke.com/concerts/cbm8032av.html) performance by Robert
Henke and finding some old Minitel terminals on Le Bon Coin, we've decided to
start our own hacky Minitel AV project.

There is at least 3 implementation paths for Minitel revival:

- **VideoTex:** Reusing the hardware *as is*, with its original protocol. This
  could be something fun to experiment with. However, due to the poor
  performances, the amount of work (you have to actually host the Minitel
  services / network), and the fact there is no fast-enough way to render an
  animated page content, this is probably a no-go for an AV setup. You can find
  this [great talk by Frédéric Bisson at FOSDEM
  2020](https://fosdem.org/2020/schedule/event/retro_reviving_minitel/) about
  the revival of old school Minitel, with a lot of interesting resources.

- **Terminal:** Using the Minitel 1B's / Minitel 2's DIN interface ("prise
  péri-informatique", I'm french and is that even a word?) to connect a
  computer, and use the device as a simple Linux terminal: display characters
  on the device's screen and use it's keyboard. The DIN in the back has to be
  converted to a standard serial interface. The hardware requirement for this
  is a "bistandard" Minitel with `Fnct` and `Ctrl` keys, and this [DIN -> RS232
  or DIN -> USB
  cable](http://jelora.fr/post/2020/02/25/Adaptateur-prise-DIN-peri-informatique-Minitel-vers-Serie-RS232-et-Serie-USB.html).
  If we implement the computer part on a Raspberry Pi, we may be able to use
  the GPIO pins, but in any case, a small voltage converter is needed. The
  problem with this implementation could be the slow speed at which the chars
  may get displayed on the screen (for AV performance usage). The other
  limitation is that you wouldn't be able to display images / graphical
  environment on the screen, we are restricted to the term usage. But it sounds
  like a creative limitation, which can be good!

- **Screen and Keyboard:** It is possible to use the device as a keyboard +
  composite screen (with the original cathodic screen or a dirty LCD
  replacement), but it would require more electronic hacking. It's the most
  flexible path, but also the hardest to build and the less respectful for the
  inital hardware.

We first chose to follow the **Terminal** option since it's the easiest for us,
without hiding too many restrictions. The "only-ASCII" constraint was actually
a pretty good creative limitation! But we realized afterwards that the serial
port speed of 4600 bauds (Minitel 1B) and 9600 bauds (Minitel 2) were too slow
for the usage we planned to do.

We had to fallback on the last implementation, **Screen and Keyboard**.

## Building

a) We didn't follow the **VideoTex** path.

b) Our aborted research on the **Terminal** implementation is described in [this
document](serial.md)

c) Our composite video implementation is WIP.

## License

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
