# Data-Analytics-Project


## Project Overview

This is an exploratory data analysis project to find out occupants' thermal comfort levels in indoor environment in Rm. 02.412 (Data Arena) & Rm. 12_431 (Analysis Room) of Building 11 of University of Technology, Sydney (UTS), by analysing and visualising historical temperature & humidity data sets, and the corresponding computed results of thermal comfort indexes.

Subjects Covered

- Data Collection & Manipulation (NumPy, Pandas DataFrames & Series, change datatypes, merge, re-order columns)
- Data Visualizations, Univariate (Categorical features & Countplot) & Bivariate analyses (Lineplots, Scatterplots, Regression line, Jointplot)
- Descriptive Statistics (Boxplot, Max, Min, Mean, Standard Deviation, IQR)
- Application on external python package
- Explanatory Storytelling with data


## Data Overview

Linear numeric data sets of temperature and humidity were collected by separate sensors located in each room, for the period of 01 May 2021 to 30 Jul 2021 were used (refer to 'Images' folder).

The Research Data Sensors Interface is funded by Australian Government's Education Investment Fund (EIF), in order to monitor renewable energy generation system, and several internal and external environmental factors of the building.

https://eif-research.feit.uts.edu.au/

https://eif-wiki.feit.uts.edu.au/eif_overview

However, being told by the Technical Services Manager of the faculty (refer to 'Image' folder for email conversation) due to technical/maintenance issues, only Temperature and Relative Humidity data sets were adopted for analyses in this project. and data sets were directly copied from url links to .txt files rather than downloaded from the search engine (refer to 'Data' folder).


## About thermal comfort, predicted mean vote(pmv) & percentage of dissatisfied(ppd)

Thermal comfort is the occupants' sensations that expresses satisfaction with the thermal environment sensation dependent on several factors, including but not limited to, air temperature, mean radiant temperature, humidity, relative air speed, metabolic rate and clothing level, in this project we will adopt 'pmv/ppd method', developed by a Danish Professor, Povl Ole Fanger.

In simple words, 'PMV' is an index that aims to predict the mean value of votes of a group of occupants on a seven-point thermal sensation scale, 'PPD' is an another index to relate 'PMV' to predict the percentage of thermally dissatisfied occupants.

According to ASHRAE Standard 55, Comfort Zone represents a predicted mean vote (pmv)of -0.5 to +0.5 & percentage of dissatisfied (ppd) <= 10% for buildings where the occupants have metabolic rates of between 1.0 met and 1.3 met and clothing provides between 0.5 clo and 1.0 clo of thermal insulation.

Further readings for understanding thermal comfort theories,

https://www.designingbuildings.co.uk/wiki/Predicted_mean_vote

https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

https://www.designingbuildings.co.uk/wiki/Indoor_air_velocity

https://roastsurvey.com/blog-post/understanding-clo-values/

http://www.sensiblehouse.org/nrg_comfort.htm

https://www.designingbuildings.co.uk/wiki/Operative_temperature


## Assumptions

To simulate the context of the analyses, several assumptions are to be made,

- Air temperature = mean radiant temperature (becomes 'operative temperature', assuming relative air speed = 0.1 m/s, i.e. negligible heat transfer between ambient air & indoor surfaces, e.g. wall, floor, ceiling.)
- Relative air speed (vr) = 0.1 m/s (for simple heat transfer calculations)
- Clothing level (clo) = 1.0 clo (typical winter indoor clothing)
- Metabolic rate (met) = 1.1 met (typing, typical work situation for occupants in both rooms)


## Methodology

First manipulate, analyse and visualise temperature & humidity data sets, find their trends, relationships and categories distributions.

Next, apply python package - 'pythermalcomfort' and 'ASHRAE (American Society of Heating, Refrigerating, and Air Conditioning Engineers) Thermal Comfort Standards for indoor environments' and related theories to compute thermal comfort indexes, 'pmv & ppd', and analyse and visualise them in similar ways. 

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd

Then, compare the representativenesses between 'temperature & humidity' and 'pmv & ppd' indexes in terms of indoor thermal comfort sensations of occupants.

Lastly, apply a different clothing level of occupants in a part of time slots that gave 'Warm/Hot' sensations in terms of 'pmv', and compute new 'pmv & ppd' indexes to see the rate of improvements.


## About UTS Building 11

With it's wide range of sustainability features (energy, water consumption etc.), UTS building 11 has once achieved '5 Star Green Star – Education Design v1' rating, awarded by the Green Building Council of Australia (GBCA).

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

Apart from sustainability aspects, indoor environmental factors such as thermal comfort, air quality also play crucial roles on occupants' experiences and building's popularity of it's own.


## Handy tool for thermal comfort calculations

https://comfort.cbe.berkeley.edu/

To simulate settings in my project,

- Choose 'Relative humidity vs air temperature' in the option panel on top of the graph
- Choose 'PMV method' in 'Select method'
- Check 'Use operative temp' box
- View different 'clothing level' & 'Metabolic rate' values,
- Then insert any temperature & humidity you like, e.g.

![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)
