# airflow_mini_1


In this project, you’ll use Apache Airflow to create a data pipeline to extract online stock market
data and deliver analytical results. You’ll use Yahoo Finance as the data source. Yahoo Finance
provides intra-day market price details down a one-minute interval. <br/>
<br/>
You’ll work with two stock symbols: AAPL and TSLA. The workflow should be scheduled to run
at 6 PM on every weekday (Mon - Fri), which functions as below: <br/>
- Download the daily price data with one minute interval for the two symbols. Each symbol
will have a separate task, Task1 (t1) and Task2 (t2), which run independently and in
parallel. <br/>
- Save both datasets into CSV files and load them into HDFS. Each symbol will have a
separate task, Task3 (t3) and Task4 (t4), which run independently and in parallel. <br/>
- Run your custom query on the downloaded dataset for both symbols, Task5 (t5). Before
this step executes, all previous tasks must complete. <br/>
- Use Celery Executor in Airflow to run the job. <br/>
