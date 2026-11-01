# The code behind GEOS 212: Water in the West

Many figures in the GEOS 212 lecture slides (Boise State University, Department of Geosciences) are made from real, public data: snowpack measured at SNOTEL stations in the Boise Mountains and streamflow measured at USGS stream gages on the Boise River. This repository has the code behind those figures, written as narrated [Jupyter notebooks](https://jupyter.org/) you can run, change, and extend.

You don't need to be a programmer to start. If you finished the Module 07 Python lab, you already know enough to read these notebooks, and each one ends with a few "Your turn" ideas to try.

## Why code?

Modern hydrology runs on data and code. With a few dozen lines of Python you can download decades of measurements from any of about 900 SNOTEL stations or 10,000 USGS stream gages, redo an analysis for a new year or place in seconds, and leave a written record of every step so anyone can check your work. These notebooks are a small window into how working hydrologists, water managers, and forecasters actually spend their days.

## The course through line: one Boise River water year

GEOS 212 follows water through the Boise River basin over one water year (October 1 to September 30): from Pacific storms, to the mountain snowpack, to soil, to the river, to groundwater, and to the people who use it. The notebooks follow the same path.

| Module | Notebook | Data | Open in Colab |
|---|---|---|---|
| 02 Energy budget | [Where it rains, seen from space](notebooks/02_where_it_rains.ipynb): 20-year satellite precipitation map, the ITCZ and dry subtropics, and checking global rainfall against the IPCC energy budget | NASA GPM IMERG | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/02_where_it_rains.ipynb) |
| 04 Snow drought | [Snow drought in the Boise Mountains](notebooks/04_snow_drought.ipynb): WY2023 (snowy) vs WY2026 (snow drought), rain vs snow, warm vs dry snow drought, what the river did | NRCS SNOTEL 978, 637, 306; USGS 13185000 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/04_snow_drought.ipynb) |
| 04 Snow drought | [Snow drought seen from space](notebooks/04b_snow_drought_from_space.ipynb): WY2023 vs WY2026 precipitation across the West as % of average (with a simple bias correction), and how high the April 1 snow line sat | NASA GPM IMERG; MODIS snow cover | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/04b_snow_drought_from_space.ipynb) |
| 05 Snowpack and forecasting | [From snowpack to streamflow forecast](notebooks/05_snow_to_streamflow_forecast.ipynb): April 1 SWE vs April-July volume, a least-squares forecast for 2026 with uncertainty, snow densification | NRCS SNOTEL 312; USGS 13235000 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/05_snow_to_streamflow_forecast.ipynb) |
| 05 Snowpack | [Checking the snow pillow with a shovel](notebooks/05b_snow_pits_vs_snotel.ipynb): NASA SnowEx snow pits vs. the Banner Summit SNOTEL pillow, and snow densification | NASA SnowEx; NRCS SNOTEL 312 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/05b_snow_pits_vs_snotel.ipynb) |
| 09 Soil moisture | [Same soil, different winters](notebooks/09_soil_moisture_smap.ipynb): SMAP root-zone soil moisture in WY2023 vs. WY2026 at Banner Summit and the Dry Creek foothills | NASA SMAP L4 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/09_soil_moisture_smap.ipynb) |
| 10 Rivers | [A natural river and a managed river](notebooks/10_natural_vs_regulated.ipynb): Twin Springs vs Glenwood Bridge, flow duration curves | USGS 13185000, 13206000 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/10_natural_vs_regulated.ipynb) |
| 10 Rivers | [Building a rating curve](notebooks/10b_rating_curve.ipynb): pairing USGS field measurements, fitting Q = C(h − e)^b, and how the rating shifted after the 2017 flood | USGS 13206000 field measurements | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/10b_rating_curve.ipynb) |
| 11 Groundwater | [Weighing the water under the Snake River Plain](notebooks/11_grace_groundwater.ipynb): GRACE satellite total water storage, seasonal cycle vs. wet and dry years, trend, and converting to acre-feet | NASA/JPL GRACE and GRACE-FO | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LejoFlores/geos212-code/blob/main/notebooks/11_grace_groundwater.ipynb) |

More notebooks will be added as more slides get real-data figures.

## How to run the notebooks

**Easiest: Google Colab (nothing to install).** Click an "Open in Colab" badge above and sign in with a Google account (your Boise State account works). Then choose *Runtime > Run all*, or click each code cell and press **Shift + Enter**.

**On your own computer.** Install [Anaconda](https://www.anaconda.com/download) or Miniconda, then in a terminal:

```bash
git clone https://github.com/LejoFlores/geos212-code.git
cd geos212-code
pip install -r requirements.txt
jupyter lab
```

and open a notebook from the `notebooks/` folder.

You can also just *read* the notebooks right here on GitHub: every one is saved with its figures already drawn.

## Where the data come from

Every notebook downloads its data live from the agency that collects it:

* **NRCS SNOTEL** snowpack, precipitation, and temperature, through the [Report Generator](https://wcc.sc.egov.usda.gov/reportGenerator/).
* **USGS NWIS** daily streamflow, through [waterservices.usgs.gov](https://waterservices.usgs.gov/).
* **NASA SnowEx, SMAP and MODIS** (snow pits, soil moisture, snow cover), from [NSIDC](https://nsidc.org/). These also need an Earthdata account, so the notebooks use saved summary tables.
* **NASA/JPL GRACE and GRACE-FO** satellite gravity (total water storage), from [PO.DAAC](https://podaac.jpl.nasa.gov/). Also needs an Earthdata account, so the notebook uses a saved regional summary.
* **NASA GPM IMERG** satellite precipitation, from [NASA GES DISC](https://disc.gsfc.nasa.gov/). Downloading it needs a free [NASA Earthdata](https://urs.earthdata.nasa.gov/) account, so these notebooks use summarized copies saved in `data/` and show the download code as an optional step.
* **USGS Water Data API** stream gaging field measurements, through [api.waterdata.usgs.gov](https://api.waterdata.usgs.gov/).

A copy of each file is saved in [`data/`](data/). If a download fails (no internet, or an agency changes its website, which happens), the notebooks automatically use the saved copy, so they keep working.

Data for water year 2026 (Oct 2025 to Sep 2026) are **provisional**: the agencies haven't finished checking them, and values may change slightly.

## Repository layout

```
notebooks/   one notebook per lecture topic, named by module number
data/        saved copies of the downloaded data (used as a fallback)
```

## Questions or ideas?

Bring them to class or office hours, or open an [issue](https://github.com/LejoFlores/geos212-code/issues) on this repository.
