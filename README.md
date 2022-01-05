# Thesis Template for University of Stavanger

This thesis template is meant to follow the University of Stavanger's guidelines for graphical profile and visual communications.
The template is inspired by the official PhD thesis cover.

You have the possibility to choose between a number of different color combinations and designs for the cover.

## Terms of Use

The template code itself is released under the [LaTeX Project Public License](LICENSE).

The use of the image material in the `logo` and `photos` folders is restricted as follows:

> The images can be used by students and employees of the University of Stavanger for official document production.
> Images cannot be used for any other purpose without written consent from the University of Stavanger, Department of communication and public affairs (AKS).
> Page 2 or the last page of the report must credit the photographer if a photo is used.

## Usage

See the `example.tex` file for additional details.

```latex
\documentclass[12pt]{report}
\usepackage[american]{babel}
\usepackage{uis-thesis}

% Optional: UiS recommended font for body text
% \setmainfont{Georgia}

\title{New Directions in Machine-verifiable\\ Progress Credentials and Fully Automated and Transparent Admissions Process}
\authors{Hein Meling}
\department{ide}
% Optional: if photo option used, specify name of photo in photos folder
% \photo{cern}
\thesistype{master}
\specialization{cs}

\begin{document}
\uiscover{1}
\uisbackcover
\end{document}
```

## Compiling

Unfortunately, due to font requirements it is not possible to compile using `pdflatex`.
Instead you can use the `xelatex` or `lualatex` engines.
I'm not aware of any problems using these alternatives over `pdflatex`, but please report any issues in the issue tracker.
The default engine on Overleaf is `xelatex`.

```shell
xelatex example
```

### Package Options

The following package options are currently supported:

| Option  | Description                                                |
|---------|------------------------------------------------------------|
| `photo` | Use photo; department specific photos are used by default  |
| `print` | Align logo placement with color box to facilitate printing |

### Package Commands

The package supports the following commands:

| Command           | Description                                                       |
|-------------------|-------------------------------------------------------------------|
| `\title`          | May use `\\` to force line breaks                                 |
| `\authors`        | Multiple authors should be separate with `,` and `and`            |
| `\department`     | Lower case department abbreviations, e.g., `ide` and `imbm`       |
| `\thesistype`     | Supported: `bachelor`, `master`, and `phd`                        |
| `\specialization` | Currently, only `cs, ds, ee, med` are supported; more to be added |
| `\photo`          | Specifies name of photo in photos folder                          |
| `\photocredit`    | Cover page photographer may be required                           |
| `\uiscover`       | Display cover page, values 1-9 provide different color schemes    |
| `\uisbackcover`   | Display back cover using the same color schemes as front cover    |
| `\faculty`        | Currently, only `tn` is supported                                 |
| `\restricted`     | Use to print `Restricted Access` on cover page                    |

_I recommend to use only one of `\department` or `\faculty` to keep the page clean._
Typically, `bachelor` and `master` thesis types should use `\department`, while the `phd` type should use `\faculty`.
However, you can use both if you prefer.

### Photo on Cover Page

- If you specify the `photo` package option, the default is to use a department specific photo.
  For example, for `ide` a photo named `photos/ide` will be used.

- If you want to use your own photo, for example a photo of your system, simply place the photo in the `photos` folder and specify the photo name using the `\photo` command.
  The usual image file types are supported.

- You must credit the photographer if you use a photo that you didn't shoot yourself.

**Example:** Cover page with a photo placed in `photos/cern`.

```latex
\usepackage[photo]{uis-thesis}
\photo{cern}
\photocredit{Ansel Adams}
```

### Language Options

The template supports both `norsk` and any variant of `english`.
You can specify the language as an option to the `bable` package or in the `\documentclass`.
Support for `nynorsk` is not working yet (see known issues below).

## Installing Fonts (Linux)

The cover page requires the Tahoma font, which comes preinstalled on macOS and Windows.
However, for Linux you may need to install the Tahoma font:

On Arch Linux:

```shell
yay -S ttf-tahoma
```

For Ubuntu, see this thread on [askubuntu.com](https://askubuntu.com/questions/438670/install-tahoma-font-in-ubuntu).

## Known Issues

- The translation package seems to override nynorsk or norsk, whichever is defined last

- Default photos are missing from the repository; I hope to add relevant photos soon

## Thanks and Contributions

- LaTeX implementation by Hein Meling, December 2021 - January 2022

- Resources for graphical profile and templates [UiS internal link](https://liveuis.sharepoint.com/sites/Arbeidsstoette/SitePages/Grafisk-profil-UiS.aspx)

- Thanks to Susanna King for help and guidance with preparing this template

- Thanks to Rodrigo Saramago for testing on Linux and providing font instructions
