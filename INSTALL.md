# Installation Guide

To utilize the artifacts in this repository, follow the installation guides below.
<!-- select only the instructions necessary for the respective artifacts in this repository -->

- To view `.md` Markdown files contained in this repository, consider a Markdown viewer like the one [integrated into Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown).
- To display and edit graphs specified in `.graphml` format, use a graph editor like [yEd](https://www.yworks.com/products/yed) by yworks.

## Python

To execute the Python source code, make sure that you have [Python 3.10.0](https://www.python.org/downloads/release/python-3100/) or any later version installed.
Make sure that the installation of Python also includes the package manager [pip](https://pypi.org/project/pip/).
Then, execute the following steps:

1. Optionally, to isolate your local python environment from this one, create a [virtual environment](https://docs.python.org/3/library/venv.html):
    1. Execute `python -m venv .venv` to create a virtual environment in the directory *.venv/*.
    2. [Activate](https://docs.python.org/3/library/venv.html#how-venvs-work) the virtual environment, e.g., via `.venv/scripts/Activate.ps1` on Windows.
2. Install all necessary requirements via `pip install -r requirements.txt`.
3. When using a virtual environment and wanting to execute jupyter notebooks (`.ipynb`), you also need to install a jupyter kernel via `ipython kernel install --user --name=venv`. IDEs like VS Code will prompt to install the kernel automatically

## R

In order to run the `.R` scripts and `.Rmd` notebooks, ensure that you have [R](https://ftp.acc.umu.se/mirror/CRAN/) (version > 4.0) and an appropriate IDE like [RStudio](https://posit.co/download/rstudio-desktop/#download) installed on your machine.
Then, install all required packages via `install.packages(c("tidyverse", "patchwork"))`.

## R for Bayesian Data Analysis

In order to run the `.R` scripts and `.Rmd` notebooks, ensure that you have [R](https://ftp.acc.umu.se/mirror/CRAN/) (version > 4.0) and an appropriate IDE like [RStudio](https://posit.co/download/rstudio-desktop/#download) installed on your machine.
Then, ensure the following steps:

1. Install the C toolchain by following the instructions for [Windows](https://github.com/stan-dev/rstan/wiki/Configuring-C---Toolchain-for-Windows#r40), [Mac OS](https://github.com/stan-dev/rstan/wiki/Configuring-C---Toolchain-for-Mac), or [Linux](https://github.com/stan-dev/rstan/wiki/Configuring-C-Toolchain-for-Linux) respectively.
2. Restart RStudio and follow the instructions starting with the [Installation of RStan](https://github.com/stan-dev/rstan/wiki/RStan-Getting-Started#installation-of-rstan)
3. Install the `devtools` and the latest version of `stan` by running the following commands
```R
    install.packages("devtools")
    devtools::install_github("stan-dev/cmdstanr")
    cmdstanr::install_cmdstan()
```
4. Install all required packages via `install.packages(c("tidyverse", "ggdag", "brms", "marginaleffects", "patchwork"))`.
5. Create a folder called *fits* within *src/* such that `brms` has a location to place all Bayesian models.
6. Open the `.Rproj` file with RStudio which will setup the environment correctly.
