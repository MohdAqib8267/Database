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

#### Clustering Index
A clustered index can be defined as an ordered data file. Sometimes the index is created on non-primary key columns which may not be unique for each record.
In this case, to identify the record faster, we will group two or more columns to get the unique value and create index out of them. This method is called a clustering index.
The records which have similar characteristics are grouped, and indexes are created for these group.
Example: suppose a company contains several employees in each department. Suppose we use a clustering index, where all employees which belong to the same Dept_ID are considered within a single cluster, and index pointers point to the cluster as a whole. Here Dept_Id is a non-unique key.
![dbms-indexing-in-dbms_6](https://github.com/MohdAqib8267/Database/assets/106628860/35a6cb43-783f-40f3-a048-1147c7b698d0)
