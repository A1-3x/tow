# **Company Scoring Overview**

This analysis evaluates companies based on four key categories:

---

## **1. Distance Score**
### **Definition**
- Measures the average towing distance compared to the overall average.

### **Formula**
$$
\text{Adjusted Distance Score} =
\begin{cases} 
1 - \frac{\text{Company Avg. Distance}}{\text{Overall Avg. Distance}}, & \text{if Company Avg. Distance} \leq \text{Overall Avg. Distance} \\
- \left( \frac{\text{Company Avg. Distance}}{\text{Overall Avg. Distance}} - 1 \right), & \text{if Company Avg. Distance} > \text{Overall Avg. Distance}
\end{cases}
$$

### **Normalization**
- Scores are normalized to a 0–1 range using:
$$
\text{Normalized Score} = \frac{\text{Score} - \text{Min}}{\text{Max} - \text{Min}}
$$

---

## **2. CEI (Community Equity Index) Score**
### **Definition**
- Measures how equitable the company’s operating areas are, relative to proportionality (closer to 0 is better).

### **Formula**
$$
\text{CEI Score} = -|\text{Company CEI Value} - 0|
$$

### **Normalization**
- Similar to Distance, normalized to a 0–1 range:
$$
\text{Normalized Score} = \frac{\text{Score} - \text{Min}}{\text{Max} - \text{Min}}
$$

---

## **3. MHI (Median Household Income) Score**

### **Definition**
The MHI score is calculated based on the median household income in Montgomery County, Maryland ($125,371 in 2023) and the service area coverage. This score reflects how well a towing company serves communities across different income levels. A higher score indicates better service coverage across diverse economic areas.

### **Formula**
$$
\text{MHI Score} = -|\text{Company Avg. MHI} - \text{Target MHI}|
$$

### **Normalization**
$$
\text{Normalized Score} = \frac{\text{Score} - \text{Min}}{\text{Max} - \text{Min}}
$$

---

## **4. Speak Only English Score**
### **Definition**
- Measures alignment of the company’s operating areas with the average number of people who speak only English.

### **Target Value**
- Mean Speak Only English: **$2298.86$**

### **Formula**
$$
\text{English Score} = -|\text{Company Avg. Speak Only English} - \text{Mean Speak Only English}|
$$

### **Normalization**
$$
\text{Normalized Score} = \frac{\text{Score} - \text{Min}}{\text{Max} - \text{Min}}
$$

---

## **5. Composite Score**
### **Definition**
- Combines all normalized scores into a single weighted score.

### **Weights**
- **Normalized MHI Score**: 40%
- **Normalized Distance Score**: 30%
- **Normalized CEI Score**: 20%
- **Normalized English Score**: 10%

### **Formula**
$$
\text{Composite Score} = 
w_1 \cdot \text{Normalized MHI Score} +
w_2 \cdot \text{Normalized Distance Score} +
w_3 \cdot \text{Normalized CEI Score} +
w_4 \cdot \text{Normalized English Score}
$$

---

## **6. Final Ranking**
### **Process**
- Companies are ranked based on their **Composite Score** (higher is better).
- Rankings and individual scores are saved in a CSV file for further analysis:
  - `final_company_rankings_with_english.csv`

---

This scoring methodology ensures fairness by normalizing all metrics and weighting them based on their importance. Adjustments to weights or metrics can be made depending on the analysis goals.
