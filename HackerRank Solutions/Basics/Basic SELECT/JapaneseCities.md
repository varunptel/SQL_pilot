

#### **Table Schema**
![CITY Table Schema](https://github.com/user-attachments/assets/0e975e33-8492-41bb-b092-0146f88819f5)

**1) Query all attributes of every Japanese city in the `CITY` table. The `COUNTRYCODE` for Japan is `JPN`.**
#### **Solution (MySQL)**
```sql
SELECT * FROM CITY
WHERE COUNTRYCODE = 'JPN';
```


**2) Query all columns for a city in CITY with the ID 1661.**
#### **Solution (MySQL)**
```sql
SELECT * FROM CITY
WHERE ID = 1661;
```

**3) Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.**
```sql
SELECT * FROM CITY
WHERE COUNTRYCODE = 'JPN';
```

**4) Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.**
```sql
SELECT NAME FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
