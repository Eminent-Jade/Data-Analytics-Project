# Data-Analytics-Project


## Project Overview

This is an exploratory data analysis on occupants' thermal comfort sensation in indoor environment in Rm. 02.412 (Data Arena) & Rm. 12_431 (Analysis Room) of Building 11 of University of Technology, Sydney (UTS) (refer to 'Images' folder), using corresponding historical temperature & humidity data sets (01 May 2021 - 30 Jul 2021) collected by EIF Research Data Sensors Interface.

https://eif-research.feit.uts.edu.au/

To achieve that, python package - 'pythermalcomfort', ASHRAE Thermal Comfort Standard for indoor environments & it's theories were applied on temperature & humidity data sets for analyses & visualisations purposes.

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd


To simplify the context of the project, several assumptions are to be made,

- air temperature = mean radiant temperature (becomes 'operative temperature', assuming  relative air speed, i.e. negligible heat transfer between ambient air & indoor surfaces, e.g. wall, floor, ceiling.)

- relative air speed (vr) = 0.1 m/s (for simple heat transfer calculations)

- clothing level (clo) = 1.0 clo (typical winter indoor clothing) 

- metabolic rate (met) = 1.1 met (typing, typical work situation for occupants in both rooms)


## Subjects covered

 - Data collection & manipulation (NumPy, Pandas DataFrames & Series, change datatypes, merge, re-order columns)
 - Data visualizations, Univariate (Categorical features & Countplot) & Bivariate analyses (Lineplots, Scatterplots, Jointplot)
 - Descriptive Statistics (Boxplot, Max, Min, Mean, Standard Deviation, IQR)
 - Explanatory story telling with data


## Content

1. Extract data and build initial dataframes
2. Categorise data
3. Merge all temperature & humidity dataframes into one
4. Visualise trends & categories
5. Adopt package - 'pythermalcomfort', compute pmv & ppd indexes & visualisations
6. Apply new 'clo' value on Rm. 02-412's time slots that originally gave 'Warm/Hot' sensations
7. Conclusions


## Data Overview

Linear numeric data sets of temperature and humidity collected by separate sensors located in each room were used.

The Research Data Sensors Interface is funded by Australian Government's Education Investment Fund (EIF).

https://eif-wiki.feit.uts.edu.au/eif_overview

However, being told by the Technical Services Manager of the faculty (refer to 'Image' folder for email conversation) due to technical/maintenance issues, only Temperature and Relative Humidity data sets were adopted for analyses in this project. and data sets were directly copied from url links to txt files rather than downloaded from the search engine (refer to 'Data' folder).


## About UTS Building 11

With it's wide range of sustainability features (energy, water consumption etc.), UTS building 11 has once achieved '5 Star Green Star – Education Design v1' rating, awarded by the Green Building Council of Australia (GBCA).

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

Apart from sustainability aspects, indoor environmental factors such as thermal comfort, air quality also play crucial roles on occupants' experiences and building's popularity of it's own. 


## About thermal comfort, predicted mean vote(pmv) & percentage of dissatisfied(ppd)

Thermal comfort is the sensation that expresses satisfaction with the thermal environment sensation dependent on several factors, including but not limited to, air temperature, mean radiant temperature, humidity, relative air speed, metabolic rate and clothing level, in this project we will adopt 'pmv/ppd method'.

According to ASHRAE Standard 55, Comfort Zone represents a predicted mean vote (pmv)of -0.5 to +0.5 & percentage of dissatisfied (ppd) <= 10% for buildings where the occupants have metabolic rates of between 1.0 met and 1.3 met and clothing provides between 0.5 clo and 1.0 clo of thermal insulation.

Further readings for understanding thermal comfort theories,

https://www.designingbuildings.co.uk/wiki/Predicted_mean_vote

https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

https://www.designingbuildings.co.uk/wiki/Indoor_air_velocity

https://roastsurvey.com/blog-post/understanding-clo-values/

http://www.sensiblehouse.org/nrg_comfort.htm

https://www.designingbuildings.co.uk/wiki/Operative_temperature


## Handy tool for thermal comfort calculations

https://comfort.cbe.berkeley.edu/

To simulate settings in my project,

 - Choose 'Relative humidity vs air temperature' in the option panel on top of the graph
 - Choose 'PMV method' in 'Select method'
 - Check 'Use operative temp' box
 - View different 'clothing level' & 'Metabolic rate' values, 

then insert any temperature & humidity you like, e.g.

![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)
