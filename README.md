# DBMS-PL

# Hotel & Room Database Project Report

## 1. Tables & Constraints

We worked with two tables: **HOTEL** and **ROOM**.

* **HOTEL** table contains:

  * H\_ID (Primary Key)
  * H\_NAME
  * H\_LOCATION

* **ROOM** table contains:

  * R\_ID (Primary Key)
  * H\_ID (Foreign Key referencing HOTEL.H\_ID)
  * RT\_ID (Room Type ID)
  * R\_NUMBER (Room number)

We applied the following constraints:

* Primary Key on HOTEL.H\_ID and ROOM.R\_ID
* Foreign Key constraint linking ROOM.H\_ID → HOTEL.H\_ID
  ![Image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/94e62e34782f7774dae360bfb54950d9cb8bb658/Screenshot%20(202).png)
  ![Image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/6953ecfc3bb12580aea101463cee408a4e96a384/Screenshot%20(203).png)

## 2. SQL Joins

We performed four types of joins to combine data from HOTEL and ROOM tables:

* **INNER JOIN** – Display only hotels that have rooms.
  ![image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/1e0a5c282fc3e6378f26ba216bfc541a78e9ba3a/Screenshot%20(204).png)
* **LEFT JOIN** – Display all hotels, including those with no rooms.
  ![image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/df001e79a89e7ab32e1df9b2c96d84f3f711740e/Screenshot%20(206).png)
* **RIGHT JOIN** – Display all rooms, including those not linked to any hotel.
  ![image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/9c6e90eb76dbc9cfdbedd207ae4e92b9bee61a9d/Screenshot%20(205).png)
* **FULL OUTER JOIN** – Combine all data from both tables, matching where possible.
  ![IMAGE ALT](https://github.com/Melissa-10-10/DBMS-PL/blob/5cb99858b517a97d18add6fb20102c7105b12230/Screenshot%20(207).png)


## 3. Index Creation

We created an index on ROOM.H\_ID to improve query performance:

```sql
CREATE INDEX idx_room_hotel ON ROOM(H_ID);
```

## 4. View Creation

We created a view for simplified access to hotel-room data:

![imagealt](https://github.com/Melissa-10-10/DBMS-PL/blob/6b1bf5246d420290b83301a35985801819093aed/Screenshot%20(211).png)

This view makes it easy to query hotel and room information together.

## 5. Simple Report

We generated a report showing the number of rooms in each hotel:

![image alt](https://github.com/Melissa-10-10/DBMS-PL/blob/98d84b547ddb32cc0bb4f20b9d258e27c574d1ea/Screenshot%20(212).png)

This query provides a clear summary of room distribution across hotels.

## 6. Results & Observations

* The joins allowed us to see how data is related between the HOTEL and ROOM tables.
* The index improved the speed of join queries.
* The view made querying hotel and room data much easier.
* The final report shows which hotels have the most rooms.


