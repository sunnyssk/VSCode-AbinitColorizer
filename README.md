# AbC README

This is the README for Abinit Colorizer (AbC) 0.1.0.

This version is designed to work with Abinit 8.0.7, while it should be able to cover several past or incoming versions.

The extension is built with [Yeoman generator](https://code.visualstudio.com/docs/tools/yocode).

## Installation

For installation, download the entire repository and paste it under<br/>
<font face=Consolas color=#fcc>%UserRoot%\\.vscode\\extensions.</font>

Or clone the repository directly to the target folder.

## Features

This plugin can highlight comments and internal variables in input and output files for abinit.

The plugin can change the edit mode to 'Abinit' automatically for files with "*.abi# AbC README

## Variables

For there are not much grammar related with abinit users, the colorizer mainly focuses on colorizing the variables in different types. Note that all colors are presented using the tokens provided with VS Code, which means it could not be controlled directly and might change between different themes.

The colorizer is currently using simple while a little lengthy regular expressions to work, which might lead to some errors on entering untypical inputs.

The variables are sorted as given on the website of Abinit. See [Main ABINIT code, input variables](http://www.abinit.org/doc/helpfiles/for-v8.0/input_variables/html_automatically_generated/allvariables.html) .

* Basic variables, <font color=#9CDCFE>VARBAS</font>. e.g. <font face=Consolas color=#9CDCFE>accuracy</font>.
* Developper variables, <font color=#569CD6>VARDEV</font>. e.g. <font face=Consolas color=#569CD6>builtintest</font>.
* Electron-Phonon variables, <font color=#56a>VAREPH</font>. e.g. <font face=Consolas color=#56a>asr</font>.
* Finite field and polarization variables, <font color=#D7BA7D>VARFF</font>. e.g. <font face=Consolas color=#D7BA7D>atvshift</font>.
* Files handling variables, <font color=#dd9>VARFIL</font>. e.g. <font face=Consolas color=#dd9>get1den</font>.
* Geometry builder + symmetry related variables, <font color=#f77>VARGEO</font>. e.g. <font face=Consolas color=#f77>brvltt</font>.
* Other ground state variables, <font color=#3eb>VARGS</font>. e.g. <font face=Consolas color=#3eb>algalch</font>.
* GW variables, <font color=#cd9731>VARGW</font>. e.g. <font face=Consolas color=#cd9731>awtr</font>.
* Internal variables, <font color=#666>VARINT</font>. e.g. <font face=Consolas color=#666>kptns</font>.
* Parallelisation variables, <font color=#dd9>VARPAR</font>. e.g. <font face=Consolas color=#dd9>autoparal</font>.
* Projector-Augmented Wave variables, <font color=#f77>VARPAW</font>. e.g. <font face=Consolas color=#f77>bxctmindg</font>.
* Response Function variables, <font color=#c6f>VARRF</font>. e.g. <font face=Consolas color=#c6f>bdeigrf</font>.
* Structure optimization variables, <font color=#f33>VARRLX</font>. e.g. <font face=Consolas color=#f33>adpimd</font>.
* Wannier90 interface variables,<font color=#ddd>VARW90</font>. e.g. <font face=Consolas color=#ddd>w90iniprj</font>.

## About Comments

Though not required by abinit itself, it is strongly recommended to comment after '#' followed with one blank character, if not the entire line.

This is because the output file includes several '#' which have no relation with comment at all.

As comments might take up a majority of the contents of the input file, the colorizer does not render the comment as usual if the comment does not take up the entire line. By typing two adjacent sharps rather than one ('##') you can force the colorizer to render the comment.

For comments taking up an entire line, things are opposite: they are automatically rendered, but another '#' in the same line could stop this rendering for following words.

## Accentuates

Three kinds of tokens are provided for the colorizer to render the contents inside of it regardless of its meaning:

<font face=Consolas color="#cd9731">[[Your Text]]</font>

The block will be rendered in warning style (orange for default theme).

<font face=Consolas color="#f33">\*\*Your Text\*\*</font>

The block will be rendered in error style (red for default theme).

<font face=Consolas color="#666">&lt;</font><font face=Consolas color="#316bcd">Your Text</font><font face=Consolas color="#666">&gt;</font> (input)

<font face=Consolas color="#666">&lt;</font><font face=Consolas color="#316bcd">Your</font><font face=Consolas> Text</font><font face=Consolas color="#666">&gt;</font> (output)
    
For output, first word (including '_' ) will be rendered in info style (blue for default theme) and the rest part will be shown in plain text style.
For input files, all words inside the tag would be rendered.

With the feature that not all comments will be rendered in "comment" form, it could help to accentuate certain parts of the input files.

## Release Notes

### 0.1.0

Initial release of Abinit Colorizer.

Provide with colorization of input, output and log files.
*", "*.abo*" and "*.ablog*" suffixes.
