# Apache Hadoop 2.7.2 Docker image

*Reference*: https://github.com/sequenceiq/hadoop-docker


# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t deepfinch/hadoop-ai-docker:2.7.2 .
```

# Start a container

In order to use the Docker image you have just build or pulled use:

**Make sure that SELinux is disabled on the host. If you are using boot2docker you don't need to do anything.**

```
docker run -it deepfinch/hadoop-ai-docker:2.7.2 /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.2.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```
