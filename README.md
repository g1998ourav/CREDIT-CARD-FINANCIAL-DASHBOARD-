" THIS DASHBOARD WAS DEVELOPED USING POWER BI DESKTOP 2024 "

PROJECT OBJECTIVE:-

Design and implement a cutting-edge, data-driven dashboard that delivers real-time insights into key performance metrics, trends, and predictive analytics, empowering stakeholders to:

⦿ Monitor credit card operations with precision and speed

⦿ Analyze performance metrics and trends to inform strategic decisions

⦿ Identify areas for optimization and process improvement

⦿ Detect and prevent fraudulent transactions

⦿ Enhance customer experience and loyalty

⦿ Stay ahead of industry competitors

PROJECT INSIGHTS- WEEK 53 (31st Dec)

WoW CHANGE:-

⦿ Revenue increased by 28.8%,

⦿ Total Transaction Amt & Count increased by xx% & xx%

⦿ Customer count increased by xx%

OVERVIEW YTD:-

⦿ Overall revenue is 57M

⦿ Total interest is 8M

⦿ Total transaction amount is 46M

⦿ Male customers are contributing more in revenue 31M, females 26M

⦿ Blue & Silver credit cards are contributing to 93% of overall
transactions

⦿ TX, NY & CA is contributing to 68%

⦿ Overall Activation rate is 57.5%

⦿ Overall Delinquent rate is 6.06%

USED THESE QUERIES FOR WEEK-ON-WEEK COMPRESSION:-  

Current_week_Revenue = CALCULATE(
    SUM('credit_card'[Revenue]),
    FILTER(
        ALL('credit_card'),
        'credit_card'[week_num2] = MAX('credit_card'[week_num2])
    )
)


Previous_week_Revenue = CALCULATE(
    SUM('credit_card'[Revenue]),
    FILTER(
        ALL('credit_card'),
        'credit_card'[week_num2] = MAX('credit_card'[week_num2])-1
    )
)


WoW_revenue = DIVIDE(([Current_week_Revenue] - [Previous_week_Revenue]),[Previous_week_Revenue])


USED THESE QUERIES TO MAKE NEW COLUMNS & PERIMETER:- 

Revenue = 'credit_card'[Annual_Fees] + 'credit_card'[Total_Trans_Amt] + 'credit_card'[Interest_Earned]


week_num2 = WEEKNUM('credit_card'[Week_Start_Date])


AgeGroup = SWITCH(
    TRUE(),
    'customer'[Customer_Age] < 30,"20-30",
    'customer'[Customer_Age] >= 30 && 'customer'[Customer_Age]<40,"30-40",
    'customer'[Customer_Age] >= 40 && 'customer'[Customer_Age]<50,"40-50",
    'customer'[Customer_Age] >= 50 && 'customer'[Customer_Age]<60,"50-60",
    'customer'[Customer_Age] >=60,"60+",
    "unknow"
    )



IncomeGroup = SWITCH(
    TRUE(),
    'customer'[Income] < 35000,"Low",
    'customer'[Income] >= 35000 && 'customer'[Income] <70000,"Med",
    'customer'[Income] >= 70000,"High",
    "unknon"
    )


PROJECT LEARNING:- 

    
⦿ Data Integration: Successfully imported data from CSV files to an SQL database, creating a solid foundation for analysis.

⦿ Data Modeling: Designed and implemented effective data models using DAX queries to categorize customer age and income groups.

⦿ Revenue Calculation: Developed a robust calculation for revenue, considering annual fees, transaction amounts, and interest earned.

⦿ Week-over-Week (WoW) Analysis: Implemented WoW comparisons to track changes in revenue, transaction amounts, and customer count.

⦿ Year-to-Date (YTD) Overview: Created a comprehensive YTD summary, highlighting key performance metrics and trends.

⦿ Interactive Dashboarding: Built an interactive credit card financial dashboard using Power BI, providing real-time insights and streamlining data analysis.

⦿ Stakeholder Engagement: Effectively shared actionable insights with stakeholders, supporting informed decision-making processes.

⦿ Data Visualization: Learned to present complex data clearly and concisely, using visualizations to facilitate better understanding.

⦿ Data Analysis: Developed skills in analyzing large datasets to extract valuable insights and trends.

⦿ Project Management: Managed the project from data import to dashboard creation, ensuring timely completion and meeting project objectives.


This project has enhanced my data analysis, visualization, and storytelling skills, allowing me to drive business growth and improve decision-making processes.




THE CREDIT CARD TRANSACTION REPORT AND CREDIT CARD CUSTOMER REPORT ARE DISPLAYED IN THESE SCREENSHOTS.


   ![Screenshot 2024-07-17 105544](https://github.com/user-attachments/assets/4edd17a6-8d01-436e-b949-009db3464dd8)
   

![Screenshot 2024-07-17 105656](https://github.com/user-attachments/assets/2001edaa-3b54-413d-82ec-b63e1706ade5)

    










