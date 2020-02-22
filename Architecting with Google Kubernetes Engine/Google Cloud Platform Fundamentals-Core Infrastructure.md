# GCP Fundamentals: Core Infrastructure

## GCP Computing Architecture
- Infrastructure as a Service: IaaS
   - Compute Engine
- Hybrid: Kubernetes Engine
- Platform as a Service: PaaS
   - App Engine
- Serverless Logic: Cloud Function
- Managed Services

## Google Network
- Google provides user's request through edge network location for lowest latency.
- Regions and Zones: 
  - Multi-Region -> Region -> Zone
  - Europe -> Europe-west2 -> Europe-west2-a
  
## Identity Access Management [IAM]
- Who: Google Account, google group, service account, an entire G Suite or Cloud Identity Domain
- Can Do What: Primitive Roles, Predefined Roles and Custom Roles.
  - Broader to specific.
- On Which Resource

## Virtual Private Network [VPC]
- VPC have global scope.
- Use firewall rules to restrict access to instances.
- Create static routes to forward trafic to specific destinations.
- Subnets have regional scope.
- In custom VPC network, if the size of the subnet is increased then the IP addressed of the virtual machines already on the subnet might be affected.

### Compute Engine
- Offers managed virtual machines.
- Machine Type: how much memory and how many virtual CPUs
  - predefined or custom
  - Some of the GCP zones have GPUs.
- Persistent disks: Standard or SSD
- Boot image
  - VM startup scripts to configure VMs with secific softwares. 
- disk snapshots.
- Preemptible VM
  - to reduce cost.
  - only diff between preemptible VM and Compute engine
  - Compute engine will have the permission to terminate if it's resources are needed elsewhere.
- Most GCP customers start off with scaling out not scaling up. 

### Important VPC capabilities
- routing tables: forward traffic from one instance to another within the same network
  - without requiring the external ip addresses.
  - No need for provisioning: Router or firewall instance
  - global distributed firewall
  - Managed by Google as a 
- VPCs among mutiple VPCs with multiple Projects
  - VPC Peering
  - Shared VPCs
- Autoscale.
- Cloud laod balancers.
  - Global HTTP(S): cross regional load balancing for a web application
  - Global SSL Proxy: Secure sockets layer traffic not HTTPS
  - Global TCP Proxy: Specific port number and TCP type.
  - Regional: UDP traffic or on any port. GCP Region.
  - Regional Internal: Traffic inside the project.
- DNS Infrastructure. Cloud DNS Infrastructure.
- Interconnect Options
  - VPN
  - Direct Peering: Private connection
  - Carrier Peering
  - Dedicated Interconnect: for high availability and reliability. SLAs

## Cloud Storage
- Unique Key
  - Unique URL
- Scalable Service
- High durability and reliability
- Not a file system.
- Storage objects are immutable
- Data encryption:
  - at rest
  - in transit https
- organised into buckets 
- versioning
  
### Cloud Storage Interactions
- Multi-Regional & Regional
  - SLAs: 99%
  - High performance
- Nearline and Coldline
  - backup and achival storage
- Bring data
  - gsutil
  - Storage transfer service
  - transfer appliance (beta)

## Big Table
- Managed NoSQL Big data table.
- NoSQL schema.
- wide column database service
- single look up key
- persistent hash table
- Accessed using HBAse API.
- Scalability
- administration tasks
- encrypted
- IAM to control access
- BigTable Access Patterns
