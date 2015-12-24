
pyspark config i2.8xlarge:
conf = (SparkConf().setAppName("hrishi").setMaster("yarn-client").set("spark.executor.memory", "30g")
       .set("spark.driver.memory", "30g") .set("spark.executor.instances", "25") .set("spark.executor.cores", "5")
       .set("spark.dynamicAllocation.enabled", "true") .set("spark.shuffle.service.enabled", "true")
       .set("spark.serializer", "org.apache.spark.serializer.KryoSerializer") .set("spark.default.parallelism","400"))
sc = SparkContext(conf=conf)
#conf.getAll()



PYSPARK_DRIVER_PYTHON=ipython PYSPARK_DRIVER_PYTHON_OPTS="notebook --no-browser --port=7777 \
--notebook-dir='/mnt/hrishikg/notebook/'" pyspark --packages com.databricks:spark-csv_2.11:1.3.0
