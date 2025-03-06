# Forest

### Introduction

The following is a brief introduction to the data, the raw data and a description of the detailed data set can be downloaded from the website  https://archive.ics.uci.edu/dataset/31/covertype

1. Number of instances (observations):  581,012
2. Number of Attributes: 12 measures, but 54 columns of data (10 quantitative variables, 4 binary wilderness areas and 40 binary soil type variables). **Cardinality estimation research usually uses only the first ten numerical columns.**

### How to Get

1. Download the dataset from the link above, and `gunzip covtype.data.gz` to get “covtype.data”.

   ```tex
   covtype.data.gz  covtype.info  old_covtype.info
   ```

2. Following other studies, we use only the first 10 columns of the Forest dataset.

   ```bash
   cut -d, -f1-10 covtype.data > covtype_10cols.csv
   ```

3. Create table in postgresql.

   ```sql
   CREATE TABLE forest (
       Elevation INTEGER,
       Aspect INTEGER,
       Slope INTEGER,
       Horizontal_Distance_To_Hydrology INTEGER,
       Vertical_Distance_To_Hydrology INTEGER,
       Horizontal_Distance_To_Roadways INTEGER,
       Hillshade_9am INTEGER,
       Hillshade_Noon INTEGER,
       Hillshade_3pm INTEGER,
       Horizontal_Distance_To_Fire_Points INTEGER
   );
   ```

4. Import the data into the table.

   ```sql
   COPY forest FROM '/absolute/path/to/covtype_10cols.csv' WITH CSV;
   ```



### **Used by Papers**

The **Forest dataset** has been used in various academic and industry research papers. Below are some examples:

1. [Lightweight and Accurate Cardinality Estimation by Neural Network Gaussian Process](https://dl.acm.org/doi/pdf/10.1145/3514221.3526156)[SIGMOD 22]
2. [Learned Cardinality Estimation: A Design Space Exploration and A Comparative Evaluation](https://dl.acm.org/doi/pdf/10.14778/3485450.3485459)[VLDB 22]
3. [MOSE: A Monotonic Selectivity Estimator Using  Learned CDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9540288)[TKDE 21]

If you have used the **Forest dataset** in your research, feel free to share your work to contribute to the community.