SQL Server Management Studio  ➔  New Query



create database car;



Now,  R-click  ⏩  car  ⏩  Tasks  ⏩  Import Flat File...

Next..  Next..  Browse the excel data.  Next..  \&  Finish.

Repeat  the  same  steps  for  importing  5 excel  .csv  files.



Done✅

all  the  excel  files  are  successfully  converted  into  SQL  tables.



To create  "master\_table"

Add ➡ New Query



SELECT  car.\[Car\_ID]

,\[Brand]  ,\[Model]  ,\[Year]  ,\[Fuel\_Type]  ,\[Transmission]  ,\[Color]  ,\[Owner\_Type]

,\[Mileage\_kmpl]  ,\[Price\_Lakh]  ,\[Provider]  ,\[Policy\_Number]  ,\[Expiry\_Date]  ,\[Status]

,\[Owner\_Name]  ,\[Contact]  ,\[City]  ,\[Purchase\_Year]  ,\[Sale\_Price\_Lakh]  ,\[Sale\_Date]

,\[Buyer\_Name]  ,\[Service\_Type]  ,\[Service\_Date]  ,\[Service\_Cost]  ,\[Service\_Center]



INTO  Master\_Car\_Data



FROM  Car

LEFT JOIN  INSURANCE  ON  car.Car\_ID  =  INSURANCE.Car\_ID

LEFT JOIN  OWNERS  ON  OWNERS.Car\_ID  =  car.Car\_ID

LEFT JOIN  SALES  ON  SALES.Car\_ID  =  car.Car\_ID

LEFT JOIN  SERVICE\_HISTORY  ON  SERVICE\_HISTORY.Car\_ID  =  car.Car\_ID



\-Select all  \&  Execute-



And  then  lastly..

Open - Power BI  ≫  Blank Report  ≫  Get Data  ≫

SQL Server database  | Connect |

Enter - Server \& Database name  | OK |

Select - Master\_Car\_Data  | Load | 

