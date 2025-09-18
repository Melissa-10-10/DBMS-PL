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
* **LEFT JOIN** – Display all hotels, including those with no rooms.
* **RIGHT JOIN** – Display all rooms, including those not linked to any hotel.
* **FULL OUTER JOIN** – Combine all data from both tables, matching where possible.

### Example Query (INNER JOIN):

```sql
SELECT r.R_ID, r.R_NUMBER, h.H_NAME, h.H_LOCATION
FROM ROOM r
INNER JOIN HOTEL h ON r.H_ID = h.H_ID;
```

## 3. Index Creation

We created an index on ROOM.H\_ID to improve query performance:

```sql
CREATE INDEX idx_room_hotel ON ROOM(H_ID);
```

## 4. View Creation

We created a view for simplified access to hotel-room data:

```sql
CREATE OR REPLACE VIEW HotelRoomView AS
SELECT h.H_ID, h.H_NAME, h.H_LOCATION, r.R_ID, r.R_NUMBER, r.RT_ID
FROM HOTEL h
LEFT JOIN ROOM r ON h.H_ID = r.H_ID;
```

This view makes it easy to query hotel and room information together.

## 5. Simple Report

We generated a report showing the number of rooms in each hotel:

```sql
SELECT h.H_NAME, COUNT(r.R_ID) AS Total_Rooms
FROM HOTEL h
LEFT JOIN ROOM r ON h.H_ID = r.H_ID
GROUP BY h.H_NAME;
```

This query provides a clear summary of room distribution across hotels.

## 6. Results & Observations

* The joins allowed us to see how data is related between the HOTEL and ROOM tables.
* The index improved the speed of join queries.
* The view made querying hotel and room data much easier.
* The final report shows which hotels have the most rooms.

---

📸 **Screenshots:**
(Add your SQL Developer screenshots here: table structures, join results, view results, and final report output.)
