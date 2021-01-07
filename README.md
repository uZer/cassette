# minitel1b-av

A small AV minitel project

## Introduction

With [anee-molly](https://github.com/anee-molly), we've got a fascination for
old computers aesthetics. After digging into the performance [CBM 8032
AV](https://www.roberthenke.com/concerts/cbm8032av.html) by Robert Henke and
finding some old Minitel terminals on Le Bon Coin, we've decided to start our
own hacky Minitel AV project.

There are 3 implementation paths we can follow:

- **VideoTex:** Reusing the Minitel *as is*, with original protocol. As a
  former network engineer, this could be something fun to experiment with. But
  the poor performances, the amount of work, the modem dependency and the fact
  we don't see any way to animate the page content is a no-go for us.

- **Terminal:** Using the Minitel 1B's DIN interface ("prise
  péri-informatique", I'm french and is that even a word?) to connect a
  computer, and use the device as a simple Linux terminal. We would just need
  to build a small device to adapt the voltage of the DIN interface (12V?) to a
  standard serial / RS-232 port (5V).  The requirement is a minitel 1B, also
  called "bistandard" with `Fnct` and `Ctrl` keys. If we implement the computer
  part on a Raspberry Pi, we may also be able to use the GPIO pins. The problem
  with this implementation is the slow (but maybe acceptable) speed at which
  the chars would get displayed on the screen (for AV performance usage). The
  other limitation is that we wouldn't be able to display images / graphical
  environment on the screen, we are restricted to the term usage.

- **Screen and Keyboard:** We can maybe use the minitel as a keyboard and a VGA
  screen (with the original cathodic screen or a dirty LCD replacement), but it
  would require more electronic hacking. Our knowledges about electronics are
  very limited so I don't think it's the best solution for us, even if it's the
  one that allows the most flexible usage.

We chose to follow the **Terminal** option since it's the easiest for us, and
the most respectful of the hardware without having too much limitations.

This repository is here to share our research about the subject.

**Disclamer:** We are not professional and just hobbyists working on this
project on ou spare time. Feel free to open PR or issues to improve the content
and fix misleading or false information we may have shared.

## Building

### Hardware

### Software

## Development of the AV tools

TBD

## License

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
