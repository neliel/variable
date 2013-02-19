---
title: Open in Emacs context menu in Windows.
author: Sarfraz
date: February 02, 2013
---

Create a file with a .reg extension.
Put the following in it:

~~~{.bash}
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\*\Shell\Open In Emacs\Command]
    @="\"C:\\Program Files (x86)\\Emacs-24.2\\bin\\emacsclientw.exe\" -a \"D:\\Program Files (x86)\\Emacs-24.2\\bin\\runemacs.exe\" \"%1\""
~~~

And then right-click merge it.
Voila!

PS: Be sure to correct the paths.
