# Trespass Towing Analysis

Trespass towing is the act of hauling a vehicle from one location to another without the consent of the vehicle’s owner. In Montgomery County, Maryland more than 100,000 vehicles have been towed in this manner since July 2021. 

By law, each invoice received for a trespass tow must include information prompting the vehicle owner to contact the Montgomery County Office of Consumer Protection with any complaints. In addition to investigating these complaints and ensuring merchants comply with regulations, the Office of Consumer Protection aims to reduce the number of trespass tows. The county enlisted Montgomery College to explore the data surrounding these cases, as well as some of the complaints filed against them. The goal of this partnership was to assess the trends in County tow data by analyzing County towing locations, towing agencies, and the towing populations while applying a racial equity and social justice lens.

### [Final Report](Towing_Analysis_Final_Report.pdf)

## Presentation Slides
On December 17, 2024 a presentation was given at the Montgomery County Stella Werner Council Office Building summarizing this project and laying a path forward for this data.
   - [Website](https://a1-3x.github.io/tow_analysis/)
   - [PDF](Tow_Slides_Final.pdf)

## Dashboard

An interactive [dashboard](https://mcgov-gis.maps.arcgis.com/apps/dashboards/075030832da640858aea4636bf980965) was created to explore the data.

![image](https://github.com/user-attachments/assets/9863684d-28f7-4bff-8688-660e731881ae)


## Datasets
   - [Trespass Towing Report](https://data.montgomerycountymd.gov/Consumer-Housing/Trespass-Towing-Report/i6vn-3s6e/about_data)

     The core of the data used to analyze trespass towing comes from a database maintained by the Montgomery County Police Department. An updated dataset is published to the dataMontgomery website monthly. Its current version includes over 100,000 entries detailing the the date each vehicle was towed, its location (address and coordinates), the reason it was towed, and information on the vehicle's make, model, and year of manufacture. A wrangled version of this dataset that includes additional Census tract data is included zipped and titled [tows.csv](tows.zip).
     
   - Trespass Towing Complaints

     The Office of Consumer Protection also provided data on trespass towing complaints filed in the 2024 fiscal year. This data includes the location of the tow, the merchant in question, the practice being disputed, and the result of the case. Details regarding these complaints can be found in the dashboard created for this project. The dataset itself is not provided to preserve the privacy of the consumers.

   - [EPA Smart Location Database](https://www.epa.gov/smartgrowth/smart-location-mapping)

     "The Environmental Protection Agency’s (EPA) Smart Location Database (SLD) was developed to address the growing demand for data products and tools that consistently compare the location efficiency of various places. The SLD summarizes several demographic, employment, and built environment variables for every Census block group (CBG) in the United States."

   - [Community Equity Index](https://montgomeryplanning.org/planning/equity-agenda-for-planning/community-equity-index-analysis/)

     The Community Equity Index (CEI) is "a composite measure of five indicators of how the county’s socioeconomic diversity is distributed, or which neighborhoods have concentrated advantage or disadvantage and which neighborhoods are representative of the county’s diversity." It is a product of Montgomery Planning's Research and Strategic Projects Division. CEI is based on five statistics:
      -   Percent of people living below 200% of the federal poverty level
      -   Percent of people with less than a bachelor’s degree
      -   Percent of people who speak English “less than very well”
      -   Percent of people who rent housing
      -   Per capita income
  
## Notebooks
   - [Data Wrangling](notebooks/tresspass_towing_wrangle.ipynb)
        The Trespass Towing dataset required a great deal of data wrangling. Much of the data had to be parsed from the notes column.
   - [Exploratory Data Analysis](notebooks/tresspass_towing_EDA.ipynb)
   - [Census Data Queries](notebooks/analyzing_census_data.ipynb)
   - [Rate of Change](notebooks/Towing_Rate_of_Change.ipynb)
   - [Correlations](notebooks/Towing_Correlations.ipynb)
        Explores correlations between numerical variables.
     
### [Google Colab Python](googlecolab.md)
 

## Web Apps

Four tools in the form of web apps were developed over the course of this project. The aim of creating these prototypes was to demonstrate that there exists a variety of ways that data-driven solutions can be utilized to mitigate the issues uncovered in this research.

1. [Ranking Towing Company](https://towrank.netlify.app)

   The Tow Ranking web app demonstrates the capability of this or similar data to rank merchants on their level of deviation from the mean. Applications based on different measures can be developed as their importance is uncovered. More information and calculations can be found [here](ranking-app.md).

   ![image](https://github.com/user-attachments/assets/d58ace4d-0473-408a-8ba0-d4f3b8c3250f)
   ![image](qrs/montgomery_county_towing_rankings_qr.png)


3. [Towr](https://towr.netlify.app)

   The Towr app is aimed at consumers. Its purpose is to prevent trespass tows from occuring by educating vehicle owners on where vehicles have been towed from in the past. Consumers looking to park their vehicle may look up an address, or share their location with the app, and will be met with a map indicating locations nearby that have seen trespass tows in the past 3 years.

   ![image](https://github.com/user-attachments/assets/9da2a43b-0322-4fe3-af01-1fcc8c6c3a15)
   ![image](qrs/tow_heatmap_qr.png)



4. [Towing Station Distance](https://towdist.vercel.app)

   The Tow Station Distance tool is aimed at county employees. Once a location is selected on the map, it calculates the Haversine distance between it and all active registered storage lots. The map indicates in red which lots violate Montgomery County Code, Chapter 30C, which states: "A storage site must not be more than 15 miles from the origin of the tow." The app provides a list of all the sites, sorted by ascending distance, with an option to filter for only those merchants violating the rule.

   ![image](https://github.com/user-attachments/assets/901dceb7-1c91-4f1e-bb9a-ecec0358efd2)
   ![image](qrs/montgomery_county_towing_distance_calculator_qr.png)




7. [Pre Screening Complaint Form](https://towwatch.vercel.app )

   The TowWatch Pre-Screening Complaint form is aimed at vehicle owners who have experienced trespass towing. This prototype prompts the user for the company that towed their vehicle using a drop down menu. If the merchant does not appear on this menu, then it is most likely not registered to operate in Montgomery County and the user is encouraged to file a complaint with the Office of Consumer Protection. If the merchant is on the list, then the user is prompted to provide the address from which their vehicle was towed. If the 15 mile rule is violated, the user is encouraged to file a complaint as well. Future versions may include additional questions to better guide the consumer.

   ![image](https://github.com/user-attachments/assets/a3f72ce9-59c4-450f-8086-25955fdc45a2)
   ![image](qrs/prescreening_complaint_qr.png)





