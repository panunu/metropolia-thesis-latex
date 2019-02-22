# Metropolia Thesis LaTeX Template

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">Metropolia Thesis LaTeX Template</span> by <span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">Panu Leppäniemi, Patrik Luoto and Patrick Ausderau</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Compiler

Use XeLaTeX as a compiler.

### Compilation

Usual compilation sequence (minted package require external Python Pygments script to be installed ([check the docs](https://www.ctan.org/pkg/minted?lang=en)))

    # minted require -shell-escape to run  external script. 
    # -8bit avoid ^^I for tabs in minted.
    $ xelatex -shell-escape -8bit main
    # If any change in the bibliography
    $ bibtex8 main
    # If any change with the abbreviation or acronym
    $ makeglossaries main
    #Then compile again
    $ xelatex -shell-escape -8bit main
    #And if still some citation or label warnings, compile once more
    $ xelatex -shell-escape -8bit main

### Using Overleaf

1. Create an account on [Overleaf](https://www.overleaf.com?r=2c9014ea&rm=d&rs=b)  (if not already have one)

#### Using git

1. Fork this project (optional (advantage of fork is to synchronize your github and overleaf projects with your local clone))
1. Clone your fork (or this github project) to your local computer
1. Follow the [instructions](https://www.overleaf.com/help/230-how-do-i-push-a-new-project-to-overleaf-via-git) to create a new Overleaf project from existing git repo
1. Once done, open your Overleaf project and from Menu change "LaTeX Engine" to XeLaTeX and set ``main.tex`` as the main document

#### Create new project from Zip

1. Download this project as zip (or fork)
1. Once logged in ShareLaTeX: Open Project section. Then New Project &rarr; Upload Project &rarr; select the zip (otherwise with the paid version you could sync with github (your fork))
1. Once project opened: from the menu change "compiler" to XeLaTeX and set ``main.tex`` as the main document



