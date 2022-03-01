# Build an environment

1 - mkdir a folder

2 - digit in the terminal ---> py -m env env

3 - cd dir to env

4 - go to ----> Scripts\activate

5 - install streamlit (or other programs) into the environment ------> pip install streamlit

6 - runnig your application ----> streamlit run app.py

# PowerBI - DAX formulas

1 - create a coumpund key -----> compund key = [ID] & "-" & [date]

2 - IF condition:

    - IF(Expression, Value if TRUE, Value if FALSE)
    
    - IF('Customer Data'[Shopping Frequency] IN {"Daily", "Monthly", "Weekly"},"Frequent Shopper","Infrequent Shopper")
    
3 - SWITCH -----> SWITCH("Customer Data"[State], "Texas", "Growth Market", "New York", "Estabilished Market", "Deprioritized Market")

4 - LOOKUPVALUE(Table2[column Interested), Table2[Key], Table1[Key])

5 - SUMX(Table, Table[Column]) ----> the output is the sum of all the values in a column

6 - Table1[Column1] * RELATED(Table2[Column2])) ----> RELATED fuction give us the product between column1 in table1 and the column2 of the table2. Keep in mind that the two tables must have a relationship 

# Data Viz
- [A Complete Guide to Bar Charts](https://chartio.com/learn/charts/bar-chart-complete-guide/)
- [A Complete Guide to Area Charts](https://chartio.com/learn/charts/area-chart-complete-guide/)
- [Change How Visuals Interact in a Report](https://docs.microsoft.com/en-us/power-bi/create-reports/service-reports-visual-interactions)
- [Battle of the Charts: Pie Chart vs. Donut Chart](https://www.beautiful.ai/blog/battle-of-the-charts-pie-chart-vs-donut-chart)
- [7 Secrets of the Matrix Visual](https://www.burningsuit.co.uk/7-secrets-of-the-matrix-visual/)
- [A Complete Guide to Scatter Plots](https://chartio.com/learn/charts/what-is-a-scatter-plot/)
- [Tips and Tricks for Power BI Map Visualizations](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-map-tips-and-tricks)
- [Create and Use Filled Maps (Choropleth Maps) in Power BI](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-filled-maps-choropleths)
- [Design guide for Power BI Slicers and filters](https://okviz.com/blog/design-guide-for-power-bi-slicers-and-filters/)

# How to create a dynamic date table on Power Query

- Create a query for the Start Date ----->Strat = Date.StartOfYear(List.Min(#"Name of the table"[Column Date]))
- Create a query for the End Date ------> End = Date.StartOfYear(List.Max(#"Name of the table"[Column Date]))
- Create a list and convert it into a table ------> ={Number.From(#"Start")..Number.From(#"End")}
- suggestions---> if you wanna put zero before the number of the month: = Text.PadStart(Text.From([Month Name]),2,"0")

# Power App - some useful links

List of useful links:

- [Text Input AutoHeight](https://www.youtube.com/watch?v=Rh20he80OLA)

# Some cmd prompt

- append multiple files------> copy *.csv combine.csv
- download this browser to run selenium edge: https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/
                
        
       
