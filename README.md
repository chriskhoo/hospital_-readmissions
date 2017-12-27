# SpringBoard Exercise: Hospital readmissions (Exploratory Data Analysis)

## Context
This repository contains an exercise on Exploratory Data Analysis for the SpringBoard program. The data set comes from a US government centre tasked with reducing Medicare (a federal health insurance program) payments by studying excess readmissions in hospitals.  

In the study, excess readmissions is defined as a ratio:
- a hospital’s number of “predicted” 30-day readmissions for heart attack, heart failure, and pneumonia
- divided by the number that would be “expected,” based on an average hospital with similar patients
- ratio greater than 1 indicates excess readmissions

This exercise is a critique of the preliminary analysis using statistically sound analysis.  

The following questions and the working to obtain their answers below can be found in the jupyter notebook.

A. Do you agree with the preliminary analysis and recommendations? Why or why not?
  - A: Whilst the analysis above provides a starting point to look at the issues, further analysis is still required before any conclusions are drawn. Firstly, the analysis provides summary statistics on populations with arbitary segmentation (e.g. hospitals/facilities with number of discharges < 100) without analyzing if the differences in the population are statistically significant.

  Using the preliminary analysis then plots the number of discharges vs. excess rate of readmissions to draw a conclusion that there is a significant corrolation. Using the corrolation, the preliminary analysis uses it to conclude a causation which it then uses to propose a recommendation that is not supported by the study (e.g. no prior mention that facilities < 300 constitute a small capacity, no root cause analysis done on the concluded issues). Furthermore, the recommendation of consolidation fails to account for practical factors (e.g. if consolidation would still afford citizens basic health care within an acceptable response time) and lacks a simple financial study to verify the cost implications of such a measure.
  Whilst the study's recommendation may be most suitable, despite the analysis, the recommendations are currently not supported by the analysis. Further studies are required to reach such conclusions.

B. Provide support for your arguments and your own recommendations with a statistically sound analysis:
  1. Setup an appropriate hypothesis test.
  - A: Null hypothesis: There is no difference in the excess readmission rate for hospitals/facilities with number of discharges <= 300 (6213 observations) and those > 300(5365 observations). Note that 300 was chosen as it was used in the final recommendation as a definition of small capacity.

  Test statistic: Mean excess readmission rate (note the level of readmission rate greater than 1 is a measure of the distrubtion's skew).

  2. Compute and report the observed significance value (or p-value).
  - A: The p-value was extremely low, we must therefore reject the null hypothesis that there is no difference in the excess readmission rate for hospitals/facilities with number of discharges <= 300 and those > 300.

  3. Report statistical significance for  αα  = .01.
  - A: There is a 1% probability that a normally distributed difference of means of excess readmission ratio would exceed: 0.00404195417585

  4. Discuss statistical significance and practical significance. Do they differ here? How does this change your recommendation to the client?
  - A: The finding here is that there is a statistically significant lower Excess Readmission Ratio in hospitals/facilities with a higher number of discharges. The practical significance of this finding is obscured by the baseline used - the 'expected readmission rate'. The expected readmission rate is derived from an average hospital with similar patients. Practically speaking, the baseline should be a theoretical limit informed by a study. Alternatively they could have use real data around 'useful' readmissions (e.g. active interventions or if the course of treatment was significantly altered) to determine if the level of excess readmissions was acceptable.

  My recommendation would be to study the cause of the lower readmission before taking action. For example, the readmission in larger facilities could be lower because there are better and more experienced doctors in those facilities. The recommendation for such a finding would be to review and improve the quality of training in smaller facilities.

  5. Look at the scatterplot above.
    - What are the advantages and disadvantages of using this plot to convey information?
    - A: The scatter plot above has the advantage of providing the reader a sense of distribution (spread and density) of the data along both axes. The information provided to the reader is very rich, for example, we clearly see that for facilities under 500 discharges, the data is concentrated around 0.8 - 1.2. The lack of data with very small discharges (under 50) with excess readmission rate below 1.1 makes me suspicious of the baseline. This level of information isn't always available with simpler plots. On the flip side, the excess of information could detract from the main message the author is tryign to convey, for example, that the mean is higher for small facilities.

  - Construct another plot that conveys the same information in a more direct manner.
  - A: See notebook for plot
