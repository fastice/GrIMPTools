# GrIMPTools
This readme provides information on tools for working with data from the Greenland Ice Mapping Project, which are funded by the NASA [MEaSUREs](https://earthdata.nasa.gov/esds/competitive-programs/measures) program and archived at [NSIDC](https://nsidc.org/data/measures/grimp).

The GrIMP project has now archived several TB of image, velocity, elevation, and glacier terminus data at NSIDC, representing a far greater volume than many users are able to store on their laptops or other computers.
Many studies require only a small subset of these data (e.g., for a particular glacier). As a result, the GrIMP project has developed several tools for accessing and working with the data remotely, eliminating the need for voluminous downloads in many studies.

The tools are all built from open source [Python](https://www.python.org) code that is called from [Jupyter](https://jupyter.org) notebooks. The examples have been structured with default parameters to do much of what the typical user may wish to do, with little or no python knowledge.

These tools are distributed across several gitHub repositories, which can be reached by following the links below.

All tools can be run locally on users machines or run directly, with some limitations, on freely available cloud resources.

## Binder

The notebooks in the repositories listed below can run locally on a users own machine or cloud resource, but users can also run them remotely free of charge as a [*binder*](https://jupyter.org/binder) app. Advantages to *binder* are:
- The notebook runs in a well-tested, pre-configured environment,
- No need to setup on your own machine.

There are some limitations to *binder*:
- The *binder* instances are often limited in memory, which can easily be exceeded if too large a region is or too many products are selected.
- The *binder* instance will time out after an ten minutes of inactivity, and all work will be lost. Keeping the notebook in 
the foreground while it runs should avoid a timeout. Products must be downloaded to be saved. 

## Installation on Local Machine

If not running in binder, the easiest and surest way to run these notebooks is use create a [conda](https://docs.conda.io/en/latest/) environment using the [environment.yml](https://github.com/fastice/GrIMPNotebooks/blob/master/binder/environment.yml) file in the binder folder for this repository.

    conda env create -f environment.yml
    python -m ipykernel install --user --name=greenlandMapping

Once installation is complete:

    conda activate greenlandMapping
    jupyter lab

It the libraries don't load once the notebook starts to run, check that the **greenlandMapping** kernel is selected from the pulldown in the upper right corner of the screen.
  
The code in these notebooks requires two code from three repositories: [grimpfunc](https://github.com/fastice/GrIMPfunc),
[nisardev](https://github.com/fastice/nisardev), and [grimpqgis](https://github.com/fastice/grimpqgis). The latter is needed only for the
[qgisRremoteNotebook.ipynb](https://github.com/fastice/GrIMPNotebooks/blob/master/qgisRemoteNotebook.ipynb) notebook. These packages are 
installed automatically with the conda install described above. Otherwise, they can be pip installed directly from their respective github repos (pip >= v22.0.3).

## [GrIMPNoteBooks](https://github.com/fastice/GrIMPNotebooks) [![Binder](https://gesis.mybinder.org/badge_logo.svg)](https://gesis.mybinder.org/v2/gh/fastice/GrIMPNotebooks/HEAD?urlpath=lab)

This repository contains notebooks to demonstrate tools for working with GrIMP data directly from the archive. Specifically the code can be used to:
- Generate publication plots directly from the [GrIMP products at NSIDC](https://nsidc.org/data/measures/grimp);
- Create or download *QGIS* project and layer definition definitions files so that GrIMP products can be displayed directly from the NSIDC servers;
- Subset data and download time series stacks directly to netCDF files. 

## [GrIMPQGISProject](https://github.com/fastice/GrIMPQGISProjects) [![Binder](https://gesis.mybinder.org/badge_logo.svg)](https://gesis.mybinder.org/v2/gh/fastice/GrIMPQGISProject/HEAD?urlpath=lab)

This reposititory contains *QGIS* project and layer definition files that allow remote GrIMP products to be directly ingested and viewed in QGIS with no intermeidate storage on the local machine.

These products require a NASA [Earth Data Login](https://urs.earthdata.nasa.gov/), which requires a free registration.

Some minor setup is required to authenticate as described here [**NSIDCLoginNotebook**](https://github.com/fastice/GrIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb).

## Supporting Python Code

The  notebooks described above using the following Python libraries:
- [grimpfunc](https://github.com/fastice/GrIMPfunc): Tools to perform NSIDC authentication, Common Metadata Repoository ([CMR](https://earthdata.nasa.gov/eosdis/science-system-description/eosdis-components/cmr)) searches for GrIMP products, and GrIMP product subsetting. (See [GrIMPSubsetterNotebook](https://github.com/fastice/GrIMPNotebooks/blob/master/GrIMPSubsetterNotebook.ipynb) for examples.)
- [grimpqgis](https://github.com/fastice/grimpqgis): Tools to build automatically build *QGIS* project files and layer definition files for remote access of GrIMP products. (See [qgisRemoteNotebook](https://github.com/fastice/GrIMPNotebooks/blob/master/qgisRemoteNotebook.ipynb) for examples.)
- [nisardev](https://github.com/fastice/nisardev): Tools for building and manipulating time series stacks of GrIMP image and velocity data. Facillitates saving subsets as NetCDF files. (See working with [workingWithGrIMPImageData](https://github.com/fastice/GrIMPNotebooks/blob/master/workingWithGrIMPImageData.ipynb), [workingWithGrIMPVelocity](https://github.com/fastice/GrIMPNotebooks/blob/master/workingWithGrIMPVelocity.ipynb), and [Flowlines](https://github.com/fastice/GrIMPNotebooks/blob/master/Flowlines.ipynb) for examples.)

## Further Information

These tools were created by Ian Joughin and Scott Henderson at the University of Washington.
For 
