# Excel Template using Pandas ExcelWriter
I found it a tedious work when doing documentation for data transformation. For example, one need to record the source of the data (which database?), the column names, the renamed-column names, transformation logic (left join, filter XXX= ??, lag a column by ??, group into categories of 5,... etc) and remarks into Excel file for easy reference in future. As the number of table increase, in which the format, template and transformation logic are usually repetitive, I have decided to stop doing it manually. Instead, with the help of ExcelWriter from pandas, I create a template for the documentation, and 'paste' the dataframe with the information I needed into it. e.g. of the dataframe:

Table|Column|Name|Logic
---|---|---|---
Card|F_NME|First Name|capitalize all the characters
Transaction|AMT|Spend Amount|sum(AMT)

The df will be fed to the templat and look gorgeous later. (Bolded header text, with colored backgroun etc)

In this example, I do a simple demonstration on how to create template using pd.ExcelWriter. The data used here is NOT the usual data I process in my work, I just simply crawled data (i.e. skill points and statistics of the anime characters from Hunter x Hunter) from wikia. 

# Steps
1. Crawl Hunter x Hunter info from [Hunterpedia](http://hunterxhunter.wikia.com/wiki/Hunterpedia). Python script is `hunter.py`
    ```
    python hunter.py
    ```
    The result will output into a jsonfile : `hunter.json`.
    
2. Specify other hardcode parameters in `hunter.ini`

3. Templating codes are in the notebook. Process crawled data, write template and save it to a file

# [Go to the Notebook](https://github.com/neurotichl/Random/blob/master/ExcelTemplating/excel.ipynb)

---

# Notes
- **xlsxwriter** is used as the writer engine here. It can only write but not read the sheets. Hence the sheets must be one-time batch-produced. (Appending new sheet to already written excel is not possible)

- No way to specify the size of image yet (Future work (?)), Image can only be scaled.

#### Simple code usage
- **applymap** : map the functino to every series in the df
- **ascii_uppercase** : to loop A B C D
- **FEED_URI** and **FEED_FORMAT** : used in the setting of CrawlerProcess to output results as json file.
