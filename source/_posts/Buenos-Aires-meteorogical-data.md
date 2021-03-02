---
title: Buenos Aires meteorogical data
date: 2021-01-02 11:55:38
summary: Public dataset of Buenos Aires climate
description: Public dataset of Buenos Aires climate
tags:
---

Through [this website](https://www.aysa.com.ar/Que-Hacemos/estaciones-meteorologicas/datos#) a water supply company called Aysa provides information on different meteorological variables in different areas of Buenos Aires. There are data from the last day but the historical data is lost, using a [simple script](https://github.com/mathigatti/aysa-datos-meteorologicos/blob/main/downloader.gs) I store this data and update [this spreadsheet](https://docs.google.com/spreadsheets/d/1qgud2AiHhAy-r8yfP5FOSSDSZ3H0ILY-G6xlpFhweug/edit?usp=sharing) every hour in order to generate an extensive public dataset of the meteorological data of Buenos Aires.


Access to the public dataset: [here](https://docs.google.com/spreadsheets/d/1qgud2AiHhAy-r8yfP5FOSSDSZ3H0ILY-G6xlpFhweug/edit#gid=0)


## Provided variables
- Wind speed (km / h)
- Temperature (ºC)
- Wind Speed (gust) (km / h)
- Pressure (hPa)
- River level (m)
- Daily Accumulated Rain (mm)
- Humidity (%)
- Wind Direction (°)

# Technical details

This program works from a simple Google Sheet spreadsheet to which a Script Editor with Google App Script was configured to run [this script](https://github.com/mathigatti/aysa-datos-meteorologicos/blob/main/downloader.gs) and a trigger was set to execute the update_google_sheet (function) every hour. )

<img src="grafico_nivel_del_rio.png" width="100%" border="5" />