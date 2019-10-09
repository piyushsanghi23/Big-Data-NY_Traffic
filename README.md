# Cloud-HW-4

Hadoop MapReduce CSV Analysis

The assignment reads the csv data file from the path  /user/tatavag/nyc.data

To run the mapper.py and reducer.py scripts over the nyc-traffic.csv, use the below command

$ hadoop fs -cat  /user/tatavag/nyc.data | python mapper.py | sort | python reducer.py

# Command to run
- Make sure output file has a unique number appended to the end so it can create a new directory
```
hadoop jar /usr/hdp/current/hadoop-mapreduce-client/hadoop-streaming.jar -file /home/sanghiph/mapper.py -mapper /home/sanghiph/mapper.py -file /home/sanghiph/reducer.py -reducer /home/sanghiph/reducer.py -input /user/tatavag/nyc.data -output /tmp/piyush_hadoop/output_test
```

Here the data is located at /user/tatavag/nyc.data
and the output is located at /tmp/piyush_hadoop/output_test

# Command to get output
- Make sure output file has the same unique number appended to the end as the run you want output for
```hadoop fs -cat /tmp/piyush_hadoop/output_test/part-00000```

or 
Just use the below command

```hadoop fs -cat /tmp/piyush_hadoop/output_test/*'```
