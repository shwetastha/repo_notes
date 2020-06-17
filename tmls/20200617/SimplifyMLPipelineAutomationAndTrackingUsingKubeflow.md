# Simplify ML Pipeline Automation and Tracking using Kubeflow
Presenter: Yaron Haviv[https://medium.com/@yaronhaviv]

## Research to Production:
- ML Pipeline:
	- Ingest -> Prepare -> Train -> Validate -> Deploy
	- Micro services and codes for each components
- MLRun -> MLOps Automation
- Simple Production Ready Development Process:
	- Write and test functions locally
	- Add requirements run on the cluster
	- Build/run ML Pipeline
- MLRun -> Orchaestration + Provisions + Tracking
- MLFlow -> We need to code to get the metadata for tracking 

## Kubeflow
- Operators for ML frameworks
- /var/folders/dm/p1x98cgx7w567c2d8qyb46780000gp/T/TemporaryItems/\(A\ Document\ Being\ Saved\ By\ screencaptureui\ 11\)/Screen\ Shot\ 2020-06-17\ at\ 10.23.36\ AM.png 
- Using MLRun to logging artifacts with contexts
- Nuclio: Open Source Project on top of Kubeflow.
- MLRun handles all the artefact management while Kubeflow requires a lot pf boilerplating
- MLRun can also be used in local system and on any cloud.


## Resources:
- MLOps Live Webinar:https://www.youtube.com/playlist?list=PLH8M0UOY0uy4qzau2iAFunuT6cTMmTHvB
- MLRun Demos: https://github.com/mlrun/demos
- MLRun Functions: https://github.com/mlrun/functions
- 
