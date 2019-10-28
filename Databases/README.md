# Lab Databases
Lab exercises. Introduction to Information Technology. Databases. Based on Sullivan, Dan. NoSQL for mere mortals. 

This course of the Khan Academy teaches how to create your own database:
https://www.khanacademy.org/computing/hour-of-code/hour-of-sql/pp/project-design-a-store-database

The school library provides several books as online resources. You can access them through the library databases link: https://www.himolde.no/bibliotek/english/databases/ in the Database Ebook Central ProQuest - E-books in full text. 

We are not going to delve into the details of Database design because you are going to have a course in Databases on the next semester. In this class we will show you what you can do with databases. At the end of this class you will be able to create a simple database and use it in your project.

Objective: This is a hands-on lab on Databases

#NoSQL databases:
The most widely used types of NoSQL databases are:
- Key-Value pair: DynamoDB, LevelDB, Riak, Tokyo/Kyoto Cabinet, Oracle NoSQL DB
- Document: MongoDB, CouchDB
- Column family store: Hypertable. MariaDB, Apache HBase
- Graph Databases: Neo4J, DEX, GraphBase, GraphChi

Lets play with the Amazon's database: DynamoDB. DynamoDB is a key-value pair NoSQL database
https://www.qwiklabs.com/focuses/7781?parent=catalog

<!--### Key-Value pair databases
Introduction to the technology: explain the data model (what makes all the systems in the class similar)-->
<!--Gives an assessment of the types of workloads for which it is and is not well-suited.-->
<!--Compares several of the specific products in the class, contrasting the things that are different between systems.-->

## My first Relational database
Now let's create a similar data storage in our playground using SQL.

<!--MongoDB Atlas https://www.youtube.com/watch?v=leNNivaQbDY
https://docs.mongodb.com/manual/faq/fundamentals/#how-do-i-create-a-database-and-a-collection
## Design a database-->

https://www.khanacademy.org/computing/hour-of-code/hour-of-sql/pp/project-design-a-store-database

--------------

Security:
In the browser, access the address (the IP will be informed by the teacher):
http://.../test_login.html
1) Start a new packet capture on Wireshark. Enter a fictitious user and password 123456 on the page. Click the Submit button and wait for the answer page.
2) Stop packet capture. **You have sent username and password data through the HTTP POST packet**. Click on this line. In the middle screen, click ⊳ to expand the information. Answer:
  a) Can you find the login and password information entered in the previous item?
  b) Is HTTP authentication secure? Why?
3) Send your answers through the Quiz in Canvas.
