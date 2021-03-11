# About

This plug-in implements a [macrostep](https://github.com/joddie/macrostep)
back-end powered by [geiser](https://www.nongnu.org/geiser/).

`geiser` does have built-in macro-expansion facilities, namely
`geiser-expand-*`. However, I find `macrostep`'s in-place expansions to be more
convenient than pop-up buffers.

# Set-up

The main entry-point to this package is `macrostep-geiser-setup`. It sets-up the
various `macrostep` variables needed to provide `geiser`-backed macro expansion.
It can either be called interactively, or added to `geiser-mode-hook`:

```emacs-lisp
(use-package macrostep-geiser
  :after geiser-mode
  :config (add-hook 'geiser-mode-hook #'macrostep-geiser-setup))

(use-package macrostep-geiser
  :after geiser-repl
  :config (add-hook 'geiser-repl-mode-hook #'macrostep-geiser-setup))
```

Alternatively:

```emacs-lisp
(eval-after-load 'geiser-mode '(add-hook 'geiser-mode-hook #'macrostep-geiser-setup))
(eval-after-load 'geiser-repl '(add-hook 'geiser-repl-mode-hook #'macrostep-geiser-setup))
```

Additionally, this package can also integrate with `cider-mode`:

```emacs-lisp
(use-package macrostep-geiser
  :after cider-mode
  :config (add-hook 'cider-mode-hook #'macrostep-geiser-setup))
```

Alternatively:

```emacs-lisp
(eval-after-load 'cider-mode '(add-hook 'cider-mode-hook #'macrostep-geiser-setup))
```

# Usage

If `macrostep-geiser` is properly set up, `macrostep` will expand macros using
the REPL. `macrostep-geiser-expand-all` expands the macro at point recursively.
`macrostep-geiser-expand-all-mode` makes `macrostep` itself also recursively
expand macros.
