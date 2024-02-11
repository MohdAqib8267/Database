# Database

## Indexing in DBMS
Indexing is used to optimize the performance of a database by minimizing the number of disk accesses required when a query is processed. <br/>
The index is a type of data structure. It is used to locate and access the data in a database table quickly.
Index structure:<br/>
Indexes can be created using some database columns.
> |search key | data refernse |
<br/>
 -> The first column of the database is the search key that contains a copy of the primary key or candidate key of the table. The values of the primary key are stored in sorted order so that the corresponding data can be accessed easily. <br/>
 
-> The second column of the database is the data reference. It contains a set of pointers holding the address of the disk block where the value of the particular key can be found.

DBMS Indexing in DBMS

#### Primary Index
If the index is created on the basis of the primary key of the table, then it is known as primary indexing. These primary keys are unique to each record and contain 1:1 relation between the records.<br/>
As primary keys are stored in sorted order, the performance of the searching operation is quite efficient. <br/>
The primary index can be classified into two types: Dense index and Sparse index.<br/>
###### Dense index
The dense index contains an index record for every search key value in the data file. It makes searching faster.
In this, the number of records in the index table is same as the number of records in the main table.
It needs more space to store index record itself. The index records have the search key and a pointer to the actual record on the disk
![dbms-indexing-in-dbms_3](https://github.com/MohdAqib8267/Database/assets/106628860/a0f61e20-72c8-4311-a505-f56c53d079ae)

##### Sparse index
In the data file, index record appears only for a few items. Each item points to a block.
In this, instead of pointing to each record in the main table, the index points to the records in the main table in a gap.
![dbms-indexing-in-dbms_4](https://github.com/MohdAqib8267/Database/assets/106628860/34c85ec7-41bf-4cd3-a86b-c70f88bb9001)

#### Clustering Index
A clustered index can be defined as an ordered data file. Sometimes the index is created on non-primary key columns which may not be unique for each record.
In this case, to identify the record faster, we will group two or more columns to get the unique value and create index out of them. This method is called a clustering index.
The records which have similar characteristics are grouped, and indexes are created for these group.
Example: suppose a company contains several employees in each department. Suppose we use a clustering index, where all employees which belong to the same Dept_ID are considered within a single cluster, and index pointers point to the cluster as a whole. Here Dept_Id is a non-unique key.
![dbms-indexing-in-dbms_6](https://github.com/MohdAqib8267/Database/assets/106628860/35a6cb43-783f-40f3-a048-1147c7b698d0)

#### Secondary Index
In the sparse indexing, as the size of the table grows, the size of mapping also grows. These mappings are usually kept in the primary memory so that address fetch should be faster. Then the secondary memory searches the actual data based on the address got from mapping. If the mapping size grows then fetching the address itself becomes slower. In this case, the sparse index will not be efficient. To overcome this problem, secondary indexing is introduced. <br/>

In secondary indexing, to reduce the size of mapping, another level of indexing is introduced. In this method, the huge range for the columns is selected initially so that the mapping size of the first level becomes small. Then each range is further divided into smaller ranges. The mapping of the first level is stored in the primary memory, so that address fetch is faster. The mapping of the second level and actual data are stored in the secondary memory (hard disk).
![dbms-indexing-in-dbms_7](https://github.com/MohdAqib8267/Database/assets/106628860/ce94e5bc-ae69-4b5c-9f10-7391b959c915)

## What Is a Data Warehouse?
A data warehouse is a type of database that’s designed for reporting and analysis of a company’s data. It collects data from one or many sources, restructures it in a specific way, and allows business users to analyse and visualise the data.
#### Why Do We Need a Data Warehouse?
You’ve probably heard of databases that are used for storing data for applications or websites. These databases specialise in recording transactional data: things that happen during the operation of a business. Some examples are:

>Hotel reservations
>Airline bookings
>Student course enrolments
>Posts on a forum
>Sign-ups and sales on an eCommerce website

##### If we have these databases, why do we need a data warehouse?
Why don’t we just run analytics on the normal database?
<br/>
The main reason is performance.
##### So, the two main reasons to use a data warehouse are performance-related:

> Allow business users to analyse data quickly using a specialised database design
> Prevent the main transactional database from slowing down due to data analysis
#### Data Warehouse vs Database (OLAP vs OLTP)
There are many differences between a traditional database that you might use for a website or application and a data warehouse.

Two terms you might see when referring to these databases are OLAP and OLTP.

OLAP stands for OnLine Analytical Processing, and represents databases that work like a data warehouse: focused on analysis instead of inserts and updates.

OLTP stands for OnLine Transaction Processing, and represents databases used for transactional data (inserts and updates), such as websites and applications.
<img width="515" alt="Screenshot 2024-02-11 131125" src="https://github.com/MohdAqib8267/Database/assets/106628860/6a8e2445-7de6-45f8-97c8-e55413ae7df4">

### B+ Tree
The B+ tree is a balanced binary search tree. It follows a multi-level index format.

In the B+ tree, leaf nodes denote actual data pointers. B+ tree ensures that all leaf nodes remain at the same height.

In the B+ tree, the leaf nodes are linked using a link list. Therefore, a B+ tree can support random access as well as sequential access.
![dbms-b-plus-tree](https://github.com/MohdAqib8267/Database/assets/106628860/5ff62116-8745-492e-ac94-448b568840fa)
