# Stackoverflow Curriculum Vitae - Résumés

After that I read this [post](https://meta.stackoverflow.com/questions/415293/sunsetting-jobs-developer-story), I started from my old Stackoverflow CV and I have added some features of these [curricula vitae](https://www.latextemplates.com/cat/curricula-vitae) templates to generate the original Stackoverflow CV and my upgraded version.

## Installation

You can clone this repository in your local: if you are ready to make your CV, the ``make cv`` command, it will generate correctly a file named **stackoverflow.pdf**

```sh
# clone my repository
git clone https://github.com/bilardi/stackoverflow-cv
cd stackoverflow-cv/

# if the command below will not generate any errors, you are ready to make your CV, else before you have to follow the steps suggested
make test 

# if the command below will not generate any errors, you can try to generate my CV for testing
make cv
```

## Usage

You can copy or modify the file named **stackoverflow.tex** with your details.

This template compiles with standard **pdflatex**. There are no special requirements outside of packages that are supplied with a full distribution of TeX.

* if you modify directly the file named **stackoverflow.tex**, you can use ``make cv`` command: it will generate your new PDF file named **stackoverflow.pdf**
* if you modify directly the file named **stackoverflow.tex**, and you also want to remove the all support files generated by **pdflatex**, you can use ``make all``
* if you copy the file named **stackoverflow.tex** in yours, you can use directly ``pdflatex your-file.tex``: this command will generate the file named **your-file.pdf** and some support files

The package **pdflatex** will generate some support files that you can remove with the command ``make clean``

There is also another version of CV: this is my upgraded version with some new features. If you want to use it, you can modify the file named **stackoverflow-upgrade-version.tex** and use the command ``make upgrade``

## Development of your CV

You can modify all that you want: [colors](https://it.overleaf.com/learn/latex/Using_colours_in_LaTeX), [fonts](https://it.overleaf.com/learn/latex/Font_sizes%2C_families%2C_and_styles), [formatting](https://it.overleaf.com/learn/latex/Bold%2C_italics_and_underlining), .. and so on. And you can use the file named **fontawesome.pdf** to add any symbols that you want.

There is a file to manage the general formatting: it is named **stackoverflow.cls**. In this file, you can find all ``\newcommand``s and others used in files **stackoverflow.tex**. There is also another cls file named **stackoverflow-upgraded-version.cls** that I created initially to generate my upgraded version of Stackoverflow CV that I used with the file named **stackoverflow-upgraded-version.tex**.

You can find a simple description of each component below.

### Fonts

This template uses the [Raleway](https://tug.org/FontCatalogue/raleway/) font. A number of other options that also look good are available in the class file. Simply copy one of these into the template and uncomment it to use a different font.

### Icons

You can use the icons of [FontAwesome](https://fontawesome.com/). Icons are added with a command like this: ``\icon{Phone}{12}{+1 123 456 789}``. The first argument is the FontAwesome identifier for the icon you would like to use, this is simply the text after ``\fa`` in the file named **fontawesome.pdf**. For example, the command for the previous phone icon would be \faPhone. The second argument of the ``\icon`` command is the width and height of the square box that encloses it, you can adjust this as needed. Finally, the third argument is the text to the right of the icon box, be careful to keep this short or it will be difficult to fit everything into the width of the page.

### Bar chart

The skills bar chart is created using a ``barchart`` environment. The environment takes a single argument for the maximum width a bar can take up at 100% width, in cm. Inside this environment, use the ``\baritem{}{}`` command to add new bars. The first argument to this command is the skill label and the second is the percentage width the bar should take up of the maximum width specified for the environment. Use whole numbers from 1-100 for this.

### Positioning Content on the Page

This template makes extensive use of the ``minipage`` environment for positioning elements next to each other on the page. If you’d like to make a new set of elements, it’s recommended to copy an existing example from the template and modify the percentages. Make sure they add up to 100% whenever adjusting minipages.

### Spanning Multiple Pages

If your content doesn’t fit on one page, it will automatically wrap to the next page at the next reasonable location between entries in lists, such as for Experience or Education. LaTeX will decide where this should occur, and if you don’t like this behaviour, you can simply add a ``\newpage`` command to wherever you would like to manually break to the next page. Be wary that changing content upstream of such a break will shift its position up or down.

### Bubbles

Bubbles are created using the ``\bubbles{}`` command. The only argument to this is a string specifying the number of bubbles and their sizes and labels. This must be in the following format: ``\bubbles{5/Eclipse, 6/git}`` where the number is the relative size of the bubble and the text to right of the slash delimiter is the bubble label. Each bubble should be separated by a comma from the previous one.

### CV Sections

New sections (the labels with white text on a black background) are created using the ``\cvsect{}`` command. This takes a single argument for the section text.

### CV Entry lists

Important information with multiple entries lives in entry lists. These are created using the ``entrylist`` environment. Inside this environment, each entry is added using the ``\entry`` command. This command takes 4 arguments, the first is the date range on the left, the second is the entry heading, the third is the entry qualifier and the fourth is the entry description. The entry description can include a monospace list of technologies as follows: ``\texttt{PHP}\slashsep\texttt{JS}}``. If you don’t need any of these elements in the entry, leave its argument empty rather than removing it entirely.

## Change Log

See [CHANGELOG.md](CHANGELOG.md) for details.

## License

This package is released under the MIT license. See [LICENSE](LICENSE) for details.