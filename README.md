# Real-time-Analytics
A project to analyze Meetup website's RSVPs real-time. 

Found out the topic trends and trending cities.

## Technical aspects
Zookeeper - Confuguration manager necessary for Apache Kafka, Spark, Mongo DB etc.<br>
Zookeeper started(if not already) using \n
bin/zookeeper-server-start.sh config/zookeeper.properties

Kafka started using the below command.
bin/kafka-server-start.sh config/server.properties

### Producer.py
Kafka producer program which will connect to web socket and sends to topic meetup.

### Consumer.py
Kafka consumer consumes messages from the topic meetup.

### spark_meetup.py
Spark application program to do some analysis
The above program submitted using 
bin/spark-submit --packages org.apache.spark:spark-streaming-kafka-0-8_2.11:2.0.1 spark_meetup.py localhost:2181 meetup

### visualization.py
Produces visualizations using matplotlib and plotly
