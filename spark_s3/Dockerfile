FROM gettyimages/spark:2.3.0-hadoop-2.8

# python 3 requirements
RUN apt-get update \
&& apt-get install -y wget \
&& apt-get install -y build-essential \
&& apt-get install -y python3-dev


# S3 and minio requirements
RUN cd /usr/spark-2.3.0/bin \
&& wget https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/2.8.3/hadoop-aws-2.8.3.jar \
&& wget https://repo1.maven.org/maven2/org/apache/httpcomponents/httpclient/4.5.3/httpclient-4.5.3.jar \
&& wget https://repo1.maven.org/maven2/joda-time/joda-time/2.9.9/joda-time-2.9.9.jar \
&& wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-core/1.11.524/aws-java-sdk-core-1.11.524.jar \
&& wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk/1.11.524/aws-java-sdk-1.11.524.jar \
&& wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-kms/1.11.524/aws-java-sdk-kms-1.11.524.jar \
&& wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-s3/1.11.524/aws-java-sdk-s3-1.11.524.jar

# python packages
RUN pip3 install notebook boto3 findspark
RUN pip3 install --upgrade pip setuptools wheel
RUN pip3 install  pandas

COPY ./notebooks /code
WORKDIR /code
