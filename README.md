#+TITLE: README

# About
 `imbot` is to switch native or OS input source (input method) smartly.

# Features
1. Ease the use of OS-native input source, no need to change use experience.
2. Ease the use of Emacs-native input source, for further compatibility.
3. Respect buffer/mode by proper input source.

# Install

Just install `imbot`

Put `imbot.el` to your load-path.The load-path is usually `/elisp/`.
It's set in your `/.emacs` like this:
```
(add-to-list 'load-path (expand-file-name "/elisp"))

```

## Windows OS
Install `im-select`

## Mac OS
Install `macism`

## Linux OS
Install `fcitx-remote`

# Configure
The mode is designed carefully, so it's safe to enable for all buffers even
its all in English.


``` emacs-lisp

(require 'imbot)

;; For Mac OS with Rime
(when (eq system-type 'darwin)
  (defun imbot--activate-im ()
    (call-process imbot-command nil nil nil "im.rime.inputmethod.Squirrel.Rime"))
  (defun imbot--deactivate-im ()
    (call-process imbot-command nil nil nil "com.apple.keylayout.ABC")))

(imbot-mode)

```
