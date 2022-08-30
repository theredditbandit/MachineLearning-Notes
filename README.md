# MachineLearning-Notes

## Data cleaning and labeling

### Labeling
To lable the data initially load it into google sheets and then we can edit the column names accordingly , same can be done using code but google sheets was more convenient at the time.

### Cleaning
```py
import pandas as pd

dataframe = pd.read_csv('C:\CSV_Formatted_Data.csv')
csvfile = dataframe.fillna(method = 'ffill')
csvFile = csvfile.drop(['Unnamed: 12'],axis =1)
dataframe2 = pd.DataFrame(csvFile)
dataframe2.to_csv('CSV_Formatted_DATA.csv', index = False)
```
- In line 1 we are importing pandas.
- In the second line we are the reading the file via its path and storing it in the variable `dataframe`
- Finally we are cleaning the data with the method `.fillna(method = ffill)` which fills all the `NaN` cells with the content of the preceding cell.
- Since we are unsure about the data in the last column of our dataset , we're dropping the column with `.drop` method.
- Then in the next we are saving the changes made in a variable called `csvfile` which is inturn saved inside `dataframe2` 
- In the last line we're finally converting `dataframe2` to a csv file. 

