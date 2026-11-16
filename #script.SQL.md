# 🗄️ ARVELL – SQL Data Preparation & Integration

## 1. Database Creation & Data Import

**SQL Server Management Studio ➔ New Query**

```sql
create database car;
```

Now, R-click ⏩ car ⏩ Tasks ⏩ Import Flat File...

Next.. Next.. Browse the excel data. Next.. & Finish.

Repeat the same steps for importing 5 excel .csv files.

**Done ✅**

All the excel files are successfully converted into SQL tables.

---

## 2. Create "master_table"

**Add ➡ New Query**

```sql
SELECT car.[Car_ID]

,[Brand] ,[Model] ,[Year] ,[Fuel_Type] ,[Transmission] ,[Color] ,[Owner_Type]

,[Mileage_kmpl] ,[Price_Lakh] ,[Provider] ,[Policy_Number] ,[Expiry_Date] ,[Status]

,[Owner_Name] ,[Contact] ,[City] ,[Purchase_Year] ,[Sale_Price_Lakh] ,[Sale_Date]

,[Buyer_Name] ,[Service_Type] ,[Service_Date] ,[Service_Cost] ,[Service_Center]

INTO Master_Car_Data

FROM Car

LEFT JOIN INSURANCE ON car.Car_ID = INSURANCE.Car_ID

LEFT JOIN OWNERS ON OWNERS.Car_ID = car.Car_ID

LEFT JOIN SALES ON SALES.Car_ID = car.Car_ID

LEFT JOIN SERVICE_HISTORY ON SERVICE_HISTORY.Car_ID = car.Car_ID
```

**-Select all & Execute-**

---

## 3. Connect SQL Server to Power BI

And then lastly..

**Open - Power BI ≫ Blank Report ≫ Get Data ≫**

SQL Server database | Connect |

Enter - Server & Database name | OK |

Select - Master_Car_Data | Load |
