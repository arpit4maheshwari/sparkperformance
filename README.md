# sparkperformance

Code for blog - https://ashkrit.blogspot.com/2018/09/anatomy-of-apache-spark-job.html


Sample Data used from https://www.kaggle.com/new-york-city/nyc-parking-tickets

How to Run

```
   spark-submit --master spark://host:port --conf spark.eventLog.enabled=true \
    --class sparkperformance.parking.ParkingTicketApplication \
    ../target/sparkperformance-1.0-SNAPSHOT.jar /data/nyc-parking-tickets  \
    --conf spark.executor.extraJavaOptions='-XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintGCTimeStamps'  \
    --conf spark.executor.extraJavaOptions='-XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintGCTimeStamps -XX:NewSize=400m' \
    --conf spark.memory.offHeap.enabled=true --conf spark.memory.offHeap.size=1000000  \
    --conf spark.serializer=org.apache.spark.serializer.KryoSerializer
```

Spark UI Blog

https://ashkrit.blogspot.com/2018/11/insights-from-spark-ui.html

```
  spark-submit --master local[*] --conf spark.eventLog.enabled=true \
  --class sparkperformance.parking.ParkingTicketIdGeneratorApplication \
  ./target/sparkperformance-1.0-SNAPSHOT.jar \
  /data/Users/ashkrit/Downloads/nyc-parking-tickets /tmp/nycdict
```
