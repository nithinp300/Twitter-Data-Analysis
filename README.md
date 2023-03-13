# Twitter-Data-Analysis
Real-Time Twitter Analysis Application Using Apache Spark and AWS Ecosystem
## Goal:
A real-time analysis to explore the underlying topics and the sentiment for live tweets that are talking about AI and Machine Learning filtered by the hashtags #AI, #MachineLearning. With the sentiment analysis, we also catch a glimpse of the public attitudes towards this field. In the end, we will also build a dashboard for visualization.

## Python Packages:

Tweepy to create a stream and listen to the live tweets.\
TextBlob to do simple sentiment analysis on tweets.

## Data Processing Engine: Apache Spark
Used Spark’s machine learning library to train an LDA (Latent Dirichlet Allocation) model for topic modelling in a distributed system. I also used Spark to process the Streaming, for model scoring/inference.

## Cloud Platform: AWS

### AWS Services:

S3: Amazon Simple Storage Service\
Kinesis Data Streams: streaming service to collect and process large streams of data record in real time.\
Note: the Tweepy streaming will be the producer that will put data into the Kinesis Data Stream.

Kinesis Firehose: service to deliver real-time streaming data to destinations such as Amazon S3, Redshift, ElasticSearch, etc.\
Note: I used a Kinesis Firehose deliver stream as a consumer of the Kinesis Data Stream, and save the raw tweets into the S3 directly.

EMR: service that utilizes a hosted Hadoop framework running on the Amazon EC2 (computing instance) and Amazon S3.\
Note: I used EMR to run Spark for data processing and model training, in a distributed fashion.

Athena: a serverless, interactive query service to query data and analyze big data in Amazon S3 using standard SQL.\
Note: I used Athena to access the processed tweets that have been saved in S3.

QuickSight: a cloud-scale business intelligence (BI) service that you can use to deliver easy-to-understand insights.\
Note: I used QuickSight to connect to Athena to build a dashboard for visualization.
