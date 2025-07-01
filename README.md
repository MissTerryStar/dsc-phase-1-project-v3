Aviation Accident Analysis
A comprehensive analysis of aviation accident data to identify key factors contributing to accident severity and inform preventative measures.

Overview
This project delves into a comprehensive aviation accident dataset to uncover patterns, trends, and the primary factors that contribute to the severity of aviation incidents. By analyzing variables such as weather conditions, aircraft characteristics, purpose of flight, and location, the project aims to generate actionable insights that can enhance aviation safety, inform regulatory policies, and aid in the prevention of future accidents by focusing on identified key risk areas.

Data Understanding
The analysis is based on the 

AviationData.csv dataset, which contains 88,889 records of aviation incidents and accidents, with 31 initial columns. A preliminary review revealed that many columns contained significant numbers of missing values. For instance, the 



Schedule column was missing over 85% of its data. The dataset encompasses information from as early as 1948 up to 2022.



Data Preparation and Cleaning
To prepare the data for analysis, a series of cleaning and preprocessing steps were performed:


Column Standardization: Column names were standardized by removing periods and converting them to lowercase for easier access.


Handling Missing Values:

Columns with excessive missing values (over 50%), such as 

schedule and air_carrier, were dropped.


Columns not essential for this analysis, including 

latitude, longitude, airport_code, airport_name, and far_description, were also removed.


Categorical columns with missing data were filled with the value "Unknown".

Numerical columns for injuries (

total_fatal_injuries, total_serious_injuries, etc.) were filled with 0, assuming no entry meant no injuries of that type. The 

number_of_engines column's missing values were filled with its mode (1.0).

Feature Engineering and Cleaning:

The injury_severity column, which had 110 unique entries, was cleaned by grouping detailed reports (e.g., "Fatal(2)", "Fatal(4)") into a single "Fatal" category to simplify analysis.


The location column was split into separate city and state columns for more granular geographical analysis.

The event_date was converted to a datetime object, and the year was extracted into a new event_year column.


Duplicates and Outliers: The dataset was confirmed to have no duplicate rows. Outliers in the injury columns were retained, as they represent real-world events, particularly in crashes involving large aircraft.


Exploratory Data Analysis (EDA) - Key Findings
General Trends

Investigation Type: The vast majority of events (97.1%) are classified as "Accidents," with only 2.9% being "Incidents," indicating that most recorded events involved significant damage or injury.
![image](https://github.com/user-attachments/assets/0e458407-1b6c-4adf-9b4a-2530cc5198fd)

Injury Severity: A large majority of accidents are categorized as "Non-Fatal" (67,357 cases). When analyzing fatality counts, 76% of all accidents resulted in zero fatalities.
![image](https://github.com/user-attachments/assets/2f85ea4f-c137-41c6-8d2a-a7a43cd4629b)



Accidents Over Time: After a sharp spike in reported accidents around 1982, there has been a steady decline in incidents from 2000 to 2023, suggesting continuous improvements in aviation safety.
![image](https://github.com/user-attachments/assets/13976a42-d7dd-43a2-b83f-97dc881e1ffb)


Factors Influencing Accidents
Purpose of Flight: "Personal" flights are the leading cause of aviation accidents, accounting for 48,582 cases. This is significantly higher than the next category, "Instructional" flights, at 10,438. Personal flights also recorded the highest number of both fatal and non-fatal outcomes.






Weather Conditions: Surprisingly, most accidents (75,510 cases) occurred during Visual Meteorological Conditions (VMC), which represents clear weather suitable for flying. This suggests that adverse weather is not the primary cause of most accidents; instead, factors like human error or mechanical failure in high-volume flight conditions may be more significant.





Aircraft Characteristics:


Make: Cessna (25,905) and Piper (14,216) are the two aircraft makes most frequently involved in accidents.
![image](https://github.com/user-attachments/assets/c9b91484-19b3-430d-a23b-d1c6d1baf77e)


Engine Type: Aircraft with reciprocating engines were involved in the highest number of both fatal and non-fatal accidents.
![image](https://github.com/user-attachments/assets/b99a92e7-416b-4cf5-b7b5-e7949c4c85e9)


Bivariate and Multivariate Insights

Severity vs. Weather: Despite being the safest condition for flying, VMC sees the highest number of both fatal and non-fatal accidents. This trend holds true even when analyzing fatal injuries year by year from 2000-2023, where VMC consistently accounts for more fatalities than Instrument Meteorological Conditions (IMC).
![image](https://github.com/user-attachments/assets/8b97720e-4001-487e-ab04-829a11dcfd38)


Serious vs. Fatal Injuries: A scatter plot analysis showed no clear linear relationship or strong correlation between the number of serious injuries and the number of fatal injuries in an accident.

![image](https://github.com/user-attachments/assets/9a4f7631-e588-46f9-a4f8-4cfc23371bb5)

Tableau Dashboard
Here is the link to the tableau dashboard;https://public.tableau.com/views/AviationDataDashboard_17513497831340/AviationDataAnalysisDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link 


Key Conclusions & Recommendations
Focus on General Aviation: The highest frequency of accidents occurs during "Personal" flights. This highlights a significant risk in private/recreational flying. Safety campaigns, enhanced training, and awareness programs should be targeted at general aviation pilots.


Investigate Human Factors in Clear Weather: Since most accidents happen in clear weather (VMC), the focus for prevention should shift from weather-related challenges to human factors, pilot decision-making, and potential mechanical failures that occur during routine flights.


Enhance Instructional Flight Safety: "Instructional" flights are the second-highest category for accidents. While these are training environments where incidents might be expected, the high number of non-fatal accidents suggests a need to review and reinforce safety protocols and training syllabuses.


Acknowledge Safety Improvements: The overall number of fatal injuries has steadily declined over the past two decades. This positive trend indicates that existing safety regulations, technological advancements, and training improvements have been effective.

Technologies Used
pandas: For data manipulation and cleaning.

numpy: For numerical operations.

matplotlib & seaborn: For data visualization.

How to Use This Repository
Clone the repository:

Bash

git clone https://github.com/your-username/aviation-accident-analysis.git
Navigate to the project directory:

Bash

cd aviation-accident-analysis
Install the required libraries:

Bash

pip install pandas numpy matplotlib seaborn
Launch Jupyter Notebook and open the student.ipynb file to view the analysis. The cleaned dataset is available as 

cleaned_dataset.csv.

Author

Teresia Ndung'u
