# Thesis Template for University of Stavanger

This thesis template is meant to follow the University of Stavanger's guidelines for graphical profile and visual communications.
The template is inspired by the official PhD thesis cover.

You have the possibility to choose between a number of different color combinations and designs for the cover.

## Terms of Use

The template code itself is released under the [LaTeX Project Public License](LICENSE).

The use of the image material in the `logo` folders is restricted as follows:

> The images can be used by students and employees of the University of Stavanger for official document production.
> Images cannot be used for any other purpose without written consent from the University of Stavanger, Department of communication and public affairs (AKS).
> Page 2 or the last page of the report must credit the photographer if a photo is used.

## Usage

See the `example.tex` file for additional details.

```latex
\documentclass[11pt]{book}
\usepackage[american]{babel}
\usepackage{uis-thesis}

% Optional: UiS recommended font for body text
% \setmainfont{Georgia}

\title{New Directions in Machine-verifiable\\ Progress Credentials and Fully Automated and Transparent Admissions Process}
\authors{Hein Meling}
\department{ide}
% Optional: specify path to photo
% \photo{photos/cern}
\reporttype{master}
\specialization{cs}

\begin{document}
\uiscover{1}
%
% Insert thesis content here
%
\uisbackcover
\end{document}
```

## Compiling

To compile your document use either the `xelatex` or `lualatex` engines.
These are modern LaTeX engines that can use modern fonts via the `fontspec` package.

```shell
xelatex example
```

I'm not aware of any problems using these alternatives over `pdflatex`, but please report any issues in the issue tracker.

### Package Options

The following package options are currently supported:

| Option  | Description                                                |
|---------|------------------------------------------------------------|
| `print` | Align logo placement with color box to facilitate printing |

### Package Commands

The package supports the following commands:

| Command           | Description                                                       |
|-------------------|-------------------------------------------------------------------|
| `\title`          | May use `\\` to force line breaks                                 |
| `\authors`        | Multiple authors should be separate with `,` and `and`            |
| `\department`     | Lower case department abbreviations, e.g., `ide` and `imbm`       |
| `\reporttype`     | Supported: `bachelor`, `master`, `phd`, and `tr`                  |
| `\specialization` | Currently, only `cs, ds, ee, med` are supported; more to be added |
| `\photo`          | Optional: Specify path to photo on cover page                     |
| `\photocredit`    | Cover page photographer may be required                           |
| `\uiscover`       | Display cover page, values 1-9 provide different color schemes    |
| `\uisbackcover`   | Display back cover using the same color schemes as front cover    |
| `\faculty`        | Currently, only `tn` is supported                                 |
| `\restricted`     | Use to print `Restricted Access` on cover page                    |

_I recommend to use only one of `\department` or `\faculty` to keep the page clean._
Typically, `bachelor` and `master` thesis types should use `\department`, while the `phd` type should use `\faculty`.
However, you can use both if you prefer.

Report types `phd` and `tr` _should_ specify the thesis/report number in square brackets as follows:

```latex
\reporttype[404]{phd}
```

PhD thesis and technical report types ignores the `\specialization{}` command, so it is not necessary.
However, bachelor and master thesis reports must specify the specialization, as follows:

```latex
\reporttype{master}
\specialization{cs}
```

### Photo on Cover Page

- If you want to use your own photo, for example a photo or screenshot of your system, simply specify the path to the photo using the `\photo` command.
  The usual image file types are supported.

- You must credit the photographer if you use a photo that you didn't shoot yourself.

**Example:** Cover page with a photo placed in `photos/cern`.

```latex
\photo{photos/cern}
\photocredit{Ansel Adams}
```

### Language Options

The template supports `norsk`, `nynorsk` and any variant of `english`.
You can specify the language as an option to the `bable` package or in the `\documentclass`.

Note that `nynorsk` support requires v1.11 of the translations package; hence make sure to update your TeX distribution.

## Installing Fonts (Linux)

The cover page requires the Tahoma font, which comes preinstalled on macOS and Windows.
However, for Linux you may need to install the Tahoma font:

On Arch Linux:

```shell
yay -S ttf-tahoma
```

For Ubuntu, see this thread on [askubuntu.com](https://askubuntu.com/questions/438670/install-tahoma-font-in-ubuntu).

## Known Issues

- Need to find free replacement fonts for Overleaf; the one used on Linux is free.

## Thanks and Contributions

- LaTeX implementation by Hein Meling, December 2021 - January 2022

- Resources for graphical profile and templates [UiS internal link](https://liveuis.sharepoint.com/sites/Arbeidsstoette/SitePages/Grafisk-profil-UiS.aspx)

- Thanks to Susanna King for help and guidance with preparing this template

- Thanks to Rodrigo Saramago for testing on Linux and providing font instructions

- Thanks to Martin Gilje Jaatun for feedback

- Thanks to Vinay Setty for contributing the document instructions
