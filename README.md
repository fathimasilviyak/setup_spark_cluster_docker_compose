# Setup an experimental Apache Spark cluster on top of Docker Compose

#### Steps involved:
<ul>
  <li>Install a Spark Master and Worker using Docker Compose</li>
  <li>Create a python script containing a spark job</li>
  <li>Submit the job to the cluster directly from python</li>
</ul>

#### Pre-requisites:
<ul>
  <li>A working docker installation</li>
  <li>Docker Compose</li>
  <li>The git command line tool</li>
  <li>A python development environment</li>
</ul>

 ## Install a Apache Spark cluster using Docker Compose
 
<ul>
    <li>Get the latest code:
    
    git clone https://github.com/big-data-europe/docker-spark.git
  </li>
  <li>Change the directory to the downloaded code

    cd docker-spark
  </li>
  <li>Start the cluster

    docker-compose up
    
  </li>
</ul>
After quite some time we should see the message:
Successfully registered with master spark://<server address>:7077
We have to keep this terminal running, as it is essential for further steps.

## Create code

Create a new python file called submit.py that containing a spark job


## Execute code / submit Spark job
<ul>
  <li>In the terminal, run the following commands to upgrade the pip installer to ensure you have the latest version by running the following commands
      
      rm -r ~/.cache/pip/selfcheck/
      pip3 install --upgrade pip
      pip install --upgrade distro-info
  </li>
  <li>Run the following commands in the terminal to download the spark environment
    
    wget https://archive.apache.org/dist/spark/spark-3.3.3/spark-3.3.3-bin-hadoop3.tgz && tar xf spark-3.3.3-bin-hadoop3.tgz && rm -rf spark-3.3.3-bin-hadoop3.tgz
  </li>
  <li>Run the following commands to set up the JAVA_HOME which should be installed in the environment and SPARK_HOME which is just downloaded
      
      export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
      export SPARK_HOME=/home/project/spark-3.3.3-bin-hadoop3
  </li>
  <li>Install the required packages to set up the spark environment.
      
      pip install pyspark
      python3 -m pip install findspark
  </li>
  <li>Execute the Python script
      
      python3 submit.py
  </li>
</ul>



We can now launch the Spark Master on port 8080. This will take you to the admin UI of the Spark master. We can see all registered workers (one in this case) and submitted jobs (also one in this case).
 

We can now launch the Spark Worker on 8081. 
