# AMA

### What is foobar?

- Foo" and "bar" as metasyntactic variables were popularised by MIT and DEC, the first references are in work on LISP and PDP-1 and Project MAC from 1964 onwards.


- Both "foo" and "bar" (and even "baz") were well known in popular culture, especially from Smokey Stover and Pogo comics, which will have been read by many TMRC members.

Also, it seems likely the military FUBAR contributed to their popularity.

- FUBAR : Fucked/Fouled Up Beyond All Recoginition/Repair - Military Slang


### What is Database Sharding?

Any application or website that sees significant growth will eventually need to scale in order to accommodate increases in traffic.

It can be difficult to predict how popular a website or application will become or how long it will maintain that popularity, which is why some **organizations choose a database architecture that allows them to scale their databases dynamically.**

Sharding is a database Architechture pattern related to <em>horizontal partitioning</em> --  **the practice of separating one table’s rows into multiple different tables, known as partitions.**

Each **partition has the same schema and columns**, but also **entirely different rows.** Likewise, the data held in each is unique and independent of the data held in other partitions.

**Sharding**

- Sharding involves breaking up one’s data into two or more smaller chunks, called **logical shards**.

- The logical shards are then distributed across separate database nodes, referred to as physical shards, which can hold **multiple logical shards**.

- Collection of theses **Logical shards**


![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/db_partioning.png "Database Sharding")


#### Horizontal Scaling
- **Horizontal scaling** is the practice of adding more machines to an existing stack in order to spread out the load and allow for more traffic and faster processing.

#### Vertical scaling
- **Vertical Scaling** also known as **Scaling in** which involves upgrading the hardware of an existing server, usually by adding more RAM or CPU.


#### Benefits
- The main appeal of sharding a database is that it can help to facilitate **horizontal scaling**, also known as **scaling out**.

- It’s relatively simple to have a relational database running on a single machine and scale it up as necessary by upgrading its computing resources.

- Database sharding speeds up the query response time. When you are querying un-sharded database then it will search through each and every row of the database before it can display the result

- Sharding makes the application more reliable. When there is outage in the non-sharded database, it can make whole application unavailable. On the other hand, only some part of application will be unavaible in case Database sharding. The overall impact will be less than if entire database crashed.

#### Drawbacks of Sharding

-  If Sharding is **done incorrectly**, there’s a significant **risk that the sharding process can lead to lost data or corrupted tables.**

- Even if done correctly, there is **significant change in the workflow of teams.** Sometimes it distrupts the whole flow of a team i.e Rather than accessing and managing one’s data from a single entry point, users must manage data across multiple shard locations

- **Shards Becoming Unbalanced**. Let's say you have a databases that has two shards. One shards contains the names of customers Starting with 'A' to 'M', the other one with 'N' to 'Z'. One with 'A' to 'M' has more records than 'N' to 'Z'. Which can slow down application while querying shard with more records.
Shard with names 'A' to 'M' becomes the **hotspot**, which cancels out the benefit of sharding. The **database would likely need to be repaired and resharded** to allow **for a more even data distribution**.

- Finally, **sharding isn’t natively supported by every database engine.** For instance, **PostgreSQL does not include automatic sharding as a feature**, although it is **possible to manually shard a PostgreSQL database.**



#### Types of Shards

#### Key Based Sharding

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/key_based_shard.png "Key based Database Sharding")



#### Range Based Sharding

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/range_based_shard.png "range based Database Sharding")



#### Directory Based Sharding

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/directory_based_shard.png "Directory based Database Sharding")


### What is Deadlocks in Database?
- In a database, a deadlock is a situation in which two or more transactions are waiting for one another to give up locks.

- **For example,**
 **Transaction A** might hold a lock on some rows in the Accounts table and needs to update some rows in the Orders table to finish.
- **Transaction B** holds locks on those very rows in the Orders table but needs to update the rows in the Accounts table held by Transaction A.
- Transaction A cannot complete its transaction because of the lock on Orders. Transaction B cannot complete its transaction because of the lock on Accounts.
- All activity comes to a halt and remains at a standstill forever unless the DBMS detects the deadlock and aborts one of the transactions.

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/deadlock.gif "Deadlock in database visualization")




### How will you iterate over document.getElementsByClassName?
 - It returns a HTMLCollection (type). You will have to use

 ```javascript
 let elements = document.getElementsByClassName('card-div');
Array.from(elements).forEach((ele) => {
    // Do stuff here
    console.log(ele.tagName);
});
// you can also use elementIndex - 0, 1, 2
elements.item(elementIndex);

// .length to get length of the HTML collection
elements.length;

// Array.from() Returns a shallow copy of the elements
```

### What is Cross Join in SQL?
- In SQL, the **CROSS JOIN** is used to combine each row of the first table with each row of the second table. It is also known as the **Cartesian join** since it returns the Cartesian product of the sets of rows from the joined tables.


### What schema (in databases)?
**Schema** is the blueprint of the database.

- A database schema represents the **logical configuration of all or part of a relational database.**

- It can exist both as a **visual representation** and as a **set of formulas known as integrity constraints** that govern a database.

### What are Self invoking function (in javascript)?
- A **self-invoking** (also called self-executing) function is a **nameless (anonymous)** function that is **invoked immediately after its definition.**


**Example**
```javascript
(function(){
	console.log(Math.PI);
})();
```
#### passing parameters inside the self-invoking functions

``` javascript
(function(welcomeMessage){
	console.log(welcomeMessage);
})("Welcome to the World of Asynchornous Programming!");
```

### What is Morgan (node package) use for?
- Morgan is used for **access log**.

### What is DFA (Definite Finite Automata)?

#### Finite State Machine
 -  Finite State Machine is a **mathematical model of computation**. It is an **abstract machine** that can be in exactly one of a finite number of states at any given time.


 - The FSM can **change from one state to another** in response to **some external inputs** and/or a condition is satisfied; the **change from one state to another** is called a **transition**


 **Example**

 - Turn site in metros
	![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/turnesite.jpg "turnsite in metros")

- **State Machine**

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/simple_state_machine.png "simple state machine")


- **States Table**
![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/states_table.png "states in machine")

#### Deterministic Finite Automaton

- DFA is a finite-state machine that **accepts or rejects** a given string of symbols, by **running through a state sequence uniquely** determined by the string.

### What is Normalization (in Database)?

- It is the processes of reducing the redundancy of data in the table and also improving the data integrity


**Without normaliztion**

- Repetition of data increases the size of database.
- creates difficulty in reading, updating and creating new records.

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/normalization.png "Database Normalization")


#### Database Normalization Rules

 - **1NF**
 - **2NF**
 - **3NF**
 - **Boyce-Codd NF**


#### 1NF

- In this Normal Form, **we tackle the problem of atomicity**. Here, atomicity means **values in the table should not be further divided.**

- In simple terms, a single cell cannot hold multiple values. If a table contains a composite or multi-valued attribute, it violates the First Normal Form.

- **For Example**

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/1NF-first.png "1NF first")

- In the above table, we can clearly see that the Phone Number column has two values. Thus it violated the 1st NF. Now if we apply the 1st NF to the above table we get the below table as the result.


![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/1NF-second.png "1NF second")

- By this, we have achieved atomicity and also each and every column have unique values.

#### 2NF

- Everything that is in **1NF** plus table also should **not** contain **partial dependency**. Here, partial dependency means the proper subset of candidate key determines a non-prime attribute.


- **For Example**

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/2NF-first.png "2NF first")

- This table has a **composite primary key Emplyoee ID, Department ID.** The non-key attribute is Office Location. In this case, Office Location only depends on Department ID, which is only part of the primary key. Therefore, this table does not satisfy the second Normal Form.


- ![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/2NF-second.png "2NF second")

- we have removed the partial functional dependency that we initially had. Now, in the table, **the column Office Location is fully dependent on the primary key** of that table, which is **Department ID**.


#### 3NF

- In 3NF, It should satisfy all the condition of 1NF, 2NF plus eliminate **transitive dependency**

- A transitive dependency in a database is an **indirect relationship between values in the same table** that causes a functional dependency.

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/3NF-first.png "3NF first")

- **Book -> Author**

- **Author -> Author_Nationality**

- **Book -> Author_Nationality** - This contains Transitive Dependency. If we know the book name, we can determine the nationality via the Author column.


![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/3NF-second.png "3NF second")

- **Author_ID  → Author**

- **Author → Author_Nationality**

- **Author_ID → Author_Nationality**: The nationality can be determined from the Author_ID through the Author attribute. We still have a transitive dependency.

![alt text](https://github.com/learning-dev/AMA_answers/blob/master/images/3NF-third.png "3NF third")