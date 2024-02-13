# User SystemD Units

## Replace Plasma's default window manager with i3wm.

Unit files:

- plasma-i3.service
- plasma-kwin-x11.service -> /dev/null

The service execs i3 during Plasma's startup. The soft link to /dev/null prevents Plasma from starting the default window manager. You'll need to `systemctl --user start plasma-i3` before this will work.

## Background image changing.

Unit files:

- background_change.timer
- background_change.service

Use `feh` to change your background every so often. You can change the period in the service file.

`systemctl --user start background_change.timer`

## Emacs service file

This is pulled verbatim from emacs' own ~/.emacs.d.

Unit files:

- emacs.service

`systemctl --user start emacs`
