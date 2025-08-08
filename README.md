Installation of Python 3.12, Jupyter, R and Jupyter R-kernel  (on your Windows 10/11)
=====================================================================================

- v0.1 (2024/06/27)

#### 0. Install Python

 - open *PowerShell* (*PS*) console;
 - run `python3.12` (this will either start Python or start the installation of it from *MS market store*);

#### 1. Install R

Download and install R from the Comprehensive R Archive Network (CRAN):
- **Windows**: [Download R for Windows](https://cran.r-project.org/bin/windows/base/)
- **macOS**: [Download R for macOS](https://cran.r-project.org/bin/macosx/)
- **Linux**: Use your distribution’s package manager. For example, on Debian-based systems:
  ```sh
  sudo apt-get update
  sudo apt-get install r-base
  ```

(OPTIONAL, - you might need Admin permissions) download and install *RStudio* from https://posit.co/download/rstudio-desktop/;

#### 2. Install Jupyter

Install Jupyter using `pip` (on *Windows* from *PS* console):
```sh
python -m pip install -U --user pip
python -m pip install -U --user jupyter notebook
```

Add the *Python* script path to the search path (*System Configuration* -> *Windows Settings* -> *Edit Environmental Settings for your account*) and/or within *PS*, eg, `$env:PATH += ";C:\Users\Radomirs\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.12_qbz5n2kfra8p0\LocalCache\local-packages\Python312\Scripts"` and restart your *PowerShell*: ![path_setting](https://github.com/nad2000/BayesRules/assets/177266/088937cd-1afc-473b-a691-10f94352398d)

Verify that you can run *Jupyther* notebook with *Python-kernel*, typing in *PS*: `jupyter notebook`.

Alternatively, you can install Jupyter via Anaconda, which includes Jupyter and many other useful packages:
- Download and install Anaconda from [here](https://www.anaconda.com/products/individual).
- After installing Anaconda, open the Anaconda Prompt (Windows) or terminal (macOS/Linux) and run:
  ```sh
  conda install -c conda-forge notebook
  ```

#### 3. Install the IRKernel

Install the necessary **R** packages and the **IRKernel**:

1. Open R or RStudio (either using the shortcut on your desktop or from *PS*, eg, `C:\Users\Radomirs\AppData\Local\Programs\R\R-4.4.1\bin\x64\Rgui.exe --cd-to-userdocs` or with Linux: `R --no-readline --interactive`) and run the following commands to install the required packages:
    ```r
    install.packages('devtools')                  # devtools so you can install packages fom GitHub
    devtools::install_github("IRkernel/IRkernel") # Jupyter R-kernel
    IRkernel::installspec()                       # and finally register it so it can be used from a notebook
    ```
2. To ensure all dependencies are installed, you might also need:
    ```r
    install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'uuid', 'digest'))
    ```

#### 4. Verify the Installation

To verify that everything is installed correctly, start **Jupyter Notebook**:
```sh
jupyter notebook
```
In the Jupyter interface, click "**New**" and check if "**R**" appears in the list of *available kernels*.

### Additional Resources

- [Jupyter Documentation](https://jupyter.org/documentation)
- [R Project](https://www.r-project.org/)
- [IRKernel GitHub](https://github.com/IRkernel/IRkernel)
```
