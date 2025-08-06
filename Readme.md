## Finance Analytics Tableau Project

## Objective:
The goal of this Tableau project is to analyze financial performance across different countries, products, and time periods, using key financial metrics such as sales, profit, cost of goods sold (COGS), and discounts.

## Columns Provided:
- Segment
- Country
- Product
- Discount Band
- Units Sold
- Manufacturing Price
- Sale Price
- Gross Sales
- Discounts
- Sales
- COGS(Cost of Goods Sold)
- Profit
- Date
- Month Number
- Month Name
- Year

## Calculated Fields:
- Current year
  > [Select Year]
- Previous Year
  > [Select Year] -1
- % diff Profits
  > (SUM([CY Profits])-SUM([PY Profits]))/SUM([PY Profits])
- % diff Sales
  > (SUM([CY Sales])-SUM([PY Sales]))/SUM([PY Sales])
- COGS to Sales ratio
  > SUM([Cogs])/SUM([Sales])
- CY Profits
  > if YEAR([Date])=[Select year] then [Profit] END
- CY Sales
  > if YEAR([Date])=[Select year] then [Sales] END
- PY Profits
  > if YEAR([Date])= [Select year]-1 then [Profit] END
- PY Sales
  > if YEAR([Date])= [Select year]-1 then [Sales] END
- Discount %
  > SUM([Discounts])/SUM([Gross Sales])
- Min/Max Profits
  > if SUM([CY Profits])=WINDOW_MAX(SUM([CY Profits])) then SUM([CY Profits])
  > ELSEIF SUM([CY Profits])=WINDOW_MIN(SUM([CY Profits])) then SUM([CY Profits]) END
- Min/Max Sales
  > if SUM([CY Sales]) = WINDOW_MAX(SUM([CY Sales])) THEN SUM([CY Sales])
  > ELSEIF SUM([CY Sales]) = WINDOW_MIN(SUM([CY Sales])) THEN SUM([CY Sales]) END
- Profit Margin %
  > SUM([Profit])/SUM([Sales])
- Profit per Unit
  > SUM([Profit])/SUM([Units Sold])
- Profitability
  > IF SUM([Discounts]) = 0 THEN 0 ELSE SUM([Profit]) / SUM([Discounts]) END

## Calculated parameters:
 - Select Year

## Business Quesrions Answered:
Q1 -  Which countries have the best Profit per Unit Sold?
Ans-  Germany has the highest profit per unit sold as well as profit margin.(Profit margin and profit per unit by Country plot)

Q2 - What are the trends in sales and profits over time?
Ans- Total Sales and Total Profit KPIs plot

Q3- Are there any segments with sales growth but no profit growth?
Ans - Yes, Enterprise segment saw a negative profit growth from July onwards. Likewise, Midmarket segment saw declining growth from June to July. (Sales & profit growth per segment plot)

Q4- What is the ROI of every unit of discount?
Ans- Germany and France had the above average ROI while Canada, Mexico and USA had below average ROI. (Return on Investment of every unit of Discount plot.)

Q5- Which products deliver highest profit contribution?
Ans - Paseo, VTT and Amarilla make up 63% of the total contribution to the profits.(Profit Contribution of each Product.)

Q6- Are there any countries with High Sales but Low Profit Margins?
Ans- Yes, Canada and USA, despite being top 2 countries in sales, have profit margin lower than the average of 14.2% (High Sales Low Profit Margin Countries plot) 

Q7- How does COGS vary over time for different products?
Ans- COGS variance per Product over time plot

Q8 - Which months have highest discount usage but lowest profit?
Ans- Feb-March saw a decline in profits despite increase in discounts. Likewise August-September period and October-November period. (High Discounts but Low Profit by Months plot)

## 📁 Files Included

| File Name                                     | Description                          |
|-----------------------------------------------|--------------------------------------|
| `Financial_Dataset_Project.twbx`              | Tableau workbook                     |
| `Financial_Data.csv`			                       | Dataset provided                     |
| `Fnancial_Data_Cleaned.csv`			                | Dataset used                         |
| `README.md`                                   | This documentation                   |
| `images/financial_analysis_dashboard_1.png`   | Screenshot of the dashboard          |
| `images/financial_analysis_dashboard_2.png`   | Screenshot of the dashboard          |

---
<img width="1182" height="799" alt="Financial Analysis Dashboard 1" src="https://github.com/user-attachments/assets/c7882ea6-d7aa-4690-9428-da437a714be0" />
<img width="1178" height="830" alt="Financial Analysis Dashboard 2" src="https://github.com/user-attachments/assets/c1cfaf17-fc14-4e6d-9b6f-e5938c0fc77b" />









