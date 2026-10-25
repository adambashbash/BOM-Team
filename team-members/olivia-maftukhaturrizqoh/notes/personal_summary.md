# Olivia Maftukhaturrizqoh: What I worked on and what I learned

## What I worked on

**Semester 1.** 

- I followed the weekly tasks and built notebooks in my own folder. I started with data pipelines, then worked with radar data, producing visualisations of it. I also retrieved part of the ERA5 reanalysis data. I wrote workflow notebook for YSSY (Sydney Airport) and explored Himawari satellite data as an alternative data source, with notes on what it offers and its limits.

**Semester 2.**

- I Studied the SWIFT paper and then the CRAFT paper, working out what changed between versions and why, I wrote a comparison of CRAFT with NVIDIA's ATLAS, covering tokens, compression, and fixed versus learned encoders. Set up the project environment on my local PC and built animations of the interpolated wind data to check that the motion looked realistic. Checked the data pipeline and found that our normalisation statistics were wrong because of float32 rounding. The fix is to compute them in float64. Reviewed the team's encoder and model notebooks, including the windows, the time-based split and the training-only normalisation. Wrote documentation of the data processing workflow, the channel inventory and data access. Updated the risk register in Sprint 6.

## What I learned

- How radar data works and what it is good for: it shows where precipitation is now, which makes it useful for very short-term forecasts, and I practised visualising it. What satellite data such as Himawari offers as an alternative source: wide coverage and frequent images, with different strengths and limits from radar and from model data. How to retrieve and handle reanalysis data (ERA5), and how to build a repeatable data pipeline in notebooks. That choosing a data source means weighing coverage, update frequency, resolution and how easy the data is to access.

- Semester 2: the data we actually used. Data Channels: five surface fields (10 m U and V wind, wind gust, screen temperature, surface pressure), that especially rain was is accumulated and does not interpolate cleanly. Data properties: ACCESS-SY is the Bureau of Meteorology's Sydney model, on a grid of 744 x 892 cells (about 1.5 km), with hourly states from September 2020 to May 2024. Latitude runs from north to south. The data is stored as long-format parquet, one row per grid cell and time, split into shards with a manifest file.
- Technical: how a CNN encoder compresses a weather grid into tokens, how a transformer forecasts in that compressed space, and why the trade-off between compression and detail matters. I also learned to read large NetCDF and parquet files, split by time to avoid leakage, and check numbers instead of trusting them (float32 rounding gave wrong statistics until we used float64).
- **Working with others:** reading teammates' code critically, keeping a clear written record, and working through setup problems (Python environments, Git history, memory limits) with patience.
- **Project work:** adapting when the plan changed.