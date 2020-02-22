
1. Containers, Kubernetes and Kubernetes Engine
- Hybrid Service
- IaaS and PaaS

 ## Kubereetes
 - Kubectl
 - pod : smallest deployable component
 - service
 	- grouping pods together
	- and provinding a set of endpoints for them
 	- network loadbalancers 
	- provide the stability of IP
- rolling update for version update

 ## Anthos: Mutli-cloud system
 - Containerized Microservices Applications
 - distributed systems
 - GKE
 - On prem
 - Anthos Service Mesh communicates Cloud Interconnect with Istio Open Source
 - Anthos Config MAnagememt

2. App Engine
- PaaS
- Mostly Web Applications

  1. Standard Environment
  - Low utilisation with no harge
  - SDKs
  - Binary: runtime provided by google
  - Restrictions with sandbox
  - Scale and manage
  - Can't write to local file system
  - 60 s timeout
  - no arbitrary 3rd party app
  - less access to infra
  - Language support Java, py, Go, Php

  2. Flexible Environment
  - Specify the container
  - Compute engines
  - backward compatible updates on OS
  - Data Stroe

  3. Cloud Endpoints and Apigee Edge
  - Simple versioned API
  - Clean well defined Interface
  - API management Tools:
	  - CLoud Endpoints:
		  - consumed Other developers
		  - which end users is using the call
	  - Apigee Edge:
		  - SOftware service to different companies
		  - Taking apart legacy application
	  
3. Development in the Cloud:
	- Git Repo:
		- Cloud Source Repo
	- Cloud Functions
		- No run time binaries

	1. Deployment: infrastructure as a code:
		- Deployment Manager:
			- .yaml template
	 
	2. Monitoring: Proactive instrumentation:
		- Stackdriver
			- Logging 
			- Monitoring 
			- Debugging
			- Trace
			- Profiler

4. Google Cloud Big Data Platform
	- Fully managed and scalable
	- Dataproc:
		- Map Reduce
		- Hadoop, spark, hive, Pig
		- Auto scale
		- Monitor Through Stack Driver
		- Preemptible Instances
	- Dataflow:
		- Real time
		- unpredictable size
		- ETL
		- Batch, Streaming
		- Managed Pipelines
	- Bigquery:
		- hundreds of TBs
		- Adhoc Analytics
		- No infrastructure to manage
		- Pay as you go
		- Query and Data storage price seperate
	- Pub/Sub:
		- Messaging service
		- Scalable
		- Publisher/Subscribers
		- Decoupling system
		- At least once delivery
		- On demand scalability
		- Push or pull basis
	- Cloud Datalab:
		- Project Jupyter
		- 
6. Google Cloud Machine Learning Platform
	- Pretrained models and other models
	- Tensorflow
	- Cloud ML:
		- Managed
	- Structured and Unstructured data
	- Machine Learning APIs:
		- Cloud Vision API
		- Cloud Speech API
		- Cloud Natural Language API
		- Cloud Translation API
		- Cloud Video Intelligence API <Beta>


# Summary
Continuum between managed infra and dynamic infra
	- Compute Engine:
		- app on VM
	- Kubernetes:
		- app in containers
		- defining control
	- App Engine:
		- focus on code
		- no infra management
	- Cloud Functions:
		- no resources
		
Load balancing Options:
	- load balance inbound traffic
	- Global HTTP(S) load balancing 
		- Web application behind a single anycast IP to the entire Internet
		- regions around the world
		- GCP's Content Delivery Network
	- If your traffic isn't HTTP or HTTPS, 
	- Global TCP or SSL Proxy 
		- isn't HTTP or HTTPS, 
	- Regional:
		- For other ports or for UDP traffic
	- Regional Internal:
		- to load balance the internal tiers of a multi-tier application
		
Interconnect Options:
	- VPN:
		- on premise or Google VPC
	- Cloud Router:
		- inspite of router changes
	- Direct Peering
	- Carrier Peering
	- Dedicated Interconnect:
		- SLAs

Storage options:
	- Cloud Datastore:
		- structured + Transactional Data
	- Bigtable:
		- single keyed data
		- structure objects
	- Cloud Storage:
		- immutable binary objects
	- Cloud SQL/ Cloud Spanner:
		- full SQL support for OLTP
		- Cloud SQL: Terrabytes of capacity
		- Cloud Spanner: Petabytes + horizontal scalability
	- Bigquery: 
	  	- Interactive OLAP
		- Data Warehouse
Warm and Hot Data
Nearline and Coldline
