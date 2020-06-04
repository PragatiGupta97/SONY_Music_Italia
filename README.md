# SONY_Classification
This repository contains the ETL and Machine Algorithm for doing analysis on Spotify API's to recognise the best section of songs and make recommendation.

This is a hetrogeneous Repository comprises of 3 portions:
1. Authentication code that is written in NodeJs for fetching the authorization token.
2. Next portion is a ETL job design on Pentaho open source data integration platform which uses the authorization token obtained in last step to make calls and prepare data for the Machine Learning Algorithm.
3. Last but not the least is the Machine Learning Algo written in python for analysing the cleanses data fetched from API's

## Authentication Code and Making it work
Authentication is written in NodeJs and requires nodejs to be present in the host system. This README make this assumption that NodeJs is already installe on the host system.

Required libraries can be simply installed by running following command while the cursor is at the "Spotify Token Fetcher" directory.

npm install

After the installation is finished. One can simple hope in the directory "authorization_code" and run following command:

node app.js

This should start a NodeJs server and once the server is running successfully simply visit [Link](https://localhost:8888)

Login at the page and copy the Token. You would need this token to authenticate.

Code to classify the tracks
