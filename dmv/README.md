# DMV

### Introduction

A real-world dataset consisting of vehicle registration information in New York. Researches always use the following 11 columns with widely differing data types and domain sizes : 'Body Type', 'Color', 'County', 'Fuel Type', 'Record Type', 'Reg Valid Date', 'Registration Class', 'Revocation Indicator', 'Scofflaw Indicator', 'State', 'Suspension Indicator’.

### How to Get

1. Download the dataset：https://catalog.data.gov/dataset/vehicle-snowmobile-and-boat-registrations

   ```bash
   ➜ head -n 5 Vehicle__Snowmobile__and_Boat_Registrations.csv
   Record Type,VIN,Registration Class,City,State,Zip,County,Model Year,Make,Body Type,Fuel Type,Unladen Weight,Maximum Gross Weight,Passengers,Reg Valid Date,Reg Expiration Date,Color,Scofflaw Indicator,Suspension Indicator,Revocation Indicator
   BOAT,999999999999,BOT,HILTON,NY,14468,MONROE,1975,STARC,BOAT,GAS,,,,08/24/2022,07/31/2025,,N,N,N
   VEH,9999236,HIS,ROSLYN,NY,11576,NASSAU,1937,CHRY,4DSD,GAS,6300,,,05/07/2024,06/23/2025,BK,N,N,N
   TRL,9999,LTR,BETHEL PARK,PA,15102,OUT-OF-STATE,1980,CRCF,LTRL,NONE,,3000,,11/07/2024,12/31/2025,BR,N,N,N
   BOAT,999747,BOT,CORTLAND,NY,13045,CORTLAND,1971,STARC,BOAT,GAS,,,,03/08/2023,04/30/2026,,N,N,N
   ```

2. Date-type format conversion: The dataset contains two **DATE**-type attributes, "Reg Valid Date" and "Reg Expiration Date", in the CSV format of `%m/%d/%Y`. Before importing into the pg, you need to convert these two column formats to `%Y-%m-%d`.

3. Create table in pg：

   ```sql
   CREATE TABLE dmv (
       "Record Type" TEXT,
       "VIN" TEXT,
       "Registration Class" TEXT,
       "City" TEXT,
       "State" TEXT,
       "Zip" INT,
       "County" TEXT,
       "Model Year" INT,
       "Make" TEXT,
       "Body Type" TEXT,
       "Fuel Type" TEXT,
       "Unladen Weight" INT,
       "Maximum Gross Weight" INT,
       "Passengers" INT,
       "Reg Valid Date" DATE,
       "Reg Expiration Date" DATE,
       "Color" TEXT,
       "Scofflaw Indicator" TEXT,
       "Suspension Indicator" TEXT,
       "Revocation Indicator" TEXT
   );
   ```

4. Import the csv file into pg：

   ```sql
   \copy dmv FROM 'your_file.csv' WITH CSV HEADER DELIMITER ',' NULL ''
   ```

### **Used by Papers**

The **DMV dataset** has been used in various academic and industry research papers. Below are some examples:

1. [Deep Unsupervised Cardinality Estimation](https://arxiv.org/pdf/1905.04278)[VLDB 19]
2. [QuickSel: Quick Selectivity Learning with Mixture Models](https://dl.acm.org/doi/pdf/10.1145/3318464.3389727)[SIGMOD 20]
3. [FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation](https://arxiv.org/pdf/2011.09022)[VLDB 21]
4. [A Unified Deep Model of Learning from both Data and Queries for Cardinality Estimation](https://dl.acm.org/doi/abs/10.1145/3448016.3452830)[SIGMOD 21]
5. [Are We Ready For Learned Cardinality Estimation?](https://arxiv.org/pdf/2012.06743.pdf)[VLDB 21]

If you have used the **DMV  dataset** in your research, feel free to share your work to contribute to the community.