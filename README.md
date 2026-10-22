# atmos-satellite

Measured cloud-top temperatures over India for [AtmosIQ](https://github.com/gowthamgta/Atmos)'s 3D clouds, served by GitHub Pages at
https://gowthamgta.github.io/atmos-satellite/:

- `bt-h9/index.json`: Himawari-9 AHI, 10.4 and 3.9 um, parallax-corrected, empty where the satellite sees too slantwise (NOAA open data on AWS)
- `bt/index.json`: Meteosat SEVIRI (Indian Ocean service), 10.8 and 3.9 um (EUMETSAT Data Store)

Each frame is a PNG on a 0.03 degree grid over 68-97.5 E, 5-37.5 N: red = 10.8 (10.4) um, green = 3.9 um, kelvin = offsetK + value x stepK
(0 = no data). The last hour is kept.

The code lives in Atmos (`pipeline/satellite_restore.py`, `satellite_bt.py`, `himawari_bt.py`); the workflow here runs it every 10 minutes
(started by cron-job.org) and deploys the result with Pages, so nothing piles up in this repository's history.

Data: Himawari-9 © JMA (via NOAA Open Data Dissemination); Meteosat © EUMETSAT.
