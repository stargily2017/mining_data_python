# Quality Prediction In a Mining Process
<img width="868" height="470" alt="image" src="https://github.com/user-attachments/assets/a48c45bc-19b0-42a6-bcdb-4d8d11dc41d1" />


## EXECUTIVE SUMMARY:
The objective is to use this data to predict the level of impurity in the ore concentrate. Since silica (the impurity) is measured hourly, having a predictive model would allow engineers to anticipate its levels in advance. This early insight would enable them to take timely corrective actions to reduce impurity when needed, improving process efficiency and minimizing environmental impact by decreasing the amount of ore sent to tailings.

## Why I chose This project:

As a Data Analyst in a mining company, My work focuses on analyzing data from their flotation plant, which plays a key role in the mineral processing operations. The goal is to extract insights from the plant’s data to support decision-making and improve overall efficiency in the production process.

## Key Takeaways
Is it possible to predict % Silica Concentrate every minute?

How many steps (hours) ahead can we predict % Silica in Concentrate? This would help engineers to act in predictive and optimized way, mitigatin the % of iron that could have gone to tailings.

Is it possible to predict % Silica in Concentrate whitout using % Iron Concentrate column (as they are highly correlated)?

## Goal of this dataset

The target is to predict the % of Silica in the end of the process, which is the concentrate of iron ore and its impurity (which is the % of Silica).

## Methodology
Import libraries: pandas, matplotlib.pyplot, seaborn
from pathlib import path
functions: shape, iloc, describe, sns.pairplot, sns.heatmap, sns.lineplot

## Dataset Details
https://www.kaggle.com/datasets/edumagalhaes/quality-prediction-in-a-mining-process
<img width="215" height="101" alt="image" src="https://github.com/user-attachments/assets/5ef812db-ebcb-46b9-8fcc-9727a2d0519e" />
737453 rows and 24 columns

## Descriptive Analysis:
To find the maximum and minimum date available in dataset:
<img width="370" height="149" alt="image" src="https://github.com/user-attachments/assets/e1b6a3cc-d1a4-4a62-a078-c30e4718ad46" />
### Create filter for june 2017 data
<img width="623" height="103" alt="image" src="https://github.com/user-attachments/assets/3a5884dc-1ba9-4bcf-8280-67b1acc3670a" />

###"How do these variables relate to each other? Does the pH level affect the Iron Concentrate?"
sns.pairplot(df_june_important)
<img width="986" height="986" alt="image" src="https://github.com/user-attachments/assets/c4b8da74-406a-46c0-9b40-c8c77815e599" />
We can create a Correlation Matrix. This calculates a score between -1 and 1 for every relationship.

1.0: Perfect Positive Relationship.

-1.0: Perfect Negative Relationship.

0.0: No relationship.
We will use Pandas to do the math (.corr) and Seaborn to draw a colored Heatmap (.heatmap) so it is easy to read.
<img width="470" height="88" alt="image" src="https://github.com/user-attachments/assets/811c620c-76d3-4f27-9d1d-68094a8b865c" />

<img width="694" height="586" alt="image" src="https://github.com/user-attachments/assets/bcddfc73-1721-4daf-8071-a122c5807a3e" />
The Red Diagonal (1.0): This is just the variable comparing to itself (e.g., Iron vs. Iron). We ignore these.

The Weak Numbers: Look at the other boxes.

Iron vs. Silica: -0.27. This is a very weak negative correlation.

Iron vs. pH: 0.3. This is a very weak positive correlation.

Iron vs. Flotation Level: -0.045. This is basically zero.

## Result and Reflection:

Overall, I found that Ore Pulp pH 0.3, it's most influence the prediction of silica impurity concentration in the output flow.

For the next steps, we can consider:

Continue collecting data from the flotation column to create more data points on high-silica cases from which we can extract insights from.
On the day of the incident, the variables were chaotic. There is no clear pattern showing that one variable caused another to change.




