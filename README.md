# Trespass Towing Analysis

Trespass towing is the act of hauling a vehicle from one location to another without the consent of the vehicle’s owner. In Montgomery County, Maryland, more than 100,000 vehicles have been towed in this manner since July 2021. 


## [Final Report](Towing_Analysis_Final_Report.pdf)
## Slides
   - [Website](https://a1-3x.github.io/tow_analysis/)
   - [PDF](Tow_Slides_Final.pdf)
## [Datasets](datasetinfo.md)
   - [Trespass Towing Report](https://data.montgomerycountymd.gov/Consumer-Housing/Trespass-Towing-Report/i6vn-3s6e/about_data)

     The core of the data used to analyze trespass towing comes from a database maintained by the Montgomery County Police Department. An updated dataset is published to the dataMontgomery website monthly. Its current version includes over 100,000 entries detailing the the date each vehicle was towed, its location (address and coordinates), the reason it was towed, and information on the vehicle's make, model, and year of manufacture.
     
   - Trespass Towing Complaints

     The Office of Consumer Protections also provided data on trespass towing complaints filed in the 2024 fiscal year. This data includes the location of the tow, the merchant in question, the practice being disputed, and the result of the case. Details regarding these complaints can be found in the dashboard created for this project. The dataset itself is not provided to preserve the privacy of the consumers.

   - Community Equity Index
## Notebooks
   - [Data Wrangling]
   - [Exploratory Data Analysis]
### [Google Colab Python](googlecolab.md)

Four tools in the form of web apps were developed over the course of this project. The aim of creating these prototypes was to demonstrate that there exists a variety of ways that data-driven solutions can be utilized to mitigate the issues uncovered in this research. 

## [Web Apps](Webapp.md)
1. [Ranking Towing Company](https://towrank.netlify.app)

   The Tow Ranking web app demonstrates the capability of this or similar data to rank merchants on their level of deviation from the mean. Applications based on different measures can be developed as their importance is uncovered. More information and calculations can be found [here](ranking-app.md).

2. [Towr](https://towr.netlify.app)

   The Towr app is aimed at consumers. Its purpose is to prevent trespass tows from occuring by educating vehicle owners on where vehicles have been towed from in the past. Consumers looking to park their vehicle may look up an address, or share their location with the app, and will be met with a map indicating locations nearby that have seen trespass tows in the past 3 years.

   ![image](https://github.com/user-attachments/assets/9da2a43b-0322-4fe3-af01-1fcc8c6c3a15)



3. [Towing Station Distance](https://towdist.vercel.app)

   ![image](https://github.com/user-attachments/assets/901dceb7-1c91-4f1e-bb9a-ecec0358efd2)




4. [Pre Screening Complain Form](https://towwatch.vercel.app )

   



