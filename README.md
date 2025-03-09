# Build your sample app package jar
git clone https://github.com/DevopsCloudStudy/spark-submit-eks-cluster-java.git
cd spark-submit-eks-cluster-java/spark-submit-eks-cluster
mvn clean install
cd target
cp spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar /root/spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar
# spark-submit-eks-cluster-java
#cd spark-3.5.2-bin-hadoop3
./bin/spark-submit --master local --deploy-mode client --jars /root/spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar \
  --driver-class-path /root/spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar \
  --conf spark.executor.extraClassPath=/root/spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar \
  --class com.cloudtechmasters.App /root/spark-submit-eks-cluster-0.0.1-SNAPSHOT-jar-with-dependencies.jar
