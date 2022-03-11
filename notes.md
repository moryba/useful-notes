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

# Regular expression

## Shorthand character classes

\w ---> the "word character" class represents the regex range [A - Za - z0 - 9_], and it matches a single uppercase character, lowercase character, digit or underscore

\d ---> the "digit character" class represents the regex range [0-9], and it matches a single digit character

\s ---> the "whitespace character" class represents the regex range [ \t\r\n\f\v], matchinga single space, tab, carriage return, line break, from feed, or vertical tab

For example, the regex \d\s\w\w\w\w\w\w\w matches a digit character, followed by a whitespace character, followed by 7 word characters. Thus the regex completely matches the text 3 monkeys. 

In addition to the shorthand character classes \w, \d, and \s, we also have access to the negated shorthand character classes! These shorthands will match any character that is NOT in the regular shorthand classes. These negated shorthand classes include:

- \W ---> the "non-word charcater" class represts the regex range [^A-Za-z0-9_], matching any character tha is not included in the range represented by \w
- \D ---> the "non-digit character" class represents the regex range [^0-9], matching any character that is not included in the range represented by \d
- \S ---> the "non-whitespace character" class represents the regex range [^\t\r\n\f\v], matching any character that is not included in the range represented by \s

## Grouping

The regext I love (baboons|gorillas) will match the text I love and then match either baboons or gorillas, as the grouping limits the reach of the | to the text within the parentheses. 

These groups are also called capture groups, as they have the power to select, or capture, a substring from our matched text. 

## Quantifiers - Fixed

Instead of writing the regex \w\w\w\w\w\w\s\w\w\w\w\w\w, which would match 6 word charcters, followed by a whitespace charcter, and then followed by more characters, such as in the text rhesus monkey, there is a a better way to denote the quantity of characters we want to match on. 

- \w{3} will match exactly 3 word characters
- \w{4,7} will match at minimum 4 word characters and at maximum 7 word characters

The regex roa{3}r will match the characters ro followed by 3 as, and then the character r, such as in the text roaaar. The regex roa{3,7}r will match the characters ro followed by at least 3 as and at most 7 as, followed by an r, matching the strings roaaar, roaaaaar and roaaaaaaar.


## Quantifiers - Optional

Optional quantifiers, indicated by the question mark ?, allow us to indicate a character in a regex is optional, or can appear either 0 times or 1 time. For example, the regex humou?r matches the characters humo, then either 0 occurrences or 1 occurrence of the letter u, and finally the letter r. Note ? only applies to the character directly before it. 

With all quantifiers, we can take advantage of grouping to make even more  advanced regexes. The regex 'The monkey ate a (rotten )?banana' will completely match both 'The monkey ate a rotten banana' and 'The monkey ate a banana'.

Since the ? is a metacharacter, you need to use the escape character in your regex in order to match a question mark ? in a piece of text. The regex 'Aren't owl monkeys beautiful\?' will thus completely match the text 'Aren't owl monkeys beautiful\?'.


## Quantifiers - 0 or More, 1 or More

The Kleene star, denoted with the asterisk *, is also a quantifier, and matches the preceding character 0 or more times. This means that the character doesn’t need to appear, can appear once, or can appear many many times.

The regex meo*w will match the characters me, followed by 0 or more os, followed by a w. Thus the regex will match mew, meow, meooow, and meoooooooooooow.

Another useful quantifier is the Kleene plus, denoted by the plus +, which matches the preceding character 1 or more times.

The regex meo+w will match the characters me, followed by 1 or more os, followed by a w. Thus the regex will match meow, meooow, and meoooooooooooow, but not match mew.

Like all the other metacharacters, in order to match the symbols * and +, you need to use the escape character in your regex. The regex My cat is a \* will completely match the text My cat is a *.

## Anchors

The anchors hat ^ and the dollar sign $ are used to match text at the start and the end of a string, respctively.  For example, the regex ^Monkeys: my mortal enemy$ will completely match the text Monkeys: my mortal enemy but not match Spider Monkeys: my mortal enemy in the wild or Spider Monkeys: my mortal enemy in the wild. In fact, the ^ ensures that the matched text begins with Monkeys, and the $ ensures the matched text ends with enemy. 





        
       
