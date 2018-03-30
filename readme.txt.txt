Big data on cloud & spark using scala

-->
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

<configuration>
  <property>
    <name>fs.defaultFS</name>
    <value>hdfs://quickstart.cloudera:8020</value>
  </property>

  <!-- OOZIE proxy user setting -->
  <property>
    <name>hadoop.proxyuser.oozie.hosts</name>
    <value>*</value>
  </property>
  <property>
    <name>hadoop.proxyuser.oozie.groups</name>
    <value>*</value>
  </property>

  <!-- HTTPFS proxy user setting -->
  <property>
    <name>hadoop.proxyuser.httpfs.hosts</name>
    <value>*</value>
  </property>
  <property>
    <name>hadoop.proxyuser.httpfs.groups</name>
    <value>*</value>
  </property>

  <!-- Llama proxy user setting -->
  <property>
    <name>hadoop.proxyuser.llama.hosts</name>
    <value>*</value>
  </property>
  <property>
    <name>hadoop.proxyuser.llama.groups</name>
    <value>*</value>
  </property>

  <!-- Hue proxy user setting -->
  <property>
    <name>hadoop.proxyuser.hue.hosts</name>
    <value>*</value>
  </property>
  <property>
    <name>hadoop.proxyuser.hue.groups</name>
    <value>*</value>
  </property>

</configuration>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

<configuration>
  <property>
    <name>dfs.replication</name>
    <value>1</value>
  </property>
  <!-- Immediately exit safemode as soon as one DataNode checks in. 
       On a multi-node cluster, these configurations must be removed.  -->
  <property>
    <name>dfs.safemode.extension</name>
    <value>0</value>
  </property>
  <property>
     <name>dfs.safemode.min.datanodes</name>
     <value>1</value>
  </property>
  <property>
     <name>dfs.permissions.enabled</name>
     <value>false</value>
  </property>
  <property>
     <name>dfs.permissions</name>
     <value>false</value>
  </property>
  <property>
     <name>dfs.safemode.min.datanodes</name>
     <value>1</value>
  </property>
  <property>
     <name>dfs.webhdfs.enabled</name>
     <value>true</value>
  </property>
  <property>
     <name>hadoop.tmp.dir</name>
     <value>/var/lib/hadoop-hdfs/cache/${user.name}</value>
  </property>
  <property>
     <name>dfs.namenode.name.dir</name>
     <value>/var/lib/hadoop-hdfs/cache/${user.name}/dfs/name</value>
  </property>
  <property>
     <name>dfs.namenode.checkpoint.dir</name>
     <value>/var/lib/hadoop-hdfs/cache/${user.name}/dfs/namesecondary</value>
  </property>
  <property>
     <name>dfs.datanode.data.dir</name>
     <value>/var/lib/hadoop-hdfs/cache/${user.name}/dfs/data</value>
  </property>
  <property>
    <name>dfs.namenode.rpc-bind-host</name>
    <value>0.0.0.0</value>
  </property>

  <property>
    <name>dfs.namenode.servicerpc-address</name>
    <value>0.0.0.0:8022</value>
  </property>
  <property>
    <name>dfs.https.address</name>
    <value>0.0.0.0:50470</value>
  </property>
  <property>
    <name>dfs.namenode.http-address</name>
    <value>0.0.0.0:50070</value>
  </property>
  <property>
    <name>dfs.datanode.address</name>
    <value>0.0.0.0:50010</value>
  </property>
  <property>
    <name>dfs.datanode.ipc.address</name>
    <value>0.0.0.0:50020</value>
  </property>
  <property>
    <name>dfs.datanode.http.address</name>
    <value>0.0.0.0:50075</value>
  </property>
  <property>
    <name>dfs.datanode.https.address</name>
    <value>0.0.0.0:50475</value>
  </property>
  <property>
    <name>dfs.namenode.secondary.http-address</name>
    <value>0.0.0.0:50090</value>
  </property>
  <property>
    <name>dfs.namenode.secondary.https-address</name>
    <value>0.0.0.0:50495</value>
  </property>

  <!-- Impala configuration -->
  <property>
    <name>dfs.datanode.hdfs-blocks-metadata.enabled</name>
    <value>true</value>
  </property>
  <property>
    <name>dfs.client.file-block-storage-locations.timeout.millis</name>
    <value>10000</value>
  </property>
  <property>
    <name>dfs.client.read.shortcircuit</name>
    <value>true</value>
  </property>
  <property>
    <name>dfs.domain.socket.path</name>
    <value>/var/run/hadoop-hdfs/dn._PORT</value>
  </property>
</configuration>

//marped.xm

<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

<configuration>
  <property>
    <name>mapred.job.tracker</name>
    <value>localhost:8021</value>
  </property>

  <property>
    <name>mapreduce.framework.name</name>
    <value>yarn</value>
  </property>

  <property>
    <name>mapreduce.jobhistory.address</name>
    <value>0.0.0.0:10020</value>
  </property>
  <property>
    <name>mapreduce.jobhistory.webapp.address</name>
    <value>0.0.0.0:19888</value>
  </property>

  <property>
    <description>To set the value of tmp directory for map and reduce tasks.</description>
    <name>mapreduce.task.tmp.dir</name>
    <value>/var/lib/hadoop-mapreduce/cache/${user.name}/tasks</value>
  </property>

</configuration>

//Yarn
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

<configuration>
  <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
  </property>

  <property>
    <name>yarn.nodemanager.aux-services.mapreduce_shuffle.class</name>
    <value>org.apache.hadoop.mapred.ShuffleHandler</value>
  </property>

  <property>
    <name>yarn.log-aggregation-enable</name>
    <value>true</value>
  </property>

  <property>
    <name>yarn.dispatcher.exit-on-error</name>
    <value>true</value>
  </property>

  <property>
    <description>List of directories to store localized files in.</description>
    <name>yarn.nodemanager.local-dirs</name>
    <value>/var/lib/hadoop-yarn/cache/${user.name}/nm-local-dir</value>
  </property>

  <property>
    <description>Where to store container logs.</description>
    <name>yarn.nodemanager.log-dirs</name>
    <value>/var/log/hadoop-yarn/containers</value>
  </property>

  <property>
    <description>Where to aggregate logs to.</description>
    <name>yarn.nodemanager.remote-app-log-dir</name>
    <value>/var/log/hadoop-yarn/apps</value>
  </property>

  <property>
    <description>Classpath for typical applications.</description>
     <name>yarn.application.classpath</name>
     <value>
        $HADOOP_CONF_DIR,
        $HADOOP_COMMON_HOME/*,$HADOOP_COMMON_HOME/lib/*,
        $HADOOP_HDFS_HOME/*,$HADOOP_HDFS_HOME/lib/*,
        $HADOOP_MAPRED_HOME/*,$HADOOP_MAPRED_HOME/lib/*,
        $HADOOP_YARN_HOME/*,$HADOOP_YARN_HOME/lib/*
     </value>
  </property>
</configuration>
