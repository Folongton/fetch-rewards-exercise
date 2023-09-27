## fetch-rewards-exercise

* This exercise was done for one of the interview questions. The requirements were:
1. to create a DB from unstructured data.
2. Do an analysys on data
3. Prepare communicate findings to stakeholders.
   ---------

### 1. New Structured Relational Data Model
Using a diagram from DBeaver. I have decided to move out "items" Table. "items" table corresponds to the "rewardsReceiptItemList" attribute from our receipts.json file. Primary Keys are shown in Bold. I could have also simply flatten the whole receipts.json to a single table, but decided to keep it cleaner with Junction table.

![new_er](https://github.com/Folongton/fetch-rewards-exercise/blob/master/fetch-ER.png)

### 2. Write a query that directly answers a business question.
I have built DB using SQLite and was runnig queries from Jupyter Notebook. However, since we were using dummy data, queries doesn't provide any useful information.
<a href="https://nbviewer.jupyter.org/github/Folongton/fetch-rewards-exercise/blob/master/fetch_rew.ipynb#1842-out-of-5753-is-not-terribly-bad-considering-dummy-data.">Queries URL.</a>

### 3. Evaluate data quality issues in the data provided.
I went thru the process of transfering messy JSON to RDB building actual Database. Here are some, but not all issues I have found along my procces:
1. Incompleteness: There are many things missing from the data, but here are an example of "empty" receipts. Those are basically have only date and ID, with no useful information. <a href="https://nbviewer.jupyter.org/github/Folongton/fetch-rewards-exercise/blob/master/fetch_rew.ipynb#Some-of-the-receipts-have-no-items-on-them,-as-shown-below.-We-have-to-drop-the-empty-receipts."> "empty" receipts URL.</a> Besides this, data has many NaN values everywhere as it was sourced from NoSQL format.
2. Inaccuracy: Since it is dummy data most of it is inaccurate. As an example <a href="https://nbviewer.jupyter.org/github/Folongton/fetch-rewards-exercise/blob/master/fetch_rew.ipynb#Now,-let's-format-brands.json.gz"> here</a> in the brands DataFrame we have column "name" and "branCode" with test values.
3. Redundancy: <a href="https://nbviewer.jupyter.org/github/Folongton/fetch-rewards-exercise/blob/master/fetch_rew.ipynb#Now-let's-format-users.json.gz"> User Ids </a> and many other supposedly unique attributes entered many times over, making it hard to relate the tables.

### 4. Communicate with Stakeholders.
Hello, Stakeholder. \
This is Vasyl Zhepikov from the Data Analytics department. \
We have received your data. Before procceding to the implementation we would like to discuss some asspects of it to be sure we are on the same page. 
1. Please, let us know how do you define "barcode" attribute in your data ? As we see that barcodes quantity almost indentical to the quantity of the brands. From my past experience in marketing I know "barcode" usually referse to the UPC barcodes - unique to each product, not a brand. 
2. We have also spotted many empty receipts - receipts with no items on. Please, let us know how this scenario possible and if it contains any meaningfull information, or we can simply disregard empty receipts.
3. We would like to have more data regarding "items" and "cpg" (Consumer Packaged Goods) in order to be able provide more insights for the business. Please, let us know if we can obtain that information.
4. After reviewing the initial batch of data we have calculated potential data storage needed and decided to recommend starting the project on a cloud such as AWS (Amazon Web Services) or GCP (Google Cloud Platform) where you be able succesfully scale without potential hurdles updating and managing your own servers. Cloud services have scalability "on-demand" as well as robust tools for the analysis of the data. Let's discuss this in details on our next one-on-one meeting.


Thank you. \
Best Regards \
Vasyl Zhepikov
