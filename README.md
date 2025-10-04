
# Pizza-Sales-Analysis


## Statement

This report presents key performance metrics across multiple business dimensions, providing stakeholders with critical insights into operational performance and strategic positioning. It consolidates various data points into an accessible single-page format for quick decision-making.

This Analysis was able to look into the several KPIs which includes

- Total Revenue
- Total Order Count
- Average Order Value
- Average Items Per Order
- Average Pizza Price

This Report was succesfully able to answer detailed business questions which includes

- Which pizzas are most preferred by customers each day of the month?
- Peak Pizza Sales Hours 
- Which pizza category drives more revenue?
- Which month showed the biggest jump in running total?

# Data Modelling : Table Relationships

- Established a one-to-many relationship between the Date Table  and the pizza_sales table. 
- The Date Table serves as the primary date dimension supporting accurate time-based analysis and aggregations.

This relationship enables robust date filtering, calendar analysis, and correct calculation of time-series measures (e.g., running totals, monthly trends) within the BI reports.


![Data Modelling](https://github.com/kamalakannan-t/pizza-sales-analysis-powerbi/blob/main/screenshots/Data_Modelling.png?raw=true)


A card visual was used to represent Total Revenue.

![Total Revenue](https://github.com/kamalakannan-t/pizza-sales-analysis-powerbi/blob/main/screenshots/Total_Revenue.png?raw=true)

- Average Value Per Transaction

Following DAX expression was written to find Average Value Per Transaction

        Avg_value_per_transaction = DIVIDE(SUM(pizza_sales[total_price]),DISTINCTCOUNT(pizza_sales[order_id]))

A card visual was used to represent Average Value Per Transaction

![Avg_Value_Per_Transaction](https://github.com/kamalakannan-t/pizza-sales-analysis-powerbi/blob/main/screenshots/Avg_Value_Per_Transaction.png?raw=true)

- Running Total Sales By Month

Following DAX expression was written to find Running Total Sales By Month

        Current_Month_Sales = SUM(pizza_sales[total_price])

        Running Total Sales By Month = CALCULATE(
                [Current_Month_Sales],
                DATESYTD('Date Table'[Date]))

A Table visual was used to represent Running Total Sales By month

![Running Total Sales By Month](https://github.com/kamalakannan-t/pizza-sales-analysis-powerbi/blob/main/screenshots/Running%20Total%20Sales%20By%20Month.png?raw=true)

# Snapshot:

![Snapshot](https://github.com/kamalakannan-t/pizza-sales-analysis-powerbi/blob/main/screenshots/Snapshot.png?raw=true)
 

# Insights

Based on the key performance indicators (KPIs) provided in the analysis, several important insights can be derived which can help stakeholders gain valuable insights into the business's performance, customer behavior, and areas for improvement. These insights can inform strategic decision-making and help drive growth and profitability in the pizza business. Below are insights and recommendations:

- Classic pizzas drive the highest revenue but market share is relatively balanced across categories.
- Veggie category presents improvement opportunity - lowest revenue despite health trends.
- All categories perform within 3.23% range - indicates diverse customer preferences.
- Classic category pizzas dominate across all days of the month.
- Peak ordering day: 15th of each month (mid-month payday effect likely)
- Peak hour: 12 PM (lunch rush) - highest pizza orders.

# Recommendations

- **Veggie Category Focus**: Implement targeted marketing for health-conscious customers.
- **Cross-selling Initiative**: Current 2.32 items/order suggests potential to increase basket size.
- **Premium Pricing**: $16.49 average suggests room for selective price optimization.
- **Peak Hour Staffing**: Optimize workforce allocation for 12 PM rush.
- **Mid-month Promotions**: Leverage 15th-day peak with targeted offers.
- **Category Balance**: Promote Supreme and Chicken categories to match Classic performance.

