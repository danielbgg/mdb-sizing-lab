# mdb-sizing-lab
MDB Sizing Lab 1.2

## USERS
* Generate 100,000 random JSON documents representing users, based on the `users_mgenerate.json` template:
  ```bash
  mgeneratejs users_mgenerate.json -n 100000 | mongoimport --uri "mongodb+srv://main_user:mypassword@democluster-abcd.mongodb.net/SIZING" --collection users --drop --numInsertionWorkers=10
  ```
* Create index via cli 
    `db.users.createIndex({"accounts.account_id":1})`


## TRANSACTIONS
* Generate 100,000 random JSON documents representing users, based on the `transactions_mgenerate.json` template:
  ```bash
  mgeneratejs transactions_mgenerate.json -n 100000 | mongoimport --uri "mongodb+srv://main_user:mypassword@democluster-abcd.mongodb.net/SIZING" --collection transactions --drop --numInsertionWorkers=10
  ```
* Create indexes via cli 
    `db.transactions.createIndex({"user_id":1, "amount":1})`
    `db.transactions.createIndex({"user_id":1, "vendor":1})`
    `db.transactions.createIndex({"account_id":1, "vendor":1})`


## EVENT_LOGS
* Generate 100,000 random JSON documents representing users, based on the `event_logs_mgenerate.json` template:
  ```bash
  mgeneratejs event_logs_mgenerate.json -n 100000 | mongoimport --uri "mongodb+srv://main_user:mypassword@democluster-abcd.mongodb.net/SIZING" --collection event_logs --drop --numInsertionWorkers=10
  ```

