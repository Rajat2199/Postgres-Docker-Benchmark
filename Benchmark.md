## Postgres Benchmark

1. Create postgres docker
2. Initialize postgres with data to benchmark using the following command: 

     pgbench -h localhost -p 5432 -U postgres -i -s 100 mydb 
     
   ![](https://github.com/Rajat2199/Postgres-Docker-Benchmark/blob/main/Postgres_Initialise.png)
This will create sample database mydb and different tables inside the same.
Total tuples created: 1,00,00,000

If using Docker running on host network, use: 

      pgbench -h 127.0.0.1 -U postgres -i -s 100 mydb


3. Run the benchmark using the following command: 

     pgbench -h 127.0.0.1 -U postgres -c 10 -j 2 -T 60 mydb 


Parameters: 

- `c`: Number of clients
- `j`: Number of threads
- `T`: Duration of the test in seconds

Iterations:

    pgbench -h 127.0.0.1 -U postgres -c 10 -j 10 -t 10000 mydb
    pgbench -h 127.0.0.1 -U postgres -c 100 -j 10 -T 60 mydb
    pgbench -h 127.0.0.1 -U postgres -c 10 -j 2 -T 60 mydb  

## Benchmark Results

![](https://github.com/Rajat2199/Postgres-Docker-Benchmark/blob/main/Benchmark_results.png)


![](https://github.com/Rajat2199/Postgres-Docker-Benchmark/blob/main/Benchmark_results2.png)


![](https://github.com/Rajat2199/Postgres-Docker-Benchmark/blob/main/Benchmark_results3.png)
