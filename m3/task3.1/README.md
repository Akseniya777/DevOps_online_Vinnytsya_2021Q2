# Module 3. Database Administration

### Hello. After reading the training material of module 3 "Database Administration", and having completed the task of this module, I would like to present below my progress reportH.

### By completing Task 3.1 of Module 3, I got acquainted with the peculiarities of working with relational databases, learned how to create and delete MySQL databases through the server console, create tables with columns and insert ine data in it, modify, delete, and execute various queries. I also got acquainted with the basic principles of the RDS service for creating a database server creation, as well as with NoSQL databases from AWS - DynamoDB.

# PART 1

* First of all I've created EC2 instance with Centos 7 OS, and downloaded and MySQL on it:
![stack Overflow](https://image.prntscr.com/image/tG8QiA6aQqiZWoWBNlFLKA.png)
![stack Overflow](https://image.prntscr.com/image/fANMIPAoTNCKi11vxCp2Qg.png)

* I've scessfully run and completed MySQL server installation on my instance:
![stack Overflow](https://image.prntscr.com/image/NlCVe2TtTh6lpUql5iTy-w.png)
![stack Overflow](https://image.prntscr.com/image/pNHFKCHLQ7qD1b8uAvH-hg.png)
![stack Overflow](https://image.prntscr.com/image/kkkIKhFmS9GBjSWeOGE7Cw.png)
![stack Overflow](https://image.prntscr.com/image/9vkr-0a1RSCJ-F5OxpSqjw.png)

* after MySQL server installation, I've connected to MySQL, selected main database, view and describe it's schema by selecting 3 tables:
![stack Overflow](https://image.prntscr.com/image/G446XB_RTlGqkeMSzHdJsA.png)
![stack Overflow](https://image.prntscr.com/image/0jROEYCFRVuPd9GtdG3dig.png)
![stack Overflow](https://image.prntscr.com/image/rITVH4AMSWm46w7YP-IbHg.png)
![stack Overflow](https://image.prntscr.com/image/ANQatyfWQECf1UVReGLT1g.png)
![stack Overflow](https://image.prntscr.com/image/VutY3zIjQFm43tNnS2N2SQ.png)

* I've created a database on the server through the console, have also created 2 tables with columns:
![stack Overflow](https://image.prntscr.com/image/r5tae1pWS4WZFylRZN1FEw.png)
![stack Overflow](https://image.prntscr.com/image/hrUgwZxYRxSnc7PXG7EqLw.png)
![stack Overflow](https://image.prntscr.com/image/DhaChN_zTO2xy6RGgVR-7g.png)

* I've filled in created database tables by inserting the data into columns:
![stack Overflow](https://image.prntscr.com/image/hUXCeGfLQrak2pn8F3Xpnw.png)
![stack Overflow](https://image.prntscr.com/image/kFcdGTPlRYy3rDk8jYORAw.png)
![stack Overflow](https://image.prntscr.com/image/iy7JHy9nRUG5J3xNNFPfpw.png)
![stack Overflow](https://image.prntscr.com/image/e72dPsfQRUaslOzTegpAyw.png)

* Have executed different queries with SELECT operator with WHERE, GROUP BY and ORDER BY:
![stack Overflow](https://image.prntscr.com/image/LOvZcxrtQGyDNWT8XEhbJg.png)
![stack Overflow](https://image.prntscr.com/image/fzYxBF0pQ7Cn-eOW2Pu3Eg.png)
![stack Overflow](https://image.prntscr.com/image/Be2AJ7KMQRG0qp2-TCJMRQ.png)
![stack Overflow](https://image.prntscr.com/image/w2iuJ-kxRuKf0NABnuzkcQ.png)

* have also created database user and granted full privilleges on it:
![stack Overflow](https://image.prntscr.com/image/bsoYAbYrQL2Wa8Wi5He_Ew.png)
![stack Overflow](https://image.prntscr.com/image/bgvAaXmnR5W9Ac_-4WmSYQ.png)

* I've made s selection from selection the main table 'db' of tatabase 'mysql':
![stack Overflow](https://image.prntscr.com/image/dh88JM06QlO8XuRS4ebY8g.png)

# PART 2

* I've created my database backup:
![stack Overflow](https://image.prntscr.com/image/gVveiRe_T1edP_unwKSE3A.png)

* after that have deleted table from database, and then restored database from previously created backup:
![stack Overflow](https://image.prntscr.com/image/sXi2qHpjTpSKSRd16Q86_g.png)
![stack Overflow](https://image.prntscr.com/image/soAKve2STHe8iXMq0IqrxA.png)

* I've created RDS Database Server, after that have connected to new RDS Database Serverfrom my EC2 instance where I've saved database backup, transferred and restored MySQL database backup from EC2 instance to RDS Server:
![stack Overflow](https://image.prntscr.com/image/4ewqwcs5Syi4D0qgf0UGMA.png)
![stack Overflow](https://image.prntscr.com/image/aNMd2FZeRwSELDtubA5Jig.png)

* have executed SELECT operator on RDS:
![stack Overflow](https://image.prntscr.com/image/cQNsZ2kMRM6Dy7-RDFSwmA.png)
![stack Overflow](https://image.prntscr.com/image/lpIQuJmsRNmrWSp_yclmsw.png)

* and created the dump of my database on my laptop by connecting to RDS server:
![stack Overflow](https://image.prntscr.com/image/iwS9vFx_R9iKBtQ5TePLag.png)

# PART 3

* I've created NoSQL table using Amazon DynamoDB:
![stack Overflow](https://image.prntscr.com/image/Q9IVwMQgSzW3WXhb8v4k7Q.png)

* have inserted data into my table:
![stack Overflow](https://image.prntscr.com/image/4v_yZIhaQKGW7D_PAkLpIg.png)

* and executed query into Amazon DynamoDB table using Query and Scan:
![stack Overflow](https://image.prntscr.com/image/yB1Ra9RUS7WicOudvHAVSA.png)
![stack Overflow](https://image.prntscr.com/image/wU6g0cpaTl_tqDIO-qgUbA.png)
![stack Overflow](https://image.prntscr.com/image/Sd0whdjDSXyyqPZRJhEmQw.png)

### Thank you for attention!
