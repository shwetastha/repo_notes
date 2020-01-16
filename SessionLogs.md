
## Kind :
ACCESSED, CREATED, CREATION_FAILED, CREATION_BLOCKED

## Commands :
	gcloud beta dataproc clusters create dataproc-pipeline \
                        --region=us-east1 --zone=us-east1-b --bucket=dataproc-pipeline \
                        --properties=hive:hive.metastore.warehouse.dir=gs://dataproc-pipeline/hive-warehouse \
                        --master-machine-type=n1-standard-16 --num-masters=1 \
                        --scopes=https://www.googleapis.com/auth/bigquery,https://www.googleapis.com/auth/bigtable.admin.table,https://www.googleapis.com/auth/bigtable.data,https://www.googleapis.com/auth/cloud.useraccounts.readonly,https://www.googleapis.com/auth/devstorage.full_control,https://www.googleapis.com/auth/devstorage.read_write,https://www.googleapis.com/auth/logging.write \
                        --worker-machine-type=n1-standard-16 --num-workers=2

	gcloud compute instances delete-access-config dataproc-pipeline-m --zone us-east1-b --access-config-name "External NAT"
	gcloud compute instances delete-access-config dataproc-pipeline-w-0 --zone us-east1-b --access-config-name "External NAT"
	gcloud compute instances delete-access-config dataproc-pipeline-w-1 --zone us-east1-b --access-config-name "External NAT"
	gcloud compute instances add-access-config dataproc-pipeline-m --zone us-east1-b --access-config-name="ExernalPostgresPipeline" --address=35.243.231.88
	gcloud compute instances add-access-config dataproc-pipeline-w-0 --zone us-east1-b --access-config-name="ExernalPostgresPipeline" --address=35.196.184.254
	gcloud compute instances add-access-config dataproc-pipeline-w-1 --zone us-east1-b --access-config-name="ExernalPostgresPipeline" --address=35.231.163.122

## Test Sessions :
	gcloud compute instances delete-access-config test-session-m --zone us-east1-c --access-config-name "External NAT"
	gcloud compute instances delete-access-config test-session-w-0 --zone us-east1-c --access-config-name "External NAT"
	gcloud compute instances delete-access-config test-session-w-1 --zone us-east1-c --access-config-name "External NAT"
	gcloud compute instances add-access-config test-session-m --zone us-east1-c --access-config-name="ExernalPostgresPipeline" --address=35.243.231.88
	gcloud compute instances add-access-config test-session-w-0 --zone us-east1-c --access-config-name="ExernalPostgresPipeline" --address=35.196.184.254
	gcloud compute instances add-access-config test-session-w-1 --zone us-east1-c --access-config-name="ExernalPostgresPipeline" --address=35.231.163.122
	
## Submit Job
	gcloud dataproc jobs submit pyspark \
      --cluster  test-session --region us-east1 \
    pyspark-sessionlogs-pipeline.py \
      --properties spark.dynamicAllocation.enabled=true,spark.driver.maxResultSize=16g  \
      --jars=gs://dataproc-pgpull-poc/dataproc-tools/postgresql-42.2.7_latest.jar,gs://spark-lib/bigquery/spark-bigquery-latest.jar \
      --py-files=gs://dataproc-pipeline/pyspark-postgres-pipeline/pyspark_standard_pipeline.py,gs://dataproc-pipeline/pyspark-postgres-pipeline/pyspark_custom.py,gs://dataproc-pipeline/pyspark-postgres-pipeline/pyspark_custom_money.py \

