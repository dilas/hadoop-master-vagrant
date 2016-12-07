# hadoop-master-vagrant
Hadoop Master Vagrant Machine

To run a Apache Spark example on cluster:

```
spark-submit --class org.apache.spark.examples.SparkPi --master yarn --deploy-mode cluster --driver-memory 1g --executor-memory 512m --executor-cores 1 /opt/spark/examples/jars/spark-examples*.jar 15
```

Or local:

```
spark-submit --class "SimpleApp" --master local[*] target/scala-2.11/simple-project_2.11-1.0.jar
```