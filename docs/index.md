

This page provides more information about the IRIS Python tutorial given at the IRIS-10 meeting in Bengaluru, India. At the workshop, participants are expected to work on the tutorial using Binder, a cloud-based solution that lets you run an instance of Jupyter lab with all the required packages and data files. To start the Binder notebook, follow the link below:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tiagopereira/iris10/master?urlpath=lab/tree/notebooks%2FIRIS10.ipynb)

# Running on your computer

Binder makes it easy to get started with minimal effort, but if you want to actually use [IRISPy](https://docs.sunpy.org/projects/irispy/en/latest/), you will need to have it installed in your computer. IRISPy relies on several other packages such as SunPy, astropy, and matplotlib. The recommended way to install all of them is via conda ([miniconda](https://conda.io/miniconda.html) or [Anaconda](https://www.anaconda.com/download/)). You can follow the [installation instructions](https://docs.sunpy.org/projects/irispy/en/latest/installation.html) on the IRISPy documentation, or follow all the lines below (they are very similar).

To install the tutorial files, you need to clone its [git repository](https://github.com/tiagopereira/iris_tutorials/) or [download a zip file](https://github.com/tiagopereira/iris_tutorials/archive/master.zip). To clone, run the following in a directory of your choice:

```bash
git clone https://github.com/tiagopereira/iris10.git
```

You will end up with a directory called `iris10`. In the terminal, go to that directory. If you do not have IRISPy installed, you can create a new conda environment by using the supplied `environment.yml` file. The following will download and install all required packages into an environment called `iris`:

```bash
conda env create -f environment.yml
```

Then you need to activate the environment:

```bash
conda activate iris
```

Lastly, you will need to install IRISPy (not available on conda) with pip:

```bash
pip install git+https://github.com/tiagopereira/irispy.git
```

Optionally, if you want to have interactive matplotlib plots in jupyter, you need to run (this operation takes a while):

```bash
jupyter labextension install @jupyter-widgets/jupyterlab-manager jupyter-matplotlib
```

Finally, you will need to download the data files used in the tutorial. Assuming you are at the terminal in the directory of `iris_tutorials`, you can download the data files into `iris_tutorials/notebooks` with the following:

```bash
wget -c http://www.lmsal.com/solarsoft/irisa/data/level2_compressed/2018/01/02/20180102_153155_3610108077/iris_l2_20180102_153155_3610108077_SJI_1400_t000.fits.gz -P notebooks/
wget -c http://www.lmsal.com/solarsoft/irisa/data/level2/2014/09/19/20140919_051712_3860608353/iris_l2_20140919_051712_3860608353_SJI_2832_t000.fits -P notebooks/
wget -c https://folk.uio.no/tiago/aia_20140919_060030_1700_image_lev1.fits -P notebooks/
wget -c https://folk.uio.no/tiago/iris_l2_20180102_153155_3610108077_raster_t000_r00000.fits.bz2 -P notebooks
pbunzip2 notebooks/iris_l2_20180102_153155_3610108077_raster_t000_r00000.fits.bz2
```

This will download about 350 MB of data. Once you have them, you are ready to start the tutorial:

```bash
jupyter lab
```

And then navigate to `notebooks/IRIS10.ipynb`.
