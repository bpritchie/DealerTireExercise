# DealerTireExercise

The  DealerTire Notebook contains code to automate the recall data pull from https://www-odi.nhtsa.dot.gov/downloads/flatfiles.cfm and produce descriptive analysis and charts for the data.

Descriptive statistics and data exploration created with pandas-profiling can be found via this link: https://bpritchie.github.io/DealerTireExercise/data_profile.html


Executive Summary:

- Focusing on the list of relevant vehicle manufactures given for the excercise, BMW was found to have the most number of Recall Campaigns (414) but Honda had the highest number of potential units impacted overall.
- Looking exclusively at Campaigns with RecallTypeCode T (as in Tires as it relates to Dealer Tire), Mazda is the only vehicle make of this type with an estimated potential impact of 158,400,000 units.
- Mercedes seems to stand out among Vehicle Makes as it appears to have only one campaign recall in the entire dataset. 
- Top recall manufacture component names were (if data was available): Unit Assy Infotainment Control, Meter Assy Combination, Seat belt cable fastening, Fuel Pump Module, Wire Engine Room, Driver Air Bag, Computer Power Management Control, Rear Seat Belt and Pump with Filter. 

Information needed for further analysis:
- Ideally, I would have liked to bring in additional data to be able to compare the number of recall campaigns per Vehicle Make. Additional data would include:
  - Production Metrics: Total number of units produced per year of each make and model type. This would have allowed me to convert number of campaigns and number of potentially impacted parts into percentages of production output and compare more easily among Manufactures. It would be unethical to compare totals without relating them to the production and marketshare metrics of the manufactures. For example, it would be unfair to compare the total number of Toyota recall campaigns to that of Porsche since Porsche produces significantly less number of vehicles per year than Toyota. 
  - Recall Costs: Estimated total costs of recalls, both realized and unrealized. With this information we could have determined if there was a certain timeframe in which a recall could cost less in relation to the difference of the number of years between a vehicle Make/Model and when the recall was in effect. 
  - Data Clearification: In this dataset, need clearification on number of units definition. It appears that the number of units might not be equal to vehicles. For example, if the cause of the recall is a tire, is it counting 4 tires for the total number of units impacted for a single vehicle?
  
