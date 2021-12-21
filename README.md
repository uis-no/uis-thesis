# Thesis Template for University of Stavanger

This thesis template is meant to follow the University of Stavanger's guidelines for graphical profile and visual communications.
The template is inspired by the official PhD thesis cover.

You have the possibility to choose between a number of different color combinations and designs for the cover.

## Usage

See the `example.tex` file for additional details.

```latex
\documentclass[12pt]{report}
\usepackage[american]{babel}
\usepackage{uis-thesis}

\setmainfont{Georgia}

\title{New Directions for Machine-verifiable\\ Progress Credentials with Application to Academic Credentials}
\authors{Hein Meling}
\department{ide}
% Optional if photo option used: specify name of photo in photos folder
% \photo{cern}
\thesistype{master}
\specialization{cs}

\begin{document}
\uiscover{1}
\end{document}
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
| `\uiscover`       | Display cover page, values 1-9 provide different color schemes    |
| `\faculty`        | Currently, only `tn` is supported                                 |
| `\restricted`     | Use to print `Restricted Access` on cover page                    |

_I recommend to use only one of `\department` and `\faculty` to avoid overloading the page with information._
Typically, `bachelor` and `master` thesis types should use `\department`, while the `phd` type may use `\faculty`.

#### Photos on Cover Page

- If you specify the `photo` package option, the default is to use a department specific photo.
  For example, for `ide` a photo named `photos/ide` will be used.

- If you want to use your own photo, for example a photo of your system, simply place the photo in the `photos` folder and specify the photo name using the `\photo` command.
  The usual image file types are supported.

**Example:** Cover page with a photo placed in `photos/cern`.

```latex
\usepackage[photo]{uis-thesis}
\photo{cern}
```

### Language Options

The template supports both `norsk` and any variant of `english`.
You can specify the language as an option to the `bable` package or in the `\documentclass`.
Support for `nynorsk` is not working yet (see known issues below).

## Known Issues

- The translation package seems to override nynorsk or norsk, whichever is defined last

## Thanks and Contributions

- LaTeX implementation by Hein Meling, December 2021

- Resources for graphical profile and templates [UiS internal link](https://liveuis.sharepoint.com/sites/Arbeidsstoette/SitePages/Grafisk-profil-UiS.aspx)

- Thanks to Susanna King for help and guidance with preparing this template
