---
title: How to delete all files in a folder exept some using haskell.
author: Sarfraz
date: June 5, 2012
---

A really simple script. But you have to write it. Let me save you some minutes. You can even use it without knowing of haskell.

~~~~~~~~~~~~~~~~~~~~~~~~~ { .haskell } 
    ^_^ ( ~/Bureau ) $ cat delete_fcontent

    import System.Directory

    filesNotToConsider :: [String]
    filesNotToConsider= [".", "..", "dbf.txt", ".git", "README.md", "INSTALL"]

    isNotHere :: [String] -> String -> Bool
    isNotHere list element = case list of [] -> True
                                          _  -> if element == (head list)
                                                then False
                                                else isNotHere (tail list) element

    filteredList :: [String] -> [String]
    filteredList = filter (isNotHere filesNotToConsider)

    typeDelete :: FilePath -> IO ()
    typeDelete file = do fileOrNot <- doesFileExist file
                          if fileOrNot
                          then removeFile file
                          else removeDirectoryRecursive file

    main :: IO ()
    main = getDirectoryContents "." >>= (\x -> mapM_ typeDelete (filteredList x))
~~~~~~~~~~~~~~~~~~~~~~~~~

Compile it with:

    ghc -O2 --make delete_fcontent

