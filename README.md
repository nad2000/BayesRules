Installation of Python 3.12, Jupyter, R and Jupyter R-kernel  (on your Windows 10/11)
=====================================================================================

- v0.1 (2024/06/27)

1. open *PowerShell*;
1. run `python3.12` (this will either start Python or start the installation of it from *MS market store*);
1. intall  *Jupyter*: `pip install --user jupyter`;
1. add the *Python* script path to the search path (*System Configuration* -> *Windows Settings* -> *Edit Environmental Settings for your account*) and/or within *PS*, eg, `$env:PATH += ";C:\Users\Radomirs\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.12_qbz5n2kfra8p0\LocalCache\local-packages\Python312\Scripts"`: ![path_setting](https://github.com/nad2000/BayesRules/assets/177266/088937cd-1afc-473b-a691-10f94352398d)
1. verify that you can run *Jupyther* notebook with *Python-kernel*;
1. install *R*: download *R (base)* from https://cran.r-project.org/bin/windows/ and install it;
1. (optional) download and install *RStudio* form https://posit.co/download/rstudio-desktop/;
1. start *R* console (either using short-cut or form *PS*): `C:\Users\Radomirs\AppData\Local\Programs\R\R-4.4.1\bin\x64\Rgui.exe --cd-to-userdocs`
1. and install for *R* console **devtools**: `install.packages("devtools")`;
1. install *R-kernel* from *R* console: `devtools::install_github("IRkernel/IRkernel")`;
1. and finally register it so it could be used from a notebook: `IRkernel::installspec()`;
1. verify that you can run *Jupyther* notebook with *R-kernel*;


