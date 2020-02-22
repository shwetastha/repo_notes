# GKE Notes

 ## Installation
 - Install `kfctl`
	- Download the zip, unzip.
 - Use configuration to apply.
	- in github
	- `kfctl build -C -v ${CONFIG_URI}
	- generates the yaml file. => CONFIG_FILE
	- replace necessary things in the config file
	? rm- rf kustomize
	- `kfctl apply -V -f ${CONFIG_FILE}


 ## Kubeflow Fairing
 - Build, train and deploy ML models.
 - TrainJob
 - PredictionEndpoint
	- created serve point


 ## Hyperparameter Tuning (??)
 - Hyperparameter:parameters external to the model to control the training.
	- learning rate, batch size, epochs
 - Tuning: finds a set of hyperparameters that optimizes an objective function
	- find the optimal batch size and learning rate to maximize prediction accuravy.
 - Katib


# Spotify Presentation KubeCon- Nov 2019
- Terraform + Kustomize
- GCP Deployment CLI
	- kfctl -> Generate Config Files
	- update gcp config for shared VPC
	- update pipelines to use Cloud SQL and named Persistence Disks.
	- kfctl creates GCP resources and installs Kubeflow apps
	- <<add context in the terminal>>
- With Kustomize Deployment
	- kfctl generates Kustomize manifests
	- Overlays for customized deployment
	- kfctl apply deploys manifests

# TensorFLow Extended (TFX)
- 
