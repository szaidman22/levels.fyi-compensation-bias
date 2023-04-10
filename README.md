# levels.fyi-compensation-bias

![download](https://user-images.githubusercontent.com/61389709/230993762-78eeff96-0ec7-4ba1-bc55-382ddebed069.png)

Background – Current Gender and Wage gaps in the US

In their 2021 Gender and Pay Gap Report, which analyzes pay disparities in the US across all industries via crowdsourced data, PayScale found that, without adding any control variables, women make 82¢ for every dollar earned by men. After adding control variables, women made 98¢ for every dollar earned by men, leaving a 2% difference attributable purely to discrimination based on gender.

PayScale’s findings on the racial wage gap show that, with or without control of demographics, both men and women of most races earn less than white men. Interestingly, when controlling for external factors, Asian men and women earn more than any group.

Data and Research Design
Levels.fyi is a website founded in 2017 as a place for tech industry professionals around the world to anonymously share detailed compensation information. In 2020, levels.fyi began collecting race, gender, and education information from users along with salary information.

Using data from levels.fyi, I asked the question: can any of the variance in compensation in the tech industry be explained by racial and gender differences? If so, how much of this variance can be attributed to differences in years of experience, job title, educational attainment, and cost of living between genders and racial groups?

My dependent variable was total annual compensation, with gender, race, education, total years of experience, years at the current company and cost of living index as independent variables.

My sample came from a comprehensive dataset of scraped salary postings from levels.fyi. I limited my analysis to jobs in the US and removed NA values for the target independent variables. I also removed records with total yearly compensation equal to 0. I joined this data to a separate table with cost of living index values by US state.

Hierarchical Regression Model
Stepwise multiple regression was used to assess whether gender and/or race would contribute any significant additional explanatory power to the prediction of total annual compensation beyond that of the control variables. The equations for each step of the hierarchical regression model are below:

Model 2a (control variables only): 

ln(Total Annual Compensation) = β0 + β1(Years of Experience) + β2(Years at Company) + β3(Education) + β4(Title) + β5(Index)

Model 2b (control variables + gender): 

ln(Total Annual Compensation) = β0 + β1(Years of Experience) + β2(Years at Company) + β3(Education) + β4(Title) + β5(Index) + β6(Gender)

Model 2c (control variables + gender + race): 

ln(Total Annual Compensation) = β0 + β1(Years of Experience) + β2(Years at Company) + β3(Education) + β4(Title) + β5(Index) + β6(Gender) + β7(Race)

Results
The adjusted R^2 value for model 2a was .410, meaning that 41% of the variance in total annual compensation in the sample could be explained by the control variables alone.

After controlling for years of experience, years at the company, education, job title and cost of living index, being female resulted in a 7% decrease in total yearly compensation on average compared to being male. The addition of gender in model 2b added .2% of explanatory power overall. An F test between models 2a and 2b confirmed that this was a significant increase in explanatory power.

In the final step of the hierarchical regression, after controlling for years of experience, years at the company, education, job title, cost of living index and gender, the only group that differed significantly from White posters at the p < .001 threshold in total annual compensation were Black posters who were compensated on average 6% less annually. Difference in total annual compensation between White and Asian posters was significant at the p < .01 threshold, with Asian posters making on average 2% more annually than White posters. The addition of race added only .1% more explanatory power to the overall model. An F test between models 2b and 2c confirmed that this was a significant increase in explanatory power.

Discussion
The direction of all coefficients in the final model agree with PayScale’s 2021 analysis. By and large, the magnitude of the coefficients for race variables agreed with PaysScale’s analysis as well. One poignant difference between my analysis and PayScale’s is the magnitude of the coefficient for Gender [Female]. In the controlled model (Model 2c), the coefficient for Gender [Female] of -.07 is significantly greater than what would have been expected based on the difference in pay of 2% that PayScale found between men and women across industries. This suggests that there may be a larger degree of discrimination in pay based on gender in the tech industry compared to other industries. Perhaps some of this effect can be explained by debunked yet pervasive stereotypes that women naturally have less ability in quantitative disciplines. This is a fascinating area for further research.

There was a large drop in coefficient magnitude for the dummy-coded race and gender variables after controlling for years of experience, years at the company, education, job title and cost of living. This drop was especially large in the coefficient for Race [Black], going from -.17 to -.06 – a difference of 11% explanatory power. This suggests that there is important information contained in the control variables that should be explored further. Systemic differences between racial groups and genders in educational attainment, job title, years of experience and tenure at a company would all affect total annual compensation. If these mediating factors are not addressed along with outright discrimination, financial parity for demographic groups that have historically been excluded from the tech industry will be severely slowed.

Ultimately, there remains a significant amount of variance in total annual compensation that cannot be explained by any of the control variables, particularly for Black tech workers and for women. As the population of these groups rises in the industry, it is increasingly important to continue to analyze the biased systems and attitudes that contribute to this phenomenon.

