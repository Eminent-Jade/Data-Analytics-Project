# Data-Analytics-Project 
This is a simulated analytical report on thermal comfort indexes for indoor environment in Rm.02.412(Data Arena) & Rm.12_431(Analysis Room) of Building 11 of UTS based on historical data (01 May 2021 - 30 Jul 2021) collected by EIF Research Data Sensors Interface https://eif-research.feit.uts.edu.au/, computed using package 'pythermalcomfort'.

## Content

- Project Overview
- Data Overview
1. Extract data and build initial dataframes
2. Categorise data
3. Merge dataframes into one
 3.1 Compare 'time differences' in dataframes before merging
 3.2 Deciding 'left table' for 'merge_asof' function
4. Visualise trends & categories
5. Adopt package - 'pythermalcomfort', compute pmv & ppd indexes & visualisations
 5.1 compute & visualise pmv & ppd indexes
 5.2 Hypothesis on Rm. 02-412's time slots giving 'Warm/Hot' sensations
- Conclusions

![image](https://user-images.githubusercontent.com/95272183/154760547-84df5c00-977b-4d92-96ef-e4f8378ee1e3.png)

# To achieve 'comfortable' sensations in indoor environment,
https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

 - -0.5 <= pmv <=0.5
 - ppd <= 10%

# Handy tool for thermal comfort calculations: 
https://comfort.cbe.berkeley.edu/

To simulate settings in my project:
 - Choose 'Relative humidity vs air temperature' in the option panel on top of the graph
 - Choose 'PMV method' in 'Select method'
 - Check 'Use operative temp' box
 - View different 'clothing level' & 'Metabolic rate' values


![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)


# Package used - pythermalcomfort, 
https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort
