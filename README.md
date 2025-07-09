The eddy-covariance flux processor eddy4R consists of modular software packages in the [R-language for statistical computing](https://www.r-project.org). The namesake [eddy4R Docker image](https://hub.docker.com/r/stefanmet/eddy4r/) is based on on the [rocker/ropensci image](https://hub.docker.com/r/rocker/ropensci), and currently adds two eddy4R packages and their dependencies as builds from a Dockerfile. Build additions on the operating system side:

- EBImage dependencies
  - fftw3
  - fftw3-dev
  - libjpeg-dev
  - libtiff-dev
- REddyProc dependencies
  - libudunits2-0
  - libudunits2-dev
  - libnetcdf-dev
  - udunits-bin

Build additions on the R-side via the [eddy4R installation script](https://www.dropbox.com/s/xmgsctjbrekfyw8/flow.inst.eddy4r.R?dl=1):

- eddy4R.base
- eddy4R.qaqc

For additional information please see Sect. 2.6	"Installation and operation" in [eddy4R: A community-extensible processing, analysis and modeling framework for eddy-covariance data based on R, Git, Docker and HDF5](http://www.geosci-model-dev-discuss.net/gmd-2016-318/).

## Docker Image

To build the eddy4R Docker image locally, make sure you have [Docker installed](https://docs.docker.com/get-docker/) on your system. Then, from the root directory of this repository, run:
```
docker build -t eddy4r:latest .
```

After building the image, you can run a container using:

```
docker run -e PASSWORD=<YOUR_PASS> -p 8787:8787 eddy4r:latest
```