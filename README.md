# 🗺 Data download

In this tutorial tools for geospatial data provided by Sentinel-2 mission download is shown:

1) From distribution platforms of SentinelHub <br> 
2) Using Google Earth Engine (currently in work 🏗🚧) <br>

The first part of data download example is based on very detailed tutorials on the SentinelHub. Currently used libraries so far:
* [sentinelhub](https://sentinelhub-py.readthedocs.io/en/latest/index.html) - to download image collections using Python API
* [json](https://docs.python.org/3/library/json.html)  - to read json file with credentials
* [datetime](https://docs.python.org/3/library/datetime.html) - to process data ranges for single day image and time-series
* [matplotlib](https://matplotlib.org/3.5.3/api/_as_gen/matplotlib.pyplot.html) - to visualise the data

Commonly used alternative to sentinelhub is [sentinelsat](https://sentinelsat.readthedocs.io/en/latest/api_overview.html) relied on Copernicus Open Access Hub, so to authorise for work user must be regitered on [SciHub](https://scihub.copernicus.eu/gnss/#/home). In general work sentinelsat goes through the same steps, namely: authentification, region of interest setting, specifying of the platform, specifying of the requirements to data (e.g. cloud percentage).

----------------------

**A gentle reminder**

To proceed properly geospatial data in jupyter notebook and to avoid upsetting errors like `package not found` at the import step just after installing it make sure that you run your notebook within the [**same kernel**](https://docs.jupyter.org/en/latest/projects/kernels.html) where you download libraries. I strongly do not recommend to install libraries within jupyter notebook directly with ``pip install`` unless you do not feel confident enough to understand and check which python from where do you currently use. 

For the geospatial data analysis to avoid conflicts I use the separate environment. My pipeline includes the following steps (considering that you already have python and conda): <br>

In terminal/console
1) Create new environment, specify python : ``conda create -n {place env name} python=3.9`` <br>
2) Activate new environment: ``conda activate {place env name}`` <br>
3) Install ipykernel: ``pip install ipykernel`` <br>
4) Band the kernel with environment: ``python -m ipykernel install --name {place env name}`` <br>

Then in this environment I install all needed packages using pip or conda.
To use these installed libraries I launch jupyter notebook from the environment it was installed (e.g., from the ``base``) and then:
1) in jupyter notebook I choose the right kernel from the list of kernels; <br>
2) in terminal I use separate tab, where I activate right environment ({place env name}), and where I install required libraries. Thus I can import them in jupyter notebook, because I go for them to exactly where I placed them. <br>

