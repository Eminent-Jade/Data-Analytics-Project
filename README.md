# Data-Analytics-Project


## Project Overview

This is an exploratory data analysis on occupants' thermal comfort sensation in indoor environment in Rm.02.412(Data Arena) & Rm.12_431(Analysis Room)(refer to 'Images folder') of Building 11 of University of Technology, Sydney (UTS), using corresponding historical data (01 May 2021 - 30 Jul 2021) collected by EIF Research Data Sensors Interface 

https://eif-research.feit.uts.edu.au/.


In this project, we will focus on examining thermal comfort sensations in 2 rooms. To achieve that, python package - 'pythermalcomfort', ASHRAE thermal comfort Standard for indoor environments & it's theories were adopted for analyses & visualisations purposes

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

## Content

1. Extract data and build initial dataframes
2. Categorise data
3. Merge dataframes into one

3.1 Compare 'time differences' in dataframes before merging

3.2 Deciding 'left table' for 'merge_asof' function

4. Visualise trends & categories

5. Adopt package - 'pythermalcomfort', compute pmv & ppd indexes & visualisations

5.1 compute & visualise pmv & ppd indexes

5.2 Hypothesis on Rm. 02-412's time slots giving 'Warm/Hot' sensations

6. Conclusions


## Data Overview


Linear numeric data sets collected by 2 of the sensors located respectively in 2 rooms were used.

The Research Data Sensors Interface is funded by Australian Government's Education Investment Fund(EIF).


https://eif-wiki.feit.uts.edu.au/eif_overview

However, being told by the Technical Services Manager of the faculty (refer to 'Image' folder) due to technical/maintenance issues, only Temperature and Relative Humidity data sets were adopted for analyses in this project. and data sets were directly copied from url links to txt files rather than downloaded from the search engine. (refer to 'Data' folder)


## About UTS Bulding 11

With it's wide range of sustainability features (energy, water consumption etc.), UTS building 11 has once achieved '5 Star Green Star – Education Design v1' rating, awarded by the Green Building Council of Australia (GBCA).

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

Apart from sustainability aspects, indoor environmental factors such as thermal comfort, air quality also play crucial roles on occupants' experiences and building's popularity of it's own. 


## To achieve 'comfortable' sensations in indoor environment,
https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

 - -0.5 <= pmv <=0.5
 - ppd <= 10%

## Handy tool for thermal comfort calculations: 
https://comfort.cbe.berkeley.edu/

To simulate settings in my project:
 - Choose 'Relative humidity vs air temperature' in the option panel on top of the graph
 - Choose 'PMV method' in 'Select method'
 - Check 'Use operative temp' box
 - View different 'clothing level' & 'Metabolic rate' values


![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)


## Package used - pythermalcomfort, 
https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort
