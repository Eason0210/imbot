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

### Windows OS
Install `im-select`
[im-select](https://github.com/daipeihust/im-select) can be used as a drop-in replacement of macism in Microsoft Windows.

However, because even though im-select supports switching different input languages, it does not support multiple input methods in the same lanuage, thus you should ensure that in each input language there is only one input method.

### Mac OS
Install `macism`

```
brew tap laishulu/macism
brew install macism
```
### Linux OS
Install `fcitx-remote`

# Configure
The mode is designed carefully, so it's safe to enable for all buffers even
its all in English.


``` emacs-lisp

(require 'imbot)

;; For Mac OS with Rime

(when (eq system-type 'darwin)
  (setq imbot-command "macism")
  (setq imbot-arg-cn "im.rime.inputmethod.Squirrel.Rime")
  (setq imbot-arg-en "com.apple.keylayout.ABC"))

(when (eq system-type 'gnu/linux)
  (setq imbot-command "fcitx-remote")
  (setq imbot-arg-cn "-o")
  (setq imbot-arg-en "-c"))

(imbot-mode)

```
