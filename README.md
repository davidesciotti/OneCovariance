![Logo](https://raw.githubusercontent.com/rreischke/OneCovariance/main/docs/Onecov_logo.png "Logo")

OneCovariance is python package (with some C++ for the heavy lifting) for the calculation of the covariance matrix of photometric large-scale structure surveys. It can produce the covariance matrix for all the 2-point statistics used within the Kilo-Degree-Survey (KiDS), that is configuration space statistics, bandpowers and COSEBIs. All these observables are derived from projected Fourier space quantities. The code is flexible enough to read in the ingredients from a harmonic space covariance matrix and produce one of the mentioned statistics (whether these are optimal for the considered case is a different question). 

## Documentation, Installation and Examples
The installation steps, documentation and examples are all provided at [onecovariance.readthedocs.io](https://onecovariance.readthedocs.io/en/latest/).

### Using the conda environment
 For starters you first clone the directory via:
```shell
git clone git@github.com:rreischke/OneCovariance.git
```
or
```shell
git clone https://github.com/rreischke/OneCovariance.git
```
Then navigate to the cloned directory
```shell
cd OneCovariance
conda env create -f conda_env.yaml
conda activate cov20_env
pip install .
```
On some Linux servers you will have to install ``gxx_linux-64`` by hand and the installation will not work. This usually shows the following error message in the terminal:
``
gcc: fatal error: cannot execute 'cc1plus': execvp: No such file or directory
``
If this is the case just install it by typing
```shell
 conda install -c conda-forge gxx_linux-64
```
and redo the ``pip`` installation.

### Not using the conda environment
If you do not want to use the conda environment make sure that you have ``gfortran`` and ``gsl`` installed. **Note that there is an issue with pybind11 when using python >= 3.13, so make sure to use a version below that for the moment.**
You can install both via ``conda``:
```shell
conda install -c conda-forge gfortran
conda install -c conda-forge gsl
conda install -c conda-forge gxx_linux-64
git clone git@github.com:rreischke/OneCovariance.git
cd OneCovariance    
pip install .
```
Once you have installed the external package via ``pip install`` the code simply runs by using the ``config.ini`` where all parameters are stored and explained. Running the script
```shell
python covariance.py
```
will run the code using the settings in the standard configuration file ``config.ini``. 


