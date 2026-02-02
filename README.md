# WatershedsAndCyanobacteria
Using descriptive statistics to determine the impact nutrients from pesticide runoff have on levels of cyanobacteria and whether the type of watershed (agricultural, non-agricultural, forest) and precipitation could also make a difference.


About this project:

This project was inspired by salamanders, creatures that are especially vulnerable to climate 
change due to their sensitivity to pollutants in water. Data on salamanders was not easily 
accessible, so the idea evolved to focus on how cyanobacteria is impacted by agricultural 
pollutants because cyanobacteria is also heavily related to nutrient pollution from compounds 
like nitrogen and phosphorus. 
This topic is important to discuss because it impacts not only the daily lives of real people 
who work in the agriculture industry, but also because this has long-term implications 
on the ecosystems that are necessary to keep our planet alive and healthy. 
Furthermore, this also affects the people who rely on these food systems and trust that the food 
they eat is safe. Pesticide resistance has become more prevalent and requires not only more pesticides 
to be used but also a mixing of pesticides, which poses not only health concerns but also 
economic concerns. By exploring different variables, it was found that agriculture versus 
non-agriculture water reservoirs does play a role in cyanobacteria growth. 
Future research should explore other variables, like dissolved oxygen, 
irradiance, and sulfur, which could improve the models explanatory power with robust data.


About the data:

The dataset used is titled “1987-2018 cyanobacteria and water quality data for 20 reservoirs” 
(U.S. EPA Office of Research and Development (ORD), 2021) that was chosen is from the US 
EPA (Environmental Protection Agency) which was inspired by the researcher’s desire to 
observe how 1 cyanobacteria potentially contributes to climate change. Specifically, they wanted 
to study if increasingly severe cyanobacterial blooms and deep water hypoxia coincide with 
warming water temperatures in reservoirs.

The data used was collected from various reservoirs in Indiana, Kentucky, and Ohio from 
1987-2018. The data consists of samples taken from 20 different reservoirs spanning over 30 
years. The data was separated into different groups based on the location of the reservoirs. These 
groups are forested watersheds, agricultural watersheds experiencing seasonal stratification, 
agricultural watersheds without seasonal stratification, and 1 urban watershed. (WFR) West Fork 
Lake was omitted from the data set for simplicity because this reservoir was the urban watershed 
with no seasonal stratification, the only one of it’s type in the dataset. 

The variables are describes as follows for each reservoir: yearly cyanobacteria maximum 
cell densities (MAXCD), 3 Total nitrogen (mg/l) in surface water (TN), 2 total phosphorus (mg/l) 
in surface water (TP), and precipitation standardized z-scores are summer (June-August) 
precipitation amounts transformed into reservoir-specific standardized  z-scores based on data 
from all years (PRECIP), and annual May-October 4 surface water temperatures in celsius 
(SurfaceWaterTemp). Also, isAg is a manual binary variable that was added to explain if a 
reservoir was Forest or Agriculture in nature.


How to run this code:

1. Ensure you download the R script from the most recent commit
  
2. Ensure the csv files are inside the same folder as the R studio project

3. Restart R before installing packages, then install the 4 required packages by holding CTRL+ENTER for each line

4. Install the libraries by holding CTRL+ENTER for each line OR highlight the chunk of code then hold CTRL+ENTER

5. The csv files are stored into useable variables in R by using fread. Use CTRL+ENTER to get all the variables

6. Then you should view the data and continue running the code line by line

7. The output for stargazer can be put into tables by pasting it into: https://www.quicklatex.com/



Methods:

The variables are describes as follows for each reservoir: yearly cyanobacteria maximum 
cell densities (MAXCD), 3 Total nitrogen (mg/l) in surface water (TN), 2 total phosphorus (mg/l) 
in surface water (TP), and precipitation standardized z-scores are summer (June-August) 
precipitation amounts transformed into reservoir-specific standardized  z-scores based on data 
from all years (PRECIP), and annual May-October 4 surface water temperatures in celsius 
(SurfaceWaterTemp). Also, isAg is a manual binary variable that was added to explain if a 
reservoir was Forest or Agriculture in nature. 


Results and Analysis:

In Model 1, it was found that a 1% increase in total nitrogen (TN) leads to a 0.37% 
increase in cyanobacteria (MaxCD), which indicates a positive relationship between total 
nitrogen and cyanobacteria. In Model 2, it was found that a 1% increase in total nitrogen (TN) 
leads to a 0.08% increase in cyanobacteria (MaxCD), which indicates a positive relationship 
between total nitrogen and cyanobacteria. 

Although the relationship between total phosphorus (TP) and cyanobacteria (MaxCD) are 
both positive, the relationship between total phosphorus TP and cyanobacteria (MaxCD) is 
stronger in the first model compared to the second model because total phosphorus (TP) is 
significant at the point 2 level for the first model and not the second model. Additionally, the first 
model shows that a 1% increase in total phosphorus (TP) leads to a 0.41% increase in 
cyanobacteria (MaxCD) and the second model shows that a 1% increase in total phosphorus (TP) 
leads to a 0.30% increase in cyanobacteria (MaxCD). 

In both models there is a negative relationship between surface water temperature and 
cyanobacteria. For example in Model 1, a 1% increase in surface water temperature 
(SurfaceWaterTemp) leads to 1.73% decrease in cyanobacteria (MaxCD) and in Model 2, a 1% 
increase in surface water temperature (SurfaceWaterTemp) leads to a 1.98% decrease in 
cyanobacteria (MaxCD). 

From the results of the dummy variable, there is a 113.5% difference in cyanobacteria 
growth between agricultural watersheds compared to non-agricultural watersheds. In Model 1, a 
one standard deviation (since precipitation was measured in standardized z scores) increase in 
precipitation leads to coefficient 0.2% decrease in cyanobacteria (MaxCD) because the data for 
precipitation is in standardized z scores. Meanwhile, in Model 2,  a one standard deviation 
increase in precipitation leads to coefficient 2.9% increase in cyanobacteria (MaxCD) because 
the data for precipitation is in standardized z scores. 

It was suspected that there was potential collinearity between precipitation variable 
(Precip) and the agriculture/non-agriculture reservoir binary variable (isAg) because 
precipitation was positive when the isAg variable was added in Model 2 but negative when the 
isAg variable was omitted in Model 1. However, the vif() test returned a value between 1 and 2, 
which means no multicollinearity was present.  

Both models demonstrate there is a positive relationship between Nitrogen and 
Cyanobacteria Cell Density, which aligns with pre-existing literature. Both models also 
demonstrate there is a positive relationship between Phosphorus and Cyanobacteria Cell Density, 
which also aligns with pre-existing literature, as phosphorus runoff has been observed to be the 
largest contributor to Cyanobacteria. In the first model, there is a weak negative relationship 
between precipitation and cyanobacteria cell density. In the second model, there is a weak 
positive relationship between precipitation and cyanobacteria cell density. Both models 
demonstrate that there is not a strong relationship between precipitation and Cyanobacteria. This 
demonstrates the complex relationship between the two variables. Both models also demonstrate 
that within the data there is a negative relationship between surface water temp and 
Cyanobacteria. This does not necessarily align with pre-existing literature which finds that 
higher water temps lead to more cyanobacteria growth. Finally, the second model demonstrates 
that there is a positive relationship between agriculture watersheds and Cyanobacteria Cell 
Density, which aligns with pre-existing literature (Reichwaldt & Ghadouani, 2012). 
In Model 1, the only variable that significantly improved the model's explanatory power 
was total phosphorus (TP) because it had a p-value of less than 0.05 (0.01). Also, total nitrogen 
(TN) was not less than 0.05 but it was the only other variable that came close because it had a 
p-value of 0.061. 

In Model 2, the only variable that significantly improved the model's explanatory power 
was the binary variable for agriculture/non-agriculture (isAg) because it had a p value of 0.01. 
Something that was noticed was that although the first model had indicated that total nitrogen 
(TN) had the best explanatory power, once isAg was added in the second model total phosphorus 
increased to 0.06. Furthermore, the AIC and BIC tests were conducted for both models and 
overall Model 2 was a better fit because the AIC test returned a lower value for Model 2. For 
Model 1, it was 1284.2 and it was 1279.7 for Model 2. It was concluded from the BIC test that 
Model 2 was a better fit but the difference was marginal because Model 1 returned a BIC of 
1305.7 and Model 2 returned a BIC of 1304.7.  

The adjusted R squares were low for both models (0.05% for Model 1 and 0.065% for 
Model 2). Although this means that the explanatory power for both models is low, there were 
still significant results for some of our coefficients. Therefore, it should be noted that there may 
be other variables that may better explain the growth of cyanobacteria better that weren’t 
included in our research. There might also be variables that don’t have data readily available or 
as easily accessible such as irradiance or even levels of sulfur, which were not studied in our 
project. Collection processes chosen could also play a role in the results of the data because “it 
could be possible that suspiciously high or low temperatures could have been dependent on 
actual depth measured at the surface (particularly 0-depth measurements), time of day, or any 
brief mixing events”, according to the research documentation from the researchers who 
provided the dataset used. 

The null hypothesis is not rejected as there is not a significant relationship between 
measured maximum Cyanobacteria cell density and measured levels of phosphorus, nitrogen, 
precipitation and surface water temperature. 
