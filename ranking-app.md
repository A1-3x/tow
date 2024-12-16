
#### How Individual Scores Were Calculated
# **Score Calculations for Ranking**

This document provides the calculations for each score, scaled to a 0-100 range.

---

## **1. Distance Score**
The **Distance Score** rewards companies closer to the smallest distance. Smaller distances get higher scores.

\[
\text{distanceScore} = \left(1 - \frac{\text{distance1.4} - \text{minDistance}}{\text{maxDistance} - \text{minDistance}}\right) \times 100
\]

---

## **2. CEI Score**
The **CEI Score** rewards companies whose CEI is closer to 0. Higher scores are given for smaller deviations.

\[
\text{ceiScore} = \left(1 - \frac{|\text{CEI}|}{\text{maxDeviation}}\right) \times 100
\]

---

## **3. English Score**
The **English Score** rewards companies whose **Speak Only English Ratio** is closer to the target value \(0.566\). 

### Steps:
1. Calculate the absolute deviation from the target:
   \[
   \text{English Ratio Deviation} = |\text{Speak Only English Ratio} - 0.566|
   \]

2. Normalize the deviation:
   \[
   \text{Normalized English Score} = 1 - \frac{\text{English Ratio Deviation}}{\text{maxDeviation}}
   \]

3. Scale to a 0-100 range:
   \[
   \text{englishScore} = \text{Normalized English Score} \times 100
   \]

---

## **4. Income Score**
The **Income Score** rewards companies whose **Median Household Income** is closer to the target value \(125371\).

### Steps:
1. Calculate the absolute deviation from the target:
   \[
   \text{Income Deviation} = |\text{Median Household Income} - 125371|
   \]

2. Normalize the deviation:
   \[
   \text{Normalized Income Score} = 1 - \frac{\text{Income Deviation}}{\text{maxDeviation}}
   \]

3. Scale to a 0-100 range:
   \[
   \text{mhiScore} = \text{Normalized Income Score} \times 100
   \]

---

## **5. Overall Score**
To combine all scores into a single overall score, assign weights to each category.

\[
\text{Overall Score} = w_1 \cdot \text{distanceScore} + w_2 \cdot \text{ceiScore} + w_3 \cdot \text{englishScore} + w_4 \cdot \text{mhiScore}
\]

Where:
- \(w_1, w_2, w_3, w_4\) are the weights assigned to each category.
- \(w_1 + w_2 + w_3 + w_4 = 1\).

---

## **6. Ranking**
The companies are ranked based on their **Overall Score**, with the highest score receiving the best rank.

---

### Normalizaion Calcluation 

$$\text{Normalized Distance Score} = \frac{\text{Average Distance} - \text{Min Distance}}{\text{Max Distance} - \text{Min Distance}}$$

### Explanation of Each Part
- **Distance from Reference**: The distance of the towing company from the central or reference location.
- **Min Distance**: The smallest distance in the dataset, ensuring normalization starts at 0.
- **Max Distance**: The largest distance in the dataset, ensuring normalization ends at 1.
- **Normalized Distance Score**: The scaled value between 0 and 1, where 0 represents the minimum distance, and 1 represents the maximum distance.

----


### CEI
"The Community Equity Index (CEI) is a composite measure of equity-related indicators that helps users understand socio-economic conditions that drive advantage and disadvantage across the county. It measures the extent to which individual neighborhoods are representative of the socio-economic diversity of the county." - [Montgomery Planning](https://montgomeryplanning.org/planning/equity-agenda-for-planning/community-equity-index-analysis/)

The 5 variables for the CEI:
1. Percent of people living below 200% of the federal poverty level
2. Percent of people with less than a bachelor’s degree
3. Percent of people who speak English “less than very well”
4. Percent of people who rent housing
5. Per capita income

## Step 1: Determine Percent Divergence from Countywide Average for Each Indicator

For each of the five indicators, the value is obtained for each tract and for the county. Values are converted to percentages (i.e., concentrations or shares) by dividing them by the total population of the tract (and county). The percentage of each tract is subtracted from the percentage of the county and multiplied by ten to yield a number with a single-digit absolute value. The score for each tract is calculated by the following formula:

$$
s_{t_i} = \left( \frac{v_{t_i}}{p_{t_i}} - \frac{v_{c_i}}{p_{c_i}} \right) \times 10
$$

Where:

- $s_{t_i}$: Indicator score for tract  
- $v_{t_i}$: ACS estimated value for indicator in tract  
- $p_{t_i}$: ACS estimated value for total tract population (universe for ACS variable)  
- $v_{c_i}$: ACS estimated value for indicator in county  
- $p_{c_i}$: ACS estimated value for total county population (universe for ACS variable)

The **Per Capita Income (pci)** indicator score is computed differently because it is not derived from a percentage. Rather, it indicates how far a tract’s pci is above or below the countywide pci.

## Step 1: Determine Per Capita Income Indicator Score

$$
s_{pci} = 100 - \left( \frac{pci_t}{pci_c} \right) \times 10
$$

Where:

- $s_{pci}$: Per capita income indicator score  
- $pci_t$: Tract per capita income  
- $pci_c$: County per capita income  

---

## Step 2: Average the Five Indicator Scores for Each Tract

For each tract, compute the average of the five indicator scores.

$$
s_{t_{cei}} = \frac{s_{t_1} + s_{t_2} + s_{t_3} + s_{t_4} + s_{t_5}}{5}
$$

Where:

- $s_{t_{cei}}$: Tract CEI score  
- $s_{t_1,2,3,\dots}$: Individual indicator scores for tracts  
****
### Table 4: Weights of CEI Indicators

| Indicator                                       | Coefficient | Weight |
|------------------------------------------------|-------------|--------|
| Per capita income                              | 0.98        | 5.24   |
| Renter occupied units                          | 0.54        | 2.89   |
| People without a bachelor's degree             | 0.40        | 2.12   |
| People living below 200% of the poverty level  | 0.25        | 1.32   |
| People who speak English less than very well   | 0.19        | 1.00   |




### Conclusion
The overall score for Henry's Wrecker is **80.9%**, calculated as the weighted sum of the individual scores, each contributing equally with a weight of 25%.

