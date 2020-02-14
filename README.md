# Continent Intelligence Study 

# EXECUTIVE SUMMARY 

# AIMS AND OBJECTIVES

The aim of this project is to measure one’s ability to gather information from a real-world database and appraise their knowledge of statistical analysis, and hypothesis testing, to generate analytical insights that can be meaningful to the company/stakeholder.
For this project, a dataset must be selected in order to perform statistical analyses and hypothesis testing, to answer at least three questions from the data source of choice.
For each hypothesis, both the null hypothesis and the alternative hypothesis must be specified for each research question. Also, the statistical tests chosen for the project must be clearly described (independent t-test, dependent t-test, ANOVA etc.).
The use of alternative datasets brings with it a question of who your audience is for this data science project. Once a stakeholder is picked, it is important to keep them in mind whilst performing the appropriate statistical analysis. When translating statistics for a non-technical audience, be sure to answer questions that are relevant to the stakeholder and being clear with the limitations of the findings.

# DATASET

The data used in this project was extracted from the World Book Fact, from the Central Intelligence Agency (CIA) official website: https://www.cia.gov/library/publications/the-world-factbook/
The World Factbook provides information on the history, people and society, government, economy, energy, geography, communications, transportation, military, and transnational issues, for 267 world entities. The Reference tab includes: a variety of world, regional, country, ocean, and time zone maps; Flags of the World; and a Country Comparison function that ranks the country information and data in more than 75 Factbook fields.
In the World Book Fact, the following data frames were selected from the Guide to Guide Comparisons: Airport;, Area, Budget; Continent; Currant Accounts (import and export deficit); Debt Foreigners, Education Spend; Electric Consumption; emissions (CO2); Exports; Fossil electricity; Gross Domestic Product (GDP); GDP Growth; GDP Growth; GDP per capita; Hydroelectricity; Imports; Industry Product Growth; Internet users; Life expectancy; Marine Merchant; Migration; Military Expenditure; Natural Gas Consumption; Nuclear Electricity; Other Renewable electricity; Petroleum Consumption; Population Growth; Population; Public Debt; Railways; Unemployment; Waterways; and Workforce. 
The variables central to this study are: Country; Continent; CO2 emissions; Internet users; Daily Petroleum Consumption; Renewable electricity; and Military Expenditure. Nonetheless, several variables remained within the data frame so that further investigations regarding the continental effects upon political socio-economical facts in several world entities. 


# DELIVERABLES

1. A Jupyter Notebook containing well-formatted, professional looking markdown cells explaining any substantial code. All functions have docstrings that act as professional-quality documentation. The notebook is written to technical audiences with a way to both understand the approach and reproduce the results. The target audience for this deliverable is other data scientists looking to validate your findings. The notebook should be well organized, easy to follow, and code is commented where appropriate. Finally, notebook should clearly show how the results were achieved for each hypothesis test, including how the p-values were calculated. 
2. A user focused README.md file that explains the process, methodology and findings, and clearly showing both technical expertise and ability to communicate the results. 
3. PowerPoint/Google Slide presentation that explains the hypothesis testing, findings, and their relevance to the company/stakeholders. Contain between 5-10 professional quality slides detailing: (a) A high-level overview of your methodology; (b) The results of your hypothesis tests; (3) Any real-world recommendations it can be made based on the findings.

# INTRODUCTION

Today, as we discuss global topics such as climate change, one important factor always comes to mind: the amount of carbon emissions being produced and its impact on the environment. 
The largest source of increasing CO2 in the atmosphere is the burning of fossil fuels and vegetation – as the result of human activity. Globally, humans produce over 40 billion tonnes of CO2 every year. 41 countries (each emitting more than 100 million tonnes) are responsible for the lion’s share (90%) of carbon emissions (source https://ecotricity.co.nz/). 
The growing concern regarding CO2 emissions is such that CO2 policies and regulations are now in place and dictates the amounts of CO2 quotas companies are allowed to emit or sell their carbon credits to each other. One example of such a scheme is the 'Cumulative Emissions, Global Carbon Budgets and the Implications for Climate Mitigation Targets' was launched in 2015 to highlight the emerging science of the climate response to cumulative emissions, and how this can inform efforts to decrease emissions fast enough to avoid dangerous climate impacts. 
The present study comprises a comparative analysis across the continents regarding 5 potentially related factors: renewable energy; daily consumption of petroleum; internet usage; military expenditure; and CO2 emissions. 

# HYPOTHESES 

H1 – There are continental differences in CO2 emissions 
H0 – There are no differences in CO2 emissions 
H2- There are continental differences in renewable energy production 
H0 – There are no differences in renewable energy production
H3 - There are continental differences military expenditure 
H0 – There are no continental differences military expenditure
H4 – There are continental differences in internet usage 
H0 – There are no continental differences in the internet usage
H5 – There are continental differences in daily petroleum consumption 
H0 – There are no continental differences in daily petroleum consumption

# METHODOLOGY

The final data frame in this project is a compilation of several data sets extracted from the CIA website, ‘The World Fact Book’, and converted the files into csv. A continent column was created to cluster the countries into continents, which allowed for the merging of the data. Left and outer joins were used in order to merge the data. 
The data was inspected for null values. For the internet usage variable, the null values for the Afghanistan and Sudan were replaced by the median of their continent group, as opposed to the mean, in order to control for the extrapolations of the outlier values. The remainder null values were replaced by 0.0 values, as they regarded very small islands with no reported internet usage. Moreover, for the military expenditure variable, the null values for Qatar and Syria were replaced by the median of their continental group, to control for extrapolation. The remainder null values were replaced by 0.0 values, as research showed that such countries do not have military bodies, or recently abolished theirs. 
Following the procedural data cleanse, exploratory analysis was conducted in order to assess whether the data met the appropriate assumptions for the chosen statistical analysis. The residuals, that is, difference between the entered value and the mean of all values for that group, were found to be normally distributed. Moreover, the data was found to be homoscedastic, which indicates that a dependent variable's variability is equal across values of the independent variable. To verify whether the data was homoscedastic, Levene’s statistics were conducted across all variables. Based on those findings, the variable Military expenditure was dropped from the data. 
Due to the cumulative risk of drawing false conclusions when statistically testing multiple quantities simultaneously, Bonferroni correction was used to minimize the chance of type 1 errors, in which 𝛼 is divided by the number of comparisons you are making to set a new, adjusted threshold rejecting the null hypothesis. After the Bonferroni test, the alpha was corrected to 0.010206. 
One-way ANOVAs statistics were conducted in order to compare continental differences across all experimental variables. Finally, post hoc Tukey’s HSD tests were performed in order to assess the breakdown of the multiple comparisons. 

# FINDINGS

The present investigation found that there were no significant differences for CO2 emissions, petroleum consumption and internet usage amongst all continents. However, there were significant differences for renewable energy across the continents. 
Further analysis was included to investigate the extend of such significant results. Post Hoc Tukey HSD test analysis showed that for renewable energy, the significant differences were only observable in the comparisons between Europe and Asia, and Europa and North America. 

# CONCLUSION

This project aimed to analyse a compilation of several data sets extracted from the CIA website, ‘The World Fact Book’, with continent column was created to cluster the countries into continents, which allowed for the merging of the data.
Exploratory data analysis was conducted in order to assess whether the met the assumption of the ANOVA statistics, including Levene statistics, distribution function of residuals. One-way ANOVAs were performed to compare differences in petroleum consumption, internet usage, CO2 emissions, and renewable energy across all continents. In Addition, Post Hoc Tukey HSD analysis were used in order to investigate the significant results. 
The present investigation found that there were no significant differences for CO2 emissions, petroleum consumption and internet usage amongst all continents. However, there were significant differences for renewable energy and military expenditure across the continents. Post hoc analysis showed that those significant differences were only observable in few continental comparisons. 
There were limitations encountered in this project. Firstly, due to the approach used to compile the data frame, it was not possible to apply neither of the recommend OOP Refactors. Moreover, the instructions provided for this project entailed the use of reductive statistical analysis, which limited the potential understanding of the data used for this project. Therefore, further analysis must take place in order to assess other potential relating factors with regards to CO2 emissions. 
Nonetheless, the findings presented in this project offer a comprehensive insight of the continental trends regarding relevant issues including carbon emissions and renewable energy, which can inform future policies and regulations, as well as aid the advancement of knowledge in the research field. 

