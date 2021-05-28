# One-Key

We have installed too many Emacs plugins, if you bind a global key for each command, we have no global key can be used in a short time.

The goal of one-key.el is to call a set of commands with a global key, to save the resources of the global key.

# Install
Add the full path of one-key.el to your Emacs ```load-path```, then add the following to `init.el`:

    ```Elisp
    (add-to-list 'load-path "~/.emacs.d/site-lisp/one-key/")
    (require 'one-key)
    ```

# Define one-key menu

Define one-key function ```one-key-menu-magit```:

    ```Elisp
    (one-key-create-menu
     "MAGIT"
     '(
       (("s" . "Magit status") . magit-status+)
       (("c" . "Magit checkout") . magit-checkout)
       (("C" . "Magit commit") . magit-commit)
       (("u" . "Magit push to remote") . magit-push-current-to-pushremote)
       (("p" . "Magit delete remote branch") . magit-delete-remote-branch)
       (("i" . "Magit pull") . magit-pull-from-upstream)
       (("r" . "Magit rebase") . magit-rebase)
       (("e" . "Magit merge") . magit-merge)
       (("l" . "Magit log") . magit-log-all)
       (("L" . "Magit blame") . magit-blame+)
       (("b" . "Magit branch") . magit-branch)
       (("B" . "Magit buffer") . magit-process-buffer)
       (("D" . "Magit discarded") . magit-discard)
       (("," . "Magit init") . magit-init)
       (("." . "Magit add remote") . magit-remote-add)
       )
     t)
    ```

Then binding function ```one-key-menu-magit``` with one global key to call it.
