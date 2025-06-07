**If you are just here to view the docs, jump strait to "Open existing documentation"**

This project uses [material for mkdocs](https://squidfunk.github.io/mkdocs-material/) for building documentation.

It also requires the [mkdoxy](https://github.com/JakubAndrysek/MkDoxy-demo) pip package and the [doxygen](https://www.doxygen.nl/index.html) executable. 

The documentation is capable of documenting any docstring in any file within the `src/main` or `src/argos_lib` directory.

Follow the instructions below to open the docs, or install the necessary tools and build the documentation.

## Open existing documentation

**RECOMMENDED**

Ideally, there should be built documentation present in this repository. Open the `/Docs/site/index.html` file from your file explorer to view it.

## Install Tooling & Build

1. You need **Python** installed and available in your path for this to work. You can get this from the [Microsoft store](https://apps.microsoft.com/detail/9nrwmjp3717k?hl=en-us&gl=US) or from the [python foundation](https://www.python.org/downloads/). Make sure you **add it to your path** when asked in the installer.
2. Install [Doxygen](www.doxygen.nl/download.html) and also add this to your path. The specific directory you'll need to add is: `C:\Program Files\doxygen\bin`. If help is needed, follow the instructions [here](https://windowsloop.com/how-to-add-to-windows-path/) (scroll down to "Add directory or program to Windows PATH")
3. Open this repository in **this** folder (`Docs/`) using a terminal or vscode
4. Run the following commands:

```
python -m venv ./.venv
./.venv/Scripts/activate
pip install -r requirements.txt
mkdocs serve
```

5. Open a web browser and open [localhost:8000](https://localhost:8000/) to view documentation
6. Use `mkdocs build` to build the documentation into a folder at `Docs/site/` if you want to

## Troubleshooting

**Running scripts is disabled on this system**

This may occur while trying to run `./.venv/Scripts/activate`. You can enable running scripts by following the instructions [here](https://stackoverflow.com/a/64633728)

**Documentation fails to build**

Check to make sure that `mkdoxy` and `doxygen` were installed properly and added to the PATH environment variable (you can test this by typing `doxygen -v` into a terminal, and if a version is printed, it is correct)