# About

This plug-in implements a [macrostep](https://github.com/joddie/macrostep)
back-end powered by [geiser](https://www.nongnu.org/geiser/).

`geiser` does have built-in macro-expansion facilities, namely
`geiser-expand-*`. However, I find `macrostep`'s in-place expansions to be more
convenient than pop-up buffers.

# Usage

The main entry-point to this package is `macrostep-geiser-setup`. It sets-up the
various `macrostep` variables needed to provide `geiser`-backed macro expansion.
It can either be called interactively, or added to `geiser-mode-hook`:

```emacs-lisp
(use-package macrostep-geiser
  :after geiser-mode
  :config (add-hook 'geiser-mode-hook #'macrostep-geiser-setup))
```

Alternatively:

```emacs-lisp
(eval-after-load 'geiser-mode '(add-hook 'geiser-mode-hook #'macrostep-geiser-setup))
```