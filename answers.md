# AMA

### what is foobar?

- Foo" and "bar" as metasyntactic variables were popularised by MIT and DEC, the first references are in work on LISP and PDP-1 and Project MAC from 1964 onwards.


- Both "foo" and "bar" (and even "baz") were well known in popular culture, especially from Smokey Stover and Pogo comics, which will have been read by many TMRC members.

Also, it seems likely the military FUBAR contributed to their popularity.

- FUBAR : Fucked/Fouled Up Beyond All Recoginition/Repair - Military Slang


### what is Database Sharding?

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