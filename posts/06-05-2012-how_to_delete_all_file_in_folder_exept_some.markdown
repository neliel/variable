---
title: How to delete all files in a folder exept some using haskell.
author: Sarfraz
date: June 5, 2012
---

A really simple script. But you have to write it. Let me save you some minutes. You can even use it without knowing of haskell.

~~~~~~~~~~~~~~~~~~~~~~~~~ { .haskell }
    ^_^ ( ~/Bureau ) $ cat delete_fcontent

    #!/usr/bin/env runhaskell

    import System.Directory
    import Data.List ((\\))

    filesNotToConsider :: [String]
    filesNotToConsider = [".", "..", ".git", "README.TXT", "COPYING.TXT"]

    filteredList :: [String] -> [String]
    filteredList x = x \\ filesNotToConsider

    typeDelete :: FilePath -> IO ()
    typeDelete file = do
      fileOrNot <- doesFileExist file
      if fileOrNot
        then removeFile file
        else removeDirectoryRecursive file

    main :: IO ()
    main = getDirectoryContents "." >>= (\x -> mapM_ typeDelete $ filteredList x)
~~~~~~~~~~~~~~~~~~~~~~~~~

Compile it with:

    ghc -O2 --make delete_fcontent
