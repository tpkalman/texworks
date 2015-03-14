This page documents some helpful features included in the TeXworks sources that are not documented elsewhere.



## Defining a root file ##

If you have your LaTeX code for one document distributed over several files this is for you. The problem is that only one document (the 'root document') contains all the commands necessary to be typeset (like `\documentclass` or `\begin{document}`). LaTeX will fail when run on any of the other files. To let TeXworks know that it should run LaTeX on that root file instead of the current one put the following line in the beginning of the file:
```
% !TEX root = path/to/root_file.tex
```

## Setting the (La)TeX engine per file ##

If you have a file that has to be compiled with another than the standard (La)TeX program and you don't want to have to set the program by hand every time you open the file put the following line in the beginning of the file:
```
% !TEX program = your_program
```
Note that /your\_program/ is the name you chose for the program in the settings, not the actual name of the executable.

## Setting the file encoding per file ##

If you put the following line in the beginning of a file, TeXworks will deal with special characters accordingly:
```
% !TEX encoding = your_encoding
```
For a complete list of supported encodings, please see the TeXworks settings.

## Setting the spell checking language per file ##

If you put the following line in the beginning of a file, TeXworks will set configure the spell checker for the corresponding language:
```
% !TEX spellcheck = language_tag
```
The language tag is typically a [IETF language tag](http://en.wikipedia.org/wiki/IETF_language_tag), but may depend on your spell checking software and your installed dictionaries. For a complete list of supported tags on your system, please refer to the TeXworks "Edit -> Spelling" menu.

## Using the outline and bookmarks in source files ##
If you activate the menu item Windows -> Show -> Tags, you will get a sidebar that displays the outline of the current source document by automatically locating the \part, \section, ... commands. By clicking on any of the items in the tag tree, the cursor will be positioned at the corresponding code in the editor.

_Note: This currently only works for LaTeX commands by default._

_Note: To customize the recognized patterns, edit the file tag-patterns.txt in your TeXworks resource directory_

In addition to the automatically detected commands, you can add a custom bookmark by inserting the line
```
%: My bookmark label
```
into the source code at the appropriate location.

## Using SyncTeX ##

[SyncTeX](http://itexmac.sourceforge.net/SyncTeX.html) by Jérôme Laurens provides a means for synchronization between input (i.e. (La)TeX) and output (i.e. pdf). You need a sufficiently new LaTeX engine to use its benefits (if your engine doesn't support it or its usage has been disabled you will see a note at the bottom of the preview window when you open a pdf). To use the synchronization, Ctrl-Click (Cmd-Click on Mac OS X) anywhere in your source file or the output to navigate to the corresponding place in the other window.

## Locating and customizing TeXworks resources ##

TeXworks comes with a lot of customziable configurations and templates, most notably [CodeCompletion](CodeCompletion.md), syntax highlighting and sectioning commands. All these are stored in plain text files in sub-directories of the TeXworks' resource directory. Depending on your operating system this directory is located in different locations:

| Windows XP    | `C:\Documents and Settings\<username>\TeXworks\` |
|:--------------|:-------------------------------------------------|
| Windows Vista | `C:\Users\<username>\TeXworks\` (?) |
| GNU/Linux     | `~/.TeXworks/` |
| Mac OS X      | `~/Library/TeXworks/` |

_Note: These are the standard settings. If you use a non-English version of your operating system or if you have changed the system's configuration the path on your system may differ._

_Note: TeXworks automatically creates the resource directory and its sub-directories if they don't exist, and installs a default collection of resources. You can restore these defaults (or update them for a new release) by removing the resource directories and then restarting the program._

To customize the behavior of TeXworks edit the plain text files contained in the sub-directories. Most of those files contain short comments on the purpose of the file and the syntax used.


---


_Thanks to Stefan Löffler for these notes._