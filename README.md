## fetch-rewards-exercise

### 1. New Structured Relational Data Model
Using a diagram from DBeaver. I have decided to move out "items" Table. "items" table corresponds to the "rewardsReceiptItemList" attribute from our receipts.json file. Primary Keys are shown in Bold. I could have also simply flatten the whole receipts.json to a single table, but decided to keep it cleaner with Junction table.

![new_er](https://github.com/Folongton/fetch-rewards-exercise/blob/master/fetch-ER.png)

### 2. Write a query that directly answers a business question.
I have built DB using SQLite and was runnig queries from Jupyter Notebook. However, since we were using dummy data, queries doesn't provide any useful information.
<a href="https://nbviewer.jupyter.org/github/Folongton/fetch-rewards-exercise/blob/master/fetch_rewards_exercise.ipynb#1842-out-of-5753-is-not-terribly-bad-considering-dummy-data.">Query URL.</a>

