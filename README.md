# DealerTireExercise

The  DealerTire Notebook contains code which automates the recall data pull from https://www-odi.nhtsa.dot.gov/downloads/flatfiles.cfm and produces descriptive analysis and charts for the data.

Descriptive statistics and data exploration created with pandas-profiling can be found via this link: https://bpritchie.github.io/DealerTireExercise/data_profile.html


Executive Summary:

- Focusing on the list of relevant vehicle manufactures given for the excercise, BMW was found to have the most number of Recall Campaigns (414) but Honda had the highest number of potential units impacted overall.
- Looking exclusively at Campaigns with RecallTypeCode T (as in Tires as it relates to Dealer Tire), Mazda is the only vehicle make of this type with an estimated potential impact of 158,400,000 units.
- Mercedes seems to stand out among Vehicle Makes as it appears to have only one campaign recall in the entire dataset. 
- Top recall manufacture component names were (if data was available): Unit Assy Infotainment Control, Meter Assy Combination, Seat belt cable fastening, Fuel Pump Module, Wire Engine Room, Driver Air Bag, Computer Power Management Control, Rear Seat Belt and Pump with Filter. 
-Brief look at the relationship between time of recall and model year of vehicle indicated that recalls were more likely to happen in the first six months of a new calendar year. This could make sense such that a vehicle has been released in mass and enough time has gone by to acquire results to validate a recall.

Information needed for further analysis:
- Ideally, I would have liked to bring in additional data to be able to compare the number of recall campaigns per Vehicle Make. Additional data would include:
  - Production Metrics: Total number of units produced per year of each make and model type. This would have allowed me to convert number of campaigns and number of potentially impacted parts into percentages of production output and compare more easily among Manufactures. It would be unethical to compare totals without relating them to the production and marketshare metrics of the manufactures. For example, it would be unfair to compare the total number of Toyota recall campaigns to that of Porsche since Porsche produces significantly less number of vehicles per year than Toyota. 
  - Sales/inventory information: Units sold respective of make, model, year and time sold. It would be interesting to research inventory levels in relation to when new models are coming on the road and if there was a threshold to number of vehiles on the road before a recall was performed. It would also be interesting to research the impact a recall has on inventory in respect to new car year models being released. Could easily make a linear regression predictive model if we had this information to determine when a recall is most liekly to happen.
  - Recall Costs: Estimated total costs of recalls, both realized and unrealized. With this information we could have determined if there was a certain timeframe in which a recall could cost less in relation to the difference of the number of years between a vehicle Make/Model and when the recall was in effect. 
  - Data Clearification: In this dataset, need clearification on number of units definition. It appears that the number of units might not be equal to vehicles. For example, if the cause of the recall is a tire, is it counting 4 tires for the total number of units impacted for a single vehicle?
  - Missing Data Cleaification: Why does so much data appears to be missing and incomplete? Would like to do NLP (Natural Language Processing) on text to derive key words and overall themes of long form text variables. 

Data Exploration
Please use the link above to view the profile report of the data:
- After filtering and deduping row entries, there are 28 vairables with 21,458 rows of data
- 13 variables have High Cardinality
- Notable Highly Correlated Variables:
  - Report Recieved Date is highly correlated with Owner Notified Date and Record Creation Date
    *This is great, seeing that owners are notified very quickly from when reprots are recieved
  - Manufacture Component Name is highly correlated with Vehicle Make, Recal Type Code, Manufacture of Recalled Products and Manufacture Comp Descriptions
    *This makes sense as all of these things could be dependent upon one another
- There are quite a number of variables with a large amount of missing data: 
    *mfr_comp_name has 19570 (91.2%) missing values
    *mfr_comp_desc has 19581 (91.3%) missing values
    *mfr_comp_ptno has 19730 (91.9%) missing values
    *FMVSafetyStandardNumber has 16482 (76.8%) missing values
    *RegulationPartNumber has 19089 (89.0%) missing values
    *MfgCampaignNumber has 10996 (51.2%) missing values

 
 
