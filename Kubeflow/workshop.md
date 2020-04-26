# [Full Day] KubeFlow + Keras/TensorFlow 2.0 + TF Extended (TFX) + Kubernetes + Airflow + Hyper-Parameter Tuning + Distributed Training

* Date: February 22, 2020
* Presenters: Antje Barth, Chris Fregley
6 hours!!!

**Agenda**

1. Create a Kubernetes cluster
2. Install KubeFlow, Airflow, TFX, and Jupyter
3. Setup ML Training Pipelines with KubeFlow and Airflow
4. Transform Data with TFX Transform
5. Validate Training Data with TFX Data Validation
6. Train Models with Jupyter, Keras/TensorFlow 2.0, and KubeFlow
7. Run a Notebook Directly on Kubernetes Cluster with KubeFlow Fairing
8. Analyze Models using TFX Model Analysis and Jupyter
9. Perform Hyper-Parameter Tuning with KubeFlow and Katib
10. Select the Best Model using KubeFlow Experiment Tracking
11. Reproduce Model Training with TFX Metadata Store
12. Deploy the Model to Production with TensorFlow Serving and Istio
13. Save and Download your Workspace

# AWS
Using AWS instances for the entire workshop.
Note: Google removed public datasets so TFX notebooks are not working.

Distributed Training with GPU instances.

Book: Data Science on AWS O'Reilly Book
https://www.datascienceonaws.com/

Github Repo: 
- has examples
- in progress
- kubeflow:
	- Workshop notebooks
	- Workshop contents
	
At the end of this workshop, you’ll be able to:


- Build end-to-end machine learning pipelines with AWS SageMaker and Kubeflow
- Demonstrate distributed training with Amazon SageMaker, Amazon EKS, and Kubeflow
- Identify when to consider distributed training
- Describe different approaches to distributed training
- Outline libraries and tools needed for distributing training workloads on large clusters
- Demonstrate code changes required to go from single-GPU to multi-GPU distributed training
- Apply these skills to create your own deep learning models and containers


ML training:
- Parallel run of multiple model training to get the best model training.
- Distributed training, run single model trainingto get the fastest training.

AWS:
- ML Services - Sagemaker
- Management - ECS and EKS
- Compute: EC2
- Image REgistry - ECR Elastic container Registry

Distributed training Approaches:
Asyc and sync
- Asynchronous: Parameter Server. propagating the info no repeat
- Synchronous: Ring all reduce. repeat the info.
- Horovod: framework. distributed deep learning.
- message passing interface from HPC community.

https://github.com/data-science-on-aws/kubeflow

AWS Management Console

Instructions: https://master.d2j834wqg8s4j0.amplifyapp.com/setup/portal.html


Steps:

1. Launch Amazon Sagemaker
	- creating Jupyter notebook
	- ml.t3.xlarge
	- volume 50GB EBS to download datasets.
2. In Jupyter, clone https://github.com/data-science-on-aws/kubeflow.git

# PART 1 - SINGLE NODE TRAINING WITH SAGEMAKER
- horovod
- training a TensorFlow-Keras model in a notebook on a single node

Problem: Converting a single CPU/GPU training script to a multi-node/distributed compatible training script

Frameworks: This workshop currently uses TensorFlow 1.14, Keras and Horovod 0.18.

Dataset: The CIFAR-10 consists of 60,000 32x32 images belonging to 10 different classes (6,000 images per class).
CIFAR-10 dataset includes:

40,000 images for training
10,000 images for validation
10,000 images for test

## Prepare Training Dataset
> cd ~/SageMaker/kubeflow/notebooks/
>
> # Activate the TensorFlow conda environment
> source activate tensorflow_p36
>
> # Download CIFAR10 dataset and convert it to TFRecords format
> python generate_cifar10_tfrecords.py --data-dir dataset
>
> export S3_BUCKET=sagemaker-$(aws configure get region)-$(aws sts get-caller-identity | jq -r '.Account')
echo "export S3_BUCKET=${S3_BUCKET}" | tee -a ~/.bash_profile
> 
> # Create a new S3 bucket and upload the dataset to it. 
> aws s3 mb s3://${S3_BUCKET}
>
> aws s3 sync dataset/ s3://${S3_BUCKET}/cifar10-dataset/
> 
> echo "Completed"

## Single CPU training on the local instance
cifar10-single-instance
? epoch = 1

## USING HOROVOD API FOR DISTRIBUTED TRAINING
cifar10-horovod
Note: a bit later, we will show a relatively new service called "FSx for Lustre" that sits on top of S3 to increase performance and provide POSIX file system semantics on S3 But you need a distributed file system either way to do distributed training

# PART 2 - DISTRIBUTED TRAINING WITH AMAZON SAGEMAKER
cifar10-sagemaker-distributed
- sagemaker python sdk
Note: re: S3:  SageMaker is just an execution engine.  You can pull from anywhere.  You would do that from your training script (ie. train.py) directly If you use S3, SageMaker can optimize the data loading using something called Pipe Mode summary:  you can pull from anywhere when using SageMaker, but S3 is heavily optimized Just as Google Cloud heavily optimizes their Google Cloud ML engine to retrieve from Google Cloud Storage

# PART 3 - DISTRIBUTED TRAINING WITH AMAZON EKS AND KUBEFLOW
- Create an EKS cluster.
> source ~/.bash_profile
> 
> eksctl create cluster \
>    --name ${AWS_CLUSTER_NAME} \
>    --version 1.14 \
>    --region ${AWS_REGION} \
>    --nodegroup-name cpu-nodes \
>    --node-type c5.xlarge \
>    --nodes 5 \
>    --node-volume-size 100 \
>    --node-zones us-west-2a \
>    --timeout=40m \
>    --zones=us-west-2a,us-west-2b,us-west-2c \
>    --alb-ingress-access \
>    --auto-kubeconfig
>
> echo "Completed"

- Enable FSx for Lustre access. Its a filesystem that helps access the s3 bucket. its a vpc and has a storage capacity of 1.2 TB.
- Install kubeflow using the kubeflow's aws yaml to geneerate the project and apply the changes. <<Similar to what I did for the GCP>>

## BUILD TRAINING CONTAINER IMAGE AND PUSH IT TO ECR
- logging into the ECR and building a docker container
- in the example shown the docker container just copies the python scripts to a folder.

## SUBMIT DISTRIBUTED TRAINING JOB
- in the example they actually apply specs/eks_tf_training_job-cpu.yaml file.
- In this yaml file it is just calling the python script: cifar10-multi-gpu-horovod-k8s.py
- the yaml file is a MPIJob that actually runs the python script with the necessary parameters.

#Kubeflow

## Kubeflow Fairig
- train inside of notebook and run it inside a cluster.
- TrainJob
- Prediction
- Serving
- using KFserving (default for kubeflow). Also there is TFXServing- 02_03_TFX_Serving.

## Kubeflow Pipeline
- ContainerOp
- Creating experiments


## TFJob / PytorchJob
- distributed training 
- kubeflow recognises the tfjob and pytorcjob
- running these through yaml
- using components to run reusable codes
- components basically is python scripts that have been compile to a reusable yaml.
  
## Metadata/ Artifact
- 05_00_Metadata_Tracking
- kfmd
- https://github.com/kubeflow/pipelines/blob/master/components/local/confusion_matrix/src/confusion_matrix.py
- https://github.com/kubeflow/examples/blob/master/financial_time_series/tensorflow_model/run_train.py

## HyperParameter Tuning
- 06_00_Optimize_Hyper_Parameter_Tuning
- Katib

## Neural Architecture Search /NAS
- Katib AutoML/ NAS Support

## TFLite
- 06_02_Optimize_TFLite
- save the model
- visualize the model with graph
- alternate run time much smaller than normal tensorflow
- Performance gain
- how much accuracy are you willing to loose to save on space.

## Privacy Differential
- privacy budget
- tensorflow privacy
- wrap gradientDescnetOptimizer with the differential privacy optimizer
- key is to finding the balance.



