
# 
# Use DAX time intelligence functions

DAX includes several time intelligence functions to simplify the task of modifying date filter context. You could write many of these intelligence formulas by using a function that modifies date filters, but that would create more work.

Note

Many DAX time intelligence functions are concerned with standard date periods, specifically years, quarters, and months. If you have irregular time periods (for example, financial months that begin mid-way through the calendar month), or you need to work with weeks or time periods (hours, minutes, and so on), the DAX time intelligence functions won't be helpful. Instead, you'll need to use the function and pass in hand-crafted date or time filters.

### 
# Date table requirement

To work with time intelligence DAX functions, you need to meet the prerequisite model requirement of having at least one *date table* in your model. A date table is a table that meets the following requirements:

- It must have a column of data type Date (or date/time), known as the *date column*.
- The date column must contain unique values.
- The date column must not contain BLANKs.
- The date column must not have any missing dates.
- The date column must span full years. A year isn't necessarily a calendar year (January-December).
- The date table must be indicated as a date table.

For more information, see [Create date tables in Power BI Desktop](/en-us/power-bi/guidance/model-date-tables/?azure-portal=true).

### 
# Summarizations over time

One group of DAX time intelligence functions is concerned with summarizations over time:

- - Returns a single-column table that contains dates for the year-to-date (YTD) in the current filter context. This group also includes the  and  DAX functions for month-to-date (MTD) and quarter-to-date (QTD). You can pass these functions as filters into the  DAX function.
- - Evaluates an expression for YTD in the current filter context. The equivalent QTD and MTD DAX functions of  and  are also included.
- - Returns a table that contains a column of dates that begins with a given start date and continues until a given end date.
- - Returns a table that contains a column of dates that begins with a given start date and continues for the specified number of intervals.

Note

While the function is simple to use, you are limited to passing in one filter expression. If you need to apply multiple filter expressions, use the function and then pass the function in as one of the filter expressions.

In the following example, you will create your first time intelligence calculation that will use the TOTALYTD function. The syntax is as follows:

The function requires an expression and, as is common to all time intelligence functions, a reference to the date column of a marked date table. Optionally, a single filter expression or the year-end date can be passed in (required only when the year doesn't finish on December 31).

Download and open the [**Adventure Works DW 2020 M07.pbix**](https://github.com/MicrosoftDocs/mslearn-dax-power-bi/raw/main/activities/Adventure%20Works%20DW%202020%20M07.pbix) file. Then, add the following measure definition to the **Sales** table that calculates YTD revenue. Format the measure as currency with two decimal places.

The year-end date value of represents June 30.

On **Page 1** of the report, add the **Revenue YTD** measure to the matrix visual. Notice that it produces a summarization of the revenue amounts from the beginning of the year through to the filtered month.

[![An image shows a matrix visual with grouping on Year and Month on the rows and Revenue and Revenue YTD summarizations. The YTD values are highlighted.](media/dax-matrix-revenue-ytd-activity-ssm.png)](media/dax-matrix-revenue-ytd-activity-ssm.png#lightbox)

### 
# Comparisons over time

Another group of DAX time intelligence functions is concerned with shifting time periods:

- - Returns a table that contains a column of dates, shifted either forward or backward in time by the specified number of intervals from the dates in the current filter context.
- - Returns a table that contains a column of dates that represents a period that is parallel to the dates in the specified dates column, in the current filter context, with the dates shifted a number of intervals either forward in time or back in time.
- - Returns a table that contains a column of dates that are shifted one year back in time from the dates in the specified dates column, in the current filter context.
- Many helper DAX functions for navigating backward or forward for specific time periods, all of which returns a table of dates. These helper functions include , , , , and , , , and .

Now, you will add a measure to the **Sales** table that calculates revenue for the prior year by using the function. Format the measure as currency with two decimal places.

Add the **Revenue PY** measure to the matrix visual. Notice that it produces results that are similar to the previous year's revenue amounts.

[![An image shows a matrix visual with grouping on Year and Month on the rows and Revenue, Revenue YTD, and Revenue PY summarizations. The Revenue PY month values for FY2019 equal the Revenue month values for FY2018.](media/dax-matrix-revenue-py-ssm.png)](media/dax-matrix-revenue-py-ssm.png#lightbox)

Next, you will modify the measure by renaming it to **Revenue YoY %** and then updating the clause to calculate the change ratio. Be sure to change the format to a percentage with two decimals places.

Notice that the **Revenue YoY %** measure produces a ratio of change factor over the previous year's monthly revenue. For example, July 2018 represents a 106.53 percent *increase* over the previous year's monthly revenue, and November 2018 represents a 24.22 percent *decrease* over the previous year's monthly revenue.

[![An image shows a matrix visual with grouping on Year and Month on the rows and Revenue, Revenue YTD, and Revenue YoY % summarizations. The Revenue YoY % month values for FY2019 are values that are formatted as percentages.](media/dax-matrix-revenue-yoy-ssm.png)](media/dax-matrix-revenue-yoy-ssm.png#lightbox)

Note

The **Revenue YoY %** measure demonstrates a good use of DAX variables. The measure improves the readability of the formula and allows you to unit test part of the measure logic (by returning the **RevenuePriorYear** variable value). Additionally, the measure is an optimal formula because it doesn't need to retrieve the prior year's revenue value twice. Having stored it once in a variable, the clause uses to the variable value twice.



