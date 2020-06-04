# SONY_Classification
This repository contains the ETL and Machine Algorithm for doing analysis on Spotify API's to recognise the best section of songs and make recommendation.

This is a hetrogeneous Repository comprises of 3 portions:
1. Authentication code that is written in NodeJs for fetching the authorization token.
2. Next portion is a ETL job design on Pentaho open source data integration platform which uses the authorization token obtained in last step to make calls and prepare data for the Machine Learning Algorithm.
3. Last but not the least is the Machine Learning Algo written in python for analysing the cleanses data fetched from API's

## Authentication Code and Making it work
Authentication is written in NodeJs and requires nodejs to be present in the host system. This README make this assumption that NodeJs is already installe on the host system.

Required libraries can be simply installed by running following command while the cursor is at the "Spotify Token Fetcher" directory.

```
npm install
```

After the installation is finished. One can simple hope in the directory "authorization_code" and run following command:

```
node app.js
```

This should start a NodeJs server and once the server is running successfully simply visit [Link](https://localhost:8888)

Login at the page and copy the Token. You would need this token to authenticate.

## Running The ETL Job (Optional)
In case you want to fetch data. Here Pentaho Data Integration tool is required to run ETL transformation. Again assumption has been made that Java(JDK and JRE) and Pentaho Data Integration Tools is already present on the host system.

Execution requires to open the transformation file "trans_neat_fetch.ktr" and modify following steps in the transformation with needed values:
1. In "CSV file input" step modify the path of Sample Track Ids/unpopular.csv
2. In "CSV file input 2" step modify the path of Sample Track Ids/popular.csv
3. in "Add Authentication" step modify the value of Authorization field with "Bearer <Token>"
4. In "Text file output 2" step modify the path where you want to output the file.

Execute the Job and wait for it to complete. Generally 15 to 20 minutes are required to fetch the data depending on connection bandwidth.

## Machine Learning Algo
Finally, open the "Sony_Classification.ipynb" file replace the input file path and run the algorithm. There is a input file already presend under the directory Pentaho ETL/Output. In case of using existing file ETL step is optional.
