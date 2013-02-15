---
title: Add "open with emacs" in the explorer menu.
author: Sarfraz
date: February 14, 2013
---

I recently switched from vim to emacs. You see I began programming by learning Scheme and now I am doing Common Lisp.
And since it boil down to these two in flaming editor wars, I thought I'd give it a shot.
Since before I used *nix OS. But recently I began working on win32 machines.
The instalation is pretty simple. But it lacks integration.
Since you can open anything with those swiss army knives I just added a "open with" menu.

~~~~~~~~~~~~~~~~~~~~~~~~~ { .dos }

    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\*\Shell\Open In Emacs\Command]
    @="\"C:\\Program Files (x86)\\emacs-24.2\\bin\\emacsclientw.exe\" -a \"C:\\Program Files (x86)\\emacs-24.2\\bin\\runemacs.exe\" \"%1\""x

~~~~~~~~~~~~~~~~~~~~~~~~~

Be sure to correct tha path that lead to your emacs folder.

Put that snippet in a file with the .reg extension.
Right click and merge.
Voila, du travail de pro!
