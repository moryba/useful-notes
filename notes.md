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
    . IF(Expression, Value if TRUE, Value if FALSE)
    . IF('Customer Data'[Shopping Frequency] IN {"Daily", "Monthly", "Weekly"},"Frequent Shopper","Infrequent Shopper")
    
3 - SWITCH -----> SWITCH("Customer Data"[State], "Texas", "Growth Market", "New York", "Estabilished Market", "Deprioritized Market")


                
        
       