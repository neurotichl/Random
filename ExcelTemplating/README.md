# Excel Template using Pandas ExcelWriter

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
