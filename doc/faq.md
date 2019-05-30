# Frequently Asked Questions

* LaTeX in general
  * [Is there a Wikibook on LaTeX?](#is-there-a-wikibook-on-latex)
  * [How can I find LaTeX commands for symbols by drawing them?](#how-can-i-find-latex-commands-for-symbols-by-drawing-them)
  * [What is the difference between \centering and the `center` environment](#what-is-the-difference-between--centering-and-the-center-environment)
  * [How can I change the font size?](#how-can-i-change-the-font-size)
  * [Error: Cannot determine size of graphic](#error-cannot-determine-size-of-graphic)
  * [How can I make newlines or multiple lines in cells of some tabular?](#how-can-i-make-newlines-or-multiple-lines-in-cells-of-some-tabular)
* Bibliographies with BibTeX
  * [How can I add the bibliography section to the table of contents?](#how-can-i-add-the-bibliography-section-to-the-table-of-contents)
  * [How to cite an online source with BibTeX?](#how-to-cite-an-online-source-with-bibtex)
  * [How do I specify multiple authors in BibTeX?](#how-do-i-specify-multiple-authors-in-bibtex)
* TeXstudio
  * [How to enable line numbers?](#how-to-enable-line-numbers)
  * [How to configure git in TeXstudio?](#how-to-configure-git-in-texstudio)
* Texmaker
  * [Texmaker gives "command not found" errors](#texmaker-gives-command-not-found-errors)
* TeXnicCenter
  * [I don't have any output profiles configured in TeXnicCenter](#i-don-t-have-any-output-profiles-configured-in-texniccenter)
  * [Installing packages on-the-fly in TeXnicCenter does not work](#installing-packages-on-the-fly-in-texniccenter-does-not-work)
  * [TeXnicCenter gives an error "Cannot execute command"](#texniccenter-gives-an-error-cannot-execute-command)
  * [Configure Sumatra PDF with TexnicCenter](#configure-sumatra-pdf-with-texnicenter)
* Zotero
  * [How to change the language of Zotero GUI?](#how-to-change-the-language-of-zotero-gui)
* Bibliographic Databases
  * [Advanced search in the ACM Digital Library](#advanced-search-in-the-acm-digital-library)

## Is there a Wikibook on LaTeX?

[There certainly is](http://en.wikibooks.org/wiki/LaTeX)

## How can I add the bibliography section to the table of contents?

If you want to include a line for the bibliography in your table of content,
then you can try `\addcontentsline` (see [here](http://www.weinelt.de/latex/addcontentsline.html)).

## I don't have any output profiles configured in TeXnicCenter

If your MikTeX installation was don afterwards or is in some special order
then the automatic detection step in TeXnicCenter might fail and there is no
output profile (e.g. LaTeX => PDF) but this list is just blank.

Try then:

1. Go to `Build` then `Define Output Profile` and start the `Wizard...` again.
1. Skip the optional things like postscript and see if this already works.
1. If the MikTeX path cannot be found by this wizard, then you are asked to enter that
by hand. This can be the case when you have installed MikTeX not for all users but
only for the current user. Start to look for the `MiKTeX/2.9/miktex/bin` directory
in the folder `C:\Users\{YOUR_USER_NAME}\AppData\Roaming`, copy this path and try again.

## Installing packages on-the-fly in TeXnicCenter does not work

For the more advanced exercises you need special packages, e.g. `tex\context\base\supp-pdf.mkii`
for `\include{graphicx}`. If you don't have these packages installed locally then
it is possible that during the build process in TeXnicCenter [you are asked to install
this package on-the-fly](https://i.stack.imgur.com/b1b0y.png). After a successful installation
this dialog should not appear any more. However, it is possible that this dialog
apears again and again and the installation always produces some errors.

In this case you should try to use the `MiKTeX Package Manager` (maybe also as Administrator),
see also [here](http://tex.stackexchange.com/questions/49338/miktex-2-9-install-packages-on-the-fly)
and [here](http://latex-community.org/forum/viewtopic.php?t=9034).

## TeXnicCenter gives an error "Cannot execute command"

If you are getting an error message "Cannot execute command" from TeXnicCenter
after trying to view your pdf file with Acrobat, adjust the output profile
settings, see how to  [configure PDF Viewer in the Windows installation guide](https://github.com/UB-Mannheim/sci-work-course/blob/master/doc/install-windows.md#configure-pdf-viewer-optional)

## Configure Sumatra PDF with TexnicCenter

Have a look at https://pic-projekte.de/blog/sumatra-pdf-mit-texniccenter/ and  https://tex.stackexchange.com/questions/116981/how-to-configure-texniccenter-2-0-with-sumatra-2013-2016-version

## Texmaker gives "command not found" errors

Set up the absolute paths to the tools.

## How can I find LaTeX commands for symbols by drawing them?

Try [Detexify](http://detexify.kirelabs.org/classify.html).

## What is the difference between \centering and the `center` environment

See [Difference between `\centering` and `\begin{center}...\end{center}`](http://texblog.net/latex-archive/layout/center-centering/)

## How do I specify multiple authors in BibTeX?

Different authors have to be separated by "and" in the author-field. A comma
will be used to separate last name and first name. A semicolon will be just
looked as any text. Moreover, this often lead to errors like "too many comas".

## How can I change the font size?

> The standard classes, article, report and book support 3 different font sizes, 10pt, 11pt, 12pt (by default 10pt)." 

(see [here](http://texblog.org/2012/08/29/changing-the-font-size-in-latex/) for a nice explanation).

## Error: Cannot determine size of graphic

When the `\includegraphics` gives an error for your picture and tells you that no
bounding box is found, then you can either
* use another image or image format
* mention explicitely the bounding box in LaTeX, i.e. for an image named `pic.jpg`
with width 1280 and height 960:
```latex
\includegraphics[bb=0 0 1280 960]{pic.jpg}
```

## How can I make newlines or multiple lines in cells of some tabular?

This is for example needed if otherwise the text in a column is too wide for the page size.
The easiest is to use `p{'width'}` for such columns in the tabular specification, and possibly
use in such columns then also `\newline`, e.g.
```tex
\begin{tabular}{cp{11cm}}
1 & blabla\\
2 & blabla blabla blabla\newline blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla blabla 
\end{tabular}
```
See also https://tex.stackexchange.com/questions/40561/table-with-multiple-lines-in-some-cells#answer-102986 and https://en.wikibooks.org/wiki/LaTeX/Tables#The_tabular_environment.


## How to cite an online source with BibTeX?

### Standard citation styles

By default Zotero export an website to a `MISC` element in BibTeX and with the `alpha` style only the following elements will be shown:
```
Author. Title, Year.
```

It is possible to add the url of the website in the a `howpublished` of you BibTeX file, e.g.
```
howpublished = {https://bib.uni-mannheim.de},
```
resp. if you are using `hyperref`then you can also add this line
```
howpublished = {\url{https://bib.uni-mannheim.de}},
```
Moreover, you can save the access data in a note field of your BibTeX file, e.g.
```
note = {Accessed on 28.3.2018},
```
This will only show up if you also use the `howpublished` field.

### Advanced citation styles with natbib

An alternative option is to use more advanced citation styles, e.g. `natplain` from the `natbib` package, i.e.
```
\usepackage{natbib}
\bibliographystyle{plainnat}
```
which supports also the `url` parameter.

## How to enable line numbers?

Options -> Configure TeXstudio -> Toggle "Show Advanced Options" at the bottom on -> Adv. Editor -> Show Line Numbers

## How to configure git in TeXstudio?

1. Setting an alias in git ("ci" is used in SVN and can be just replaced with "commit" in git): `git config --global alias.ci "commit"`
2. Options -> Configure TeXstudio -> Commands: In SVN and SVNADMIN enter  `git`.
3. (optionally) Options -> Configure TeXstudio -> Toggle "Show Advanced Options" at the bottom on -> Adv. Editor -> Toolbars: For example you can in the `Tools` toolbar add the command `Check in...` from the File > SVN menu (and even give it a new icon)

You may need to init a new git repository outside TeXstudio. Then, you can use the new button or the menue File -> SVN -> Check in.. to commit the current file or all changed files where you can choose a commit message.

Alternatively, there is an option for an automatic check in at every save. However, this seems to produce a lot of tiny commits with equal commit messages, which might be of less advantages.

See also https://tex.stackexchange.com/questions/112396/texstudio-texmaker-and-github

## How to change the language of Zotero GUI?

https://www.zotero.org/support/supported_languages

## Advanced search in the ACM Digital Library

In the ACM Digital Library some special characters like `:` for separating title and subtitle are leading to no results. Actually, this is only the case in the Advanced Search and not in the Basic Search. _Hint_: Delete these special characters in your search query or use quotation marks `"` for searching a phrase.

The advanced search in the ACM Digital Library is sometimes including the ACM Guide to Computing Literature and sometimes you have to include it manually. The behavior seems to depend on whether you are on Campus (or connected via VPN) or just accessing from home. What is working: Add the results from the guide before you go to advanced search.
