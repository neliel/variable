---
title: How to delete all files in a folder exept some.
author: Sarfraz
date: June 5, 2012
tags: haskell
---

A really simple script. But you have to write it. Let me save you some minutes. You can even use it without knowing of haskell.

~~~{.haskell}
    ^_^ ( ~/Bureau ) $ cat delete_fcontent

    #!/usr/bin/env runhaskell

    import System.Directory
    import Data.List ((\\))

    delete file = do
       fi <- doesFileExist file
       if fi
         then removeFile file
         else removeDirectoryRecursive file

    ldel = (\\ [".", "..", ".git", "README.TXT", "COPYING.TXT"])

    main = getDirectoryContents "." >>= (\x -> mapM_ delete $ ldel x)
~~~

Compile it with:

    ghc -O2 --make delete_fcontent
