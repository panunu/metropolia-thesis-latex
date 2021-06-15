# Metropolia Thesis LaTeX Template

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">Metropolia Thesis LaTeX Template</span> by <span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">Panu Leppäniemi, Patrik Luoto, Mikaa Oni and Patrick Ausderau</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

Check comments in [main.tex](main.tex) for details. Especially what it means when licensing your own thesis when using this template.

## Accessibility

Accessible pdf is a requirement for the 2021 thesis (and every future versions as required by EU regulations). Currently, it is [work in progress](https://tug.org/twg/accessibility/) in LaTeX and should be implemented by 2023/25. Meanwhile, there is two options:

### Option 1, check by hand (recommended)

Once your pdf is ready to be published, use e.g. Adobe Acrobat Pro DC (available on school computers), from the More Tools -> Accessibility, run the Accessibility Check and once the Checker opens, you can fix the problems by right clicking them (mostly, fix the Tagged PDF, Alternative text for image and Table Headings,...).

### Option 2, try with some experimental packages (at your own risk)

If you are not afraid and know what you are doing... Has been tested in [branch axessibility](../tree/axessibility) (and somehow in abandoned accessibility-tag branch):
* `accsupp` and `pdfcomment` packages to have alternative text to figures. Nicely get a tooltip over the image; but fail the alternative text test...
* `accessibility` package for tagged pdf; but conflicted with too many packages and as stated by the author "should be considered broken and unusable".
* `tagpdf` package  would require much manual work (e.g. when trying to add `alttext` to figures). And as stated by the author "is not intended for production use, but allows the user to try out how difficult it is to tag some structures".
* `axessibility` to tag formulae. Works nicely; but seems to mess with the reading order of the other elements?

Most of these packages required to use `lualatex` as compiler.

## Compiler

Use XeLaTeX as a compiler.

### Compilation

Usual compilation sequence (minted package require external Python Pygments script to be installed ([check the docs](https://www.ctan.org/pkg/minted?lang=en)))

    # minted require -shell-escape to run  external script.
    # -8bit avoid ^^I for tabs in minted.
    $ xelatex -shell-escape -8bit main
    # If any change in the bibliography
    $ biber main
    # If any change with the abbreviation or acronym
    $ makeglossaries main
    #Then compile again
    $ xelatex -shell-escape -8bit main
    #And if still some citation or label warnings, compile once more
    $ xelatex -shell-escape -8bit main

#### GitHub Actions

As a demonstration, check the [.github/workflows/main.yml](.github/workflows/main.yml) for an example of latex build through github actions. Result [pdf can be downloaded](../../actions) if the job is successful.

### Using Overleaf

1. Create an account on [Overleaf](https://www.overleaf.com?r=2c9014ea&rm=d&rs=b)  (if not already have one)

#### Using git

Note: git version control != GitHub 😉 These instructions can be used with the Personal/Free subscription plan. While you would need the paid version of Overleaf to directly sync with GitHub.

1. Fork this project (optional (advantage of fork is to synchronize your github and overleaf projects with your local clone))
1. Clone your fork (or this github project) to your local computer
1. Follow the [instructions](https://www.overleaf.com/help/230-how-do-i-push-a-new-project-to-overleaf-via-git) to create a new Overleaf project from existing git repo
1. Once done, open your Overleaf project and from Menu change "LaTeX Engine" to XeLaTeX and set ``main.tex`` as the main document

#### Create new project from Zip

1. Download this project as zip (or fork)
1. Once logged in Overleaf, open Project section. Then New Project &rarr; Upload Project &rarr; select the zip (otherwise with the paid version you could sync with github (your fork))
1. Once project opened: from the Menu change "compiler" to XeLaTeX and set ``main.tex`` as the main document



