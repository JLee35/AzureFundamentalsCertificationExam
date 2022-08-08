# Azure Fundamentals (AZ:900) Exam Notes

## Skills measured
 - Cloud concepts (25-30%)
 - Azure architecture and services (35-40%)
 - Azure management and governance (30-35%)

 ## Resources
 Microsoft provides learning modules for each section covered on the exam:
  - [Azure Fundamentals Part 1: Describe core Azure concepts](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-cloud-concepts/)
 - [Azure Fundamentals Part 2: Describe core Azure services](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-core-azure-services/)
 - [Azure Fundamentals Part 3: Describe core solutions and management tools on Azure](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-core-solutions-management-tools-azure/)
 - [Azure Fundamentals Part 4: Describe general security and network security features](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-general-security-network-security-features/)
 - [Azure Fundamentals Part 5: Describe identity, governance, privacy, and compliance features](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-identity-governance-privacy-compliance-features/)
 - [Azure Fundamentals Part 6: Describe Microsoft Cost Management and service level agreements](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-azure-cost-management-service-level-agreements/)

 The purpose of this page is to combine the content from the learning modules listed above into one place.

<hr>
<hr>

## Part 1: Core Azure Concepts
### Covers:
- Benefits of cloud computing and how it can save you time and money
- Cloud concepts such as high availability, scalability, elasticity, agility, and disaster recovery
- Core Azure architecture components such as subscriptions, management groups, resources and resource groups
- Summary of geographic distribution concepts such as Azure regions, region pairs, and availability zones

<hr>
<hr>

## Part 2: Core Azure Services
### Covers:
- Services available in Azure including compute, network, storage, and database
- Virtualization services such as Azure VMs, Azure Container Instances, Azure Kubernetes Service, and Azure Virtual Desktop
- Azure db services such as Azure Cosmos DB, Azure SQL, Azure Database for MySQL, Azure Database for PostgresSQL, and Azure's big data and analysis services
- Azure networking resources such as Virtual Networks, VPN Gateways, and Azure ExpressRoute
- Azure storage services such as Azure Blob Storage, Azure Disk Storage, and Azure File Storage

<hr>

## Azure Storage account fundamentals
- Stores files, messages, tables and other types of information
- Used by infrastructure as a service virtual machines, and platform as a service cloud services
- Must first create an Azure Storage account to store your data objects
- Can create an Azure Storage account by using Azure portal, PowerShell, or the Azure CLI.

Note: Azure VMs use Azure Disk Storage to store virtual disks. However, you can't use Azure Disk Storage to store a disk outside of a virtual machine.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-storage-fundamentals/media/account-container-blob-4da0ac47.png">

A storage account provides a unique namespace for your Azure Storage data, that's accessible from anywhere in the world over HTTP or HTTPS. Data in this account is secure, highly available, durable, and massively scalable.

## Disk storage fundamentals
- Disk storage provides disks for Azure virtual machines
- Apps and services have access to these disks as needed
- Allows data to be persistently stored and accessed from an attached virtual hard disk
- Could be SSD or HDD depending on performance tiers

## Azure Blob storage fundamentals
- Object storage solution for the cloud
- Can store massive amounts of data, such as text or binary data
- Unstructured, no restrictions on the kinds of data it can hold
- Manage thousands of simultaneous uploads, video data, log files
- Can be reached from anywhere with an internet connection
- Not limited to common file formats

Ideal for:
- Serving images or documents directly to a browser
- Storing files for distributed access
- Streaming video and audio
- Storing data for backup and restore, disaster recovery, and archiving
- Storing data for analysis by an on-premises or Azure-hosted service
- Storing up to 8 TB of data for virtual machines

You can store blobs in containers for better organization.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-storage-fundamentals/media/account-container-blob-4da0ac47.png">

## Azure Files fundamentals
- Fully managed and accessible via the industry standard Server Message Block and Network File System (preview) protocol
- Can be mounted concurrently by cloud or on-premises deployments of Windows, Linux, and macOS
- Applications running in Azure VMs or cloud services can mount a file story share to access file data, just as a desktop application would mount a typical SMB share
- Any number of VMs or roles can mount and access the file storage simultaneously

Good for the following situations:
- Many on-premises applications use file shares
- Store configuration files on a file share and access them from multiple VMs
- Write data to a file share, and process or analyze the data later

Azure Files ensures the data is encrypted at rest, and the SMB protocol ensures the data is encrypted in transit. You share the file via a URL, and you can use Shared Access Signature (SAS) tokens to allow access to a private asset for a specific amount of time.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-storage-fundamentals/media/sas-storage-uri-037308fa.png">

## Understand Blob access tiers
Azure provides several access tiers, which you can use to balance your storage costs with your access needs:

- Hot access tier: Optimized for storing data that is access frequently (website images)
- Cool access tier: Optimized for storing data that in infrequently access and stored for at least 30 days
- Archive access tier: For data that is rarely access and stored for at least 180 but allows for flexible latency requirements

The following considerations apply to the different access tiers:
- Only the hot and cool access tiers can be set at the account level
- All tiers can be set at the blob level, during upload or after upload
- Cool access data can tolerate slightly lower availability but still requires high durability, retrieval latency, and throughput similar ot hot
- Archive storage stores data offline and is the cheapest, but highest cost to rehydrate and access data

## Knowledge check
1. What is the first step that you would take in order to share an image file as a blob in Azure Storage? -> Create an Azure Storage account
2. Which Azure Storage option is better for storing data for backup and restore, disaster recovery, and archiving? -> Azure Blob Storage

<hr>

## Explore Azure Cosmos DB
- Globally distributed, multi-model database service
- Can elastically and independently scale throughput and storage across any number of regions
- Provides fast, single-digit-millisecond data access using any of the popular APIs
- Provides comprehensive service level agreements for throughput, latency, availability, and consistency guarantees
- Supports schemaless data, 
- Stores data at the lowest level in atom-record-sequence (ARS) format, which is then abstracted and projected as an API
- Choose from SQL, MongoDB, Cassandra, Tables, and Gremlin

## Explore Azure SQL Database
- Relational database based on latest stable version of Microsoft SQL Server db engine
- High-performance, reliable, fully managed, secure
- Can be used to build data-driven applications and websites in the programming language of your choice without need to manage infrastructure

### Features
- Is a platform as a service (PaaS) db engine
- Handles most database-management functions (upgrading, patching, backups, monitoring) without user involvement
- Provides 99.99 percent availability
- Microsoft handles all updates to the SQL and operating system code
- Lets you process both relational and non-relational structures

### Migration
- Can migrate existing SQL Server databases with minimal downtime using Azure Database Migration Service

## Explore Azure database for MySQL
- Relational db based on MySQL Community Edition engine versions 5.6, 5.7, and 8.0
- 99.99 percent availability SLA
- Built-in security, fault tolerance and data protection at no additional cost
- Allows point-in-time restore to recover a server to an earlier state, as far back as 35 days

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-database-fundamentals/media/azure-db-for-mysql-conceptual-diagram-02e2a10a.png">

## Explore Azure Database for PostgreSQL
- Relational database based on community version of the open-source PostgreSQL database engine
- Built-in high availability, simple and flexible pricing, scale on demand, automatic backups for up to 35 days, enterprise-grade security

Available in two deployment options:

1. Single Server
- Built-in high availability with no additional cost (99.99 percent SLA)
- Predictable performance with pay-as-you-go pricing
- Vertical scale as needed, within seconds
- Monitoring and alerting
- Enterprise-grade security and compliance
- Protect sensitive data at rest and in motion
- Automatic backups for up to 35 days
2. Hyperscale (Citus)
- Horizontally scales queries across multiple machines by sharding
- Query engine parallelizes incoming queries across servers for faster responses
- For applications that require greater scale and performance, (100+ GB of data)
- Supports multi-tenant applications, real-time analytics

## Explore Azure SQL Managed Instance
- Provides broadest SQL Server engine capability with all benefits of a fully managed platform as a service
- 99.99% uptime SLA
- Automated backups and configurable backup retention period
- Similar to Azure SQL Database, but this provides options to available to Azure SQL Database (like Cryllic characters for collation)

### Migration
<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-database-fundamentals/media/migration-process-flow-small-a899c59c.png">

<hr>

## Explore big data and analytics
Microsoft Azure supports a broad range of technologies and services that provide big data and analytic solutions such as:
- Azure Synapse Analytics
- Azure HDInsight
- Azure Databricks
- Azure Data Lake Analytics

### Azure Synapse Analytics
- Formally known as Azure SQL Data Warehouse
- Limitless analytics service that brings together enterprise-data warehousing and big-data analytics
- Query data on your terms with using either serverless or provisioned resources at scale
- Unified experience for ingesting, preparing, managing, and serving data for immediate business intelligence and machine learning needs

### Azure HDInsight
- Fully managed, open source analytics service for enterprises
- Cloud service that makes it easier, faster, and more cost-effective to process massive amounts of data
- Can run popular open-source frameworks and create cluster types such as Apache Spark, Apache Hadoop, Apache Kafka, Apache HBase, Apache Storm, and Machine Learning Services
- Supports extraction, transformation, loading (ETL), data warehousing, machine learning, and IoT

### Azure Databricks
- Helps unlock insights from all your data nd build artificial intelligent solutions
- Supports Python, Scala, R, Java, and SQL as well as data science frameworks and libraries including TensorFlow, PyTorch, and scikit-learn

### Azure Data Lake Analytics
- On-demand analytics job service that simplifies big data
- Write queries to transform your data and extract insights
- Can handle jobs of any scale instantly for setting the dial for how much power you need
- Only pay for your job when it's running

## Knowledge check
1. Your development team is interested in writing Graph-based applications that take advantage of the Gremlin API. Which option would be ideal for that scenario? -> Azure Cosmos DB (supports SQL, MongoDB, Cassandra, Tables, and Gremlin APIs)
2. What is a good option for migrating a LAMP stack? -> Azure Database for MYSQL
3. What would be a good tool for analyzing millions of log entries? -> Azure Synapse Analytics (good for analyzing large volumes of data)

<hr>

## Azure Virtual Network Fundamentals
Azure virtual networks enable Azure resources, such as VMs, web apps, and databases, to communicate with each other. They are like extensions of your on-premises network with resources that link other Azure resources.

Provide the following key network capabilities:
- Isolation and segmentation -> Create multiple isolated virtual networks that you can control access to
- Internet communications -> Connect to Azure VM cia Azure CLI, RDP, Secure Shell
- Communicate between Azure resources -> Secure communication via virtual networks or service endpoints
- Communicate with on-premises resources -> Create network that spans both your local and cloud environments via *Point-to-site virtual private networks, Site-to-site virtual private networks, Azure ExpressRoute*
- Route network traffic -> Azure routes traffic between subnets controlled via *Route tabes and Border Gateway Protocol*
- Filter network traffic -> Filter traffic between subnets
- Connect virtual networks -> Link virtual networks together by using virtual network peering

### Isolation and segmentation
Azure virtual network allows you to create multiple isolated virtual networks. When you set up a virtual network, you define a private IP address space by using either public or private IP address ranges. The public IP range only exists within the virtual network and isn't internet routable. You can divide that IP address space into subnets and allocate part of the defined address space to each named subnet.

For name resolution, you can use the name resolution service that's built in to Azure. You can also configure the virtual network to use an internal or an external DNS server.

### Internet communications
A VM in Azure can connect to the internet by default. You can enable incoming connections from the internet by assigning a public IP address to the VM or by putting the VM behind a public load balancer. For VM management, you can connect via the Azure CLI, Remote Desktop Protocol, or Secure Shell.

### Communicate between Azure resources
You'll want to enable Azure resources to communicate securely with each other. You can do that in one of two ways:

Virtual networks Virtual networks can connect not only VMs but other Azure resources, such as the App Service Environment for Power Apps, Azure Kubernetes Service, and Azure virtual machine scale sets.
Service endpoints You can use service endpoints to connect to other Azure resource types, such as Azure SQL databases and storage accounts. This approach enables you to link multiple Azure resources to virtual networks to improve security and provide optimal routing between resources.

### Route network traffic
By default, Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet. You can also control routing and override those settings, as follows:

- Route tables: A route table allows you to define rules about how traffic should be directed. You can create custom route tables that control how packets are routed between subnets.
- Border Gateway Protocol: Border Gateway Protocol (BGP) works with Azure VPN gateways, Azure Route Server, or ExpressRoute to propagate on-premises BGP routes to Azure virtual networks.

### Filter network traffic
Azure virtual networks enable you to filter traffic between subnets by using the following approaches:

- Network security groups: A network security group is an Azure resource that can contain multiple inbound and outbound security rules. You can define these rules to allow or block traffic, based on factors such as source and destination IP address, port, and protocol.
- Network virtual appliances: A network virtual appliance is a specialized VM that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.

### Connect virtual networks
You can link virtual networks together by using virtual network peering. Peering enables resources in each virtual network to communicate with each other. These virtual networks can be in separate regions, which allows you to create a global interconnected network through Azure.

User-defined routes (UDR) are a significant update to Azure’s Virtual Networks that allows for greater control over network traffic flow. This method allows network administrators to control the routing tables between subnets within a VNet, as well as between VNets.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/local-or-remote-gateway-in-peered-virual-network-21106a38.png">

## Azure Virtual Network Settings
You can create and configure Azure virtual networks from the Azure portal, Azure PowerShell, Azure CLI, Azure Cloud Shell or an ARM template.

### Create a virtual network
When you create an Azure virtual network, you configure a number of basic settings. You'll have the option to configure advanced settings, such as multiple subnets, distributed denial of service (DDoS) protection, Bastion host, Azure firewall, service endpoints, and use of a NAT gateway.

- NAT gateway: A NAT gateway is a fully managed and highly resilient Network Address Translation (NAT) service. You can configure a subnet to use a static outbound IP address when accessing the internet.

- BastionHost: Service which provides a secure and seamless RDP/SSH connectivity to your virtual machines directly in the Azure portal over SSL.

- Network security group: Security rules that enable you to filter the type of network traffic that can flow in and out of virtual network subnets and network interfaces. You create the groups separately.

Virtual networks are powerful and highly configurable mechanisms for connecting entities in Azure. You can connect Azure resources to one another or to resources you have on-premises. You can isolate, filter, and route your network traffic. Azure allows you to increase security where you feel you need it.

## Azure VPN Gateway Fundamentals

VPNs use an encrypted tunnel within another network. They're typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public internet). Traffic is encrypted while traveling over the untrusted network to prevent eavesdropping or other attacks.

### VPN gateways
A VPN gateway is a type of virtual network gateway. Azure VPN Gateway instances are deployed in a dedicated subnet of the virtual network and enable the following connectivity:

- Connect on-premises datacenters to virtual networks through a site-to-site connection.
- Connect individual devices to virtual networks through a point-to-site connection.
- Connect virtual networks to other virtual networks through a network-to-network connection.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/vpngateway-site-to-site-connection-diagram-0e1e7db2.png">

All data transfer is encrypted inside a private tunnel as it crosses the internet. You can deploy only one VPN gateway in each virtual network, but you can use one gateway to connect to multiple locations, which includes other virtual networks or on-premises datacenters.

When you deploy a VPN gateway, you specify the VPN type: either policy-based or route-based. The main difference between these two types of VPNs is how traffic to be encrypted is specified. In Azure, both types of VPN gateways use a pre-shared key as the only method of authentication. Both types rely on Internet Key Exchange (IKE) in either version 1 or version 2 and Internet Protocol Security (IPSec). IKE is used to set up a security association (an agreement of the encryption) between two points. This association is then passed to IPSec suite, which encrypts and decrypts data packets encapsulated in the VPN tunnel.

### Policy-based VPNs
- Specifies statically the IP address of packets that should be encrypted through each tunnel.
- Evaluates every data packet against IP addresses to choose the tunnel where that packet will be sent through.
- Support for IKEv1 only
- Use of static routing, where combinations of address prefixes from both networks control how traffic is encrypted and decrypted.
- Policy-based VPNs must be used in specific scenarios that require them.

### Route-based VPNs
- Less cumbersome solution to defining which IP addresses are behind each tunnel. 
- IPSec tunnels are modeled as a network interface or virtual tunnel interface.
- IP routing decides which tunnel interface to use when sending each packet.
- Preferred connection method of on-premises devices.
- More resilient to topology changes such as creation of new subnets.

Use this if you need any of the following types of connectivity:
- Connection between virtual networks
- Point-to-site connections
- Multisite connections
- Coexistence with an Azure ExpressRoute gateway

Key features include:
- Supports IKEv2
- Uses wildcard traffic selectors
- Can use dynamic routing protocols.

### VPN gateway sizes
Capabilities are determined by the SKU or size that you deploy.

### Deploy VPN gateways
Before you can deploy a VPN gateway, you need some Azure and on-premises resources.

- Virtual network
- GatewaySubnet
- Public IP address
- Local network gateway
- Virtual network gateway
- Connection

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/resource-requirements-for-vpn-gateway-2518703e.png">

### Require on-premises resources
To connect your datacenter to a VPN gateway, you'll need these on-premises resources:

- A VPN device that supports policy-based or route-based VPN gateways
- A public-facing (internet-routable) IPv4 address

### High-availability scenarios
There are several ways to ensure you have a fault-tolerant configuration.

- Active/standby: Two instances where standby fills in when active goes down

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/active-standby-c4a3c14d.png">

- Active/active: Assign a unique public IP address to each instance, then create separate tunnels from the on-premises device to each IP address.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/dual-redundancy-d76100c9.png">

### ExpressRoute failover
- High-availability option but not immune to physical problems due to connectivity or outages.

### Zone-redundant gateways
Brings resiliency, scalability, and higher availability to virtual network gateways. Physically and logically separates gateways within a region while protecting on-premises network connectivity to Azure from zone-level failures.

## Azure ExpressRoute Fundamentals
- Lets you extend your on-premises networks into Microsoft cloud over private connection (Azure and Microsoft 365).
- Can be from any-to-any (IP VPN) network, point-to-point Ethernet network, or virtual cross-connection
- Connections don't go over the public internet.
- Offers more reliability, faster speeds, consistent latencies, and higher security than typical connections over the internet.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/azure-expressroute-overview-5520731d.png">

### Two main layers of the Open Systems Interconnection (OSI) model:
1. Layer 2 (L2): Data Link Layer which provides node-to-node communication between two nodes on the same network
2. Layer 3 (L3): Network Layer which provides addressing and routing between nodes on a multi-node network

### Features and benefits of ExpressRoute
- Layer 3 connectivity between your on-premises network and Microsoft cloud through a connectivity provider.
- Connectivity to Microsoft cloud across all regions in the geopolitical region.
- Global connectivity to Microsoft services across all regions with the ExpressRoute premium add-on.
- Dynamic routing between your network and Microsoft via Border Gateway Protocol.
- Built-in redundancy in every peering location for higher reliability.
- Connection uptime SLA.
- QoS support for Skype for Business.

### ExpressRoute connectivity models
Supports the following models that you can use to connect your on-premises network to the Microsoft cloud:

- CloudExchange colocation
- Point-to-point Ethernet connection
- Any-to-any connection
- Directly from ExpressRoute sites

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/azure-networking-fundamentals/media/azure-connectivity-models-4deabab1.png">

### Knowledge check

1. Tailwind Traders wants to create a secure communication tunnel between its branch offices. What technology **can't** be used? -> Implicit FTP over SSL
2. Tailwind Traders wants to use Azure ExpressRoute to connect its on-premises network to the Microsoft cloud. Which of the following choices isn't an ExpressRoute model that Tailwind Traders can use? -> Site-to-site virtual private network
3. Which of the following options can you use to link virtual networks? -> Virtual network peering
4. Which of the following options isn't a benefit of ExpressRoute? -> Encrypted network communication

<hr>
<hr>

## Part 3: Core Solutions and Management Tools
### Covers:
- Azure Artificial Intelligence services
- Software development process tools and services
- Cloud monitoring services
- Azure management tools
- Serverless computing technologies
- IoT services

<hr>

## IoT services

### Azure IoT Hub
- Managed service hosted in the cloud and acts as a central message hub for bi-directional communications between your IoT application and the devices it manages
- Can be used to build IoT solutions with reliable and secure communications between millions of IoT devices and a cloud-hosted solution back end
- You can connect virtually any device to your IoT hub
- Supports multiple messaging patterns, such as device-to-cloud telemetry, file upload from devices, and request-reply methods to control your devices in the cloud
- After an IoT hub receives a message from a device, it can route that message to other Azure services
- Allows for command and control, either manual or automated
- Helps maintain health of your solution by tracking events such as device creation, device failures, and device connections

### Azure IoT Central
- Builds on top of IoT Hub by adding a dashboard that allows you to connect, monitor, and manage your IoT devices
- Provides starter templates for common scenarios across various industries
- You can use the UI to control your devices remotely

### Azure Sphere
- Creates an end-to-end, highly secure IoT solution for customers that encompasses everything from the hardware to the operating system
- Has built-in communication and security features for internet-connected devices
- Includes hardware

Comes in three parts:
1. Azure Sphere micro-controller unit (MCU): responsible for processing the operating system and signals from the attached sensors
2. Customized Linux operating system (OS): handles communication with the security service and runs vendor's software
3. Azure Sphere Security Service (AS3): Makes sure the device has not been maliciously compromised via certificate-based authentication

## Decision Criteria
- If security is your main concern, use Azure Sphere
- If you only need to connect to your remote devices for telemetry and occasionally push updates, and you don't need any reporting capabilities, use Azure IoT Hub by itself
- If you want pre-built customizable UIs then you should use IoT Central

## Knowledge check
1. A company wants to build a new voting kiosk for sales to governments around the world. Which IoT technologies should the company choose to ensure the highest degree of security? -> Azure Sphere (best for security)
2. A company wants to quickly manage its individual IoT devices by using a web-based user interface. Which IoT technology should it choose? -> IoT Central (best for GUI stuff)
3. You want to send messages from the IoT device to the cloud and vice versa. Which IoT technology can send and receive messages? -> IoT Hub (base functionality)

<hr>

## Artificial Intelligence services

## Identify the product options
There are two basic approaches to AI
1. Deep learning: modeled on the neural network of the human mind, enabling it to discover, learn and grow through experience
2. Machine learning: a data science technique that using existing data to train a model, test it, and then apply the model to new data to forecast future behaviors, outcomes, and trends

### Azure product options
Three primary product offerings from Microsoft
1. Azure Machine Learning
2. Azure Cognitive Services
3. Azure Bot Services

### Azure Machine Learning
- Platform for making predictions
- Consists of tools and services that allow you to connect to data and train and test models to find one that will most accurately predict a future result
- After you've run experiments to test the model, you can deploy and use it in real time via a web API endpoint

You can:
- Create a process that defines how to obtain data, how to handle missing or bad data, how to divide dat into sets, and how to deliver that data to a training process
- Train and evaluate predictive models with tools familiar to data scientists
- Create pipelines that define where and when to run the compute-intensive experiments that are required to score the algorithms based on the training and test data
- Deploy the best-performing algorithm as an API to an endpoint so it can be consumed in real time by other applications

Choose this when you need complete control over the design and training of an algorithm using your own data.

### Azure Cognitive Services
- Provides prebuilt machine learning models that enable applications to see, hear, speak, understand, and even begin to reason.
- Use to solve general problems, such as analyzing text for emotional sentiment or analyzing images to recognize objects or faces
- Don't need special machine learning or data science knowledge to use these services
- Easy access via APIs
- Provides pretrained models

Can be divided into the following categories:
- Language services: Allow your apps to process natural language with prebuilt scripts, evaluate sentiment, and learn how to recognize what users want
- Speech services: Convert speech into text and text into natural-sounding speech or translate from one language to another
- Vision services: Add recognition and identification capabilities when analyzing pictures, videos, etc
- Decision services: Add personalized recommendations for each user that automatically improve each time they're used, moderate content to monitor and remove risky content, and detect abnormalities in your time series data

### Azure Bot Service
- Platform for creating virtual agents that understand and reply to questions just like a human
- Bit different than other options because it has a specific use case
- Creates a virtual agent that can intelligently communicate with humans
- Behind the scenes, the bot uses other Azure services, such as Azure Cognitive Services, to understand what their human counterparts are asking for
- Bots can be used to shift simple, repetitive tasks, such as taking a dinner reservation or gathering profile information.
- Users can interact with a bot using text, interactive cards, and speech

## Analyze the decision criteria
- Use Azure Bot Service when you need to create a virtual agent to interact with humans
- Use Azure Cognitive Services for general purpose tasks, such as performing speech to text
- Use Azure Cognitive Services Personalizer service to predict user behavior and provide relevant experiences as it identifies usage patterns.
- User Azure Machine Learning when you need to analyze and predict future outcomes and for maximum flexibility

## Knowledge check
1. You need to predict future behavior on previous actions. Which product option should you select as a candidate? -> Azure Machine Learning
2. You need to create a human-computer interface that uses natural language to answer customer questions. Which product option should you select as a candidate? -> Azure Bot Services
3. You need to identify the content of product images to automatically create alt tags for images formatted properly. Which product option is the best candidate? -> Azure Cognitive Services

<hr>

## Serverless computing technologies
Serverless computing is a term used to describe an execution environment that's set up and managed for you.

## Identify the product options
1. Azure Functions: Stateless code first solution that runs when a certain event is triggered (HTTP request, schedule, etc) without need of setting up or maintaining any infrastructure
2. Azure Logic Apps: Low-code/no-code development platform for automating and orchestrating business processes and workflows

## Knowledge check
1. You need to process messages from a queue, parse them by using some existing imperative login written in Java, and then send them to a third-party API. Which serverless option should you choose? -> Azure Functions (you can use existing code)
2. You want to orchestrate a workflow by using APIs from several well-known services. Which is the best option for this scenario? -> Azure Logic Aps (best for orchestrating work flows)
3. Your team has limited experience with writing custom code, but it sees tremendous value in automating several important business processes. Which of the following options is your team's best option? -> Azure Logic Apps (minimal code needed)

<hr>

## Software development process tools and services
There are three primary offerings, each of which is aimed at a specific audience and use case.

1. Azure DevOps Services -> for enterprise scale software development, contains repos, pipelines, wikis, boards, and artifacts
2. GitHub and GitHub Actions -> lightweight version of ADO with Kanban boards, actions (which are like pipelines), widely used and supported by open-source community, appropriate for teams and individuals
3. Azure DevTest Labs -> provides automated means of managing the process of building, setting up, and tearing down VMs.

- Need to automate the creation and management of a test environment -> use Azure DevTest Labs
- Building open-source software -> use GitHub
- Need high permission granularity -> use Azure DevOps
- Need sophisticated project management and reporting -> use Azure DevOps

## Knowledge check
1. Which of the following choices would not be used to automate a CI/CD process? -> Azure Boards
2. Which service could help you manage the VMs that your developers and testers need to ensure that your new app works across various operating systems? -> Azure DevTest Labs
3. Which service lacks features to assign individual developers tasks to work on? -> Azure Pipelines

<hr>

## Azure management tools
At a high level, there are two broad categories of management tools: visual tools and code-based tools.

- Azure portal: web-based user interface to view all the services you're using, create and configure services and view reports
- Azure mobile app: Mobile version of Azure portal allowing for monitoring health and status of resources, checking for alerts and running Azure CLI and PowerShell commands
- Azure PowerShell: execute cmdlets which call Azure's Rest API to perform management tasks
- Azure CLI: executable program for executing commands in Bash which call Azure Rest API to perform management tasks
- ARM templates: Azure Resource Manager templates describe the resources you want to use in a declarative JSON format which is verified before any code is executed to ensure correct functionality

### Selecting which tool to use
- Want a visual tool for one-off actions -> use Azure Portal
- Want a repeatable Windows-like tool for one-off actions -> Use Azure PowerShell
- Want a repeatable Linux-like tool for one-off actions -> Use Azure CLI
- Want to be able to monitor and triage while mobile -> User Azure mobile app
- Want to create many resources in parallel with dependencies -> Use ARM templates

## Knowledge check
1. As an administrator, you need to retrieve the IP address from a particular VM by using Bash. What tool should you use? -> Azure CLI
2. You're a developer who needs to set up your first VM to host a process that runs nightly. What tool should you use? -> Azure portal
3. What is the best infrastructure-as-code option for quickly and reliably setting up your entire cloud infrastructure declaratively? -> ARM templates

<hr>

## Cloud monitoring services
There are three primary Azure monitoring services:

1. Azure Advisor
2. Azure Monitor
3. Azure Service Health

### Azure Advisor
- Evaluates your Azure resources and makes recommendations to help improve reliability, security, performance, and reduce costs
- Designed to help you save time on cloud optimization
- Recommendation service includes suggested actions 
- Recommendations available via the Azure portal and the API

The recommendations are divided into five categories:
1. Reliability: ensure and improve the continuity of your business-critical applications
2. Security: detect threats and vulnerabilities that might lead to security breaches
3. Performance: improve the speed of your applications
4. Cost: optimize and reduce your overall Azure spending
5. Operational Excellence: achieve process and workflow efficiency, resource manageability, and develop best practices

### Azure Monitor
- Platform for collecting, analyzing, visualizing, and potentially taking action

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/monitoring-fundamentals/media/2-identify-product-options-01.png">

### Azure Service Health
- Provides personalized view of the health of Azure services, regions, and resources
- See [status.azure.com](https://status.azure.com) for major issues that broadly affect Azure customers
- Displays both major and smaller, localized issues that affect you
- After an outage, provides incident reports (root cause analyses)

Service Health helps you keep an eye on several event types:
- Service issues with Azure
- Planned maintenance
- Health advisories

## Selecting which tool to use
- Need an analysis of your deployed resources? -> Use Azure Advisor
- Need to keep tabs on Azure itself? -> Use Azure Service Health
- Need to measure custom custom events alongside other collected telemetry data? -> Use Azure Monitor
- Need to set up alerts for outages or when autoscaling is about to deploy new instances? -> Use Azure Monitor

## Knowledge check
1. You want to be alerted when new recommendations to improve your cloud environment are available. Which service will do this? -> Azure Advisor
2. Which service provides official outage root cause analyses (RCAs) for Azure incidents? -> Azure Service Health
3. Which service is a platform what powers Application Insights, monitoring for VMs, containers, and Kubernetes? -> Azure Monitor

<hr>
<hr>

## Part 4: General security and network security features
### Covers
- Azure Security Center
- Azure Sentinel
- Azure Key Vault
- Azure Dedicated Host

<hr>

## Protect against security threats by using Azure Security Center
Monitoring service that provides visibility of your security posture across all your services (on-prem and Azure)

Can:
- Monitor security settings across on-prem and cloud workloads
- Automatically apply required security settings to new resources as they come online
- Provide security recommendations based on current configs, resources, and networks
- Continuously monitor your resources and perform automatic security assessments to identify potential vulnerabilities before they can be exploited
- Use machine learning to detect and block malware from being installed on your VMs and other resources
- Detect and analyze potential inbound attacks and investigate threats
- Provide just-in-time access control for network ports

Example of what you might see in Azure Security Center:

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/protect-against-security-threats-azure/media/2-security-center-compliance-32866f57.png">

**Resource security hygiene** shows the health of services from a security perspective, with remedial action recommendations categorized as low, medium and high.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/protect-against-security-threats-azure/media/2-security-center-dashboard-4d9c56a4.png">

 **Secure score** is a measurement of an organization's security posture based on security controls, or groups of related security recommendations. Score is based on percentage of security controls that you satisfy. 

### Protect against threats
Security center includes advanced cloud defense capabilities for VMs, network security, and file integrity.

- **Just-in-time VM access** blocks traffic by default to specific network ports of VMs but allows traffic for a specific time when an admin requests and approves it
- **Adaptive application controls** allows for controlling with applications are allowed to run on its VMs.
- **Adaptive network hardening** monitors network traffic patterns for VMs and compares those to the company's current network security group (NSG) settings.
- **File integrity monitoring** allows for configuring and monitoring changes of important files on both Windows and Linux, registry settings, applications, etc.

### Respond to security alerts
Security Center is a centralized view of all its security alerts. From here you can dismiss false alerts, investigate further, remediate alerts manually, or use an automated response with a workflow automation.

<hr>

## Detect and respond to security threats by using Azure Sentinel
Azure Sentinel is Microsoft's cloud-based security information and event management (SIEM) system.

Azure Sentinel enables you to:
- **Collect cloud data at scale** across all users, devices, applications, and infrastructure both on-premises and from multiple clouds
- **Detect previously undetected threats** with comprehensive analytics and threat intelligence
- **Investigate threats with artificial intelligence** by examining suspicious activities at scale
- **Respond to incidents rapidly** using built-in orchestration and automation of common tasks

### Connect your data sources
Azure Sentinel supports a number of data sources, which it can analyze for security events.

- **Connect Microsoft solutions** like Microsoft Threat Protection solutions, Microsoft 365 solutions, Azure Active Directory, and Windows Defender Firewall
- **Connect other services and solutions** like AWS CloudTrail, Citrix Analytics, Sophos XG Firewall, VMware Carbon Black Cloud, and Okta SSO
- **Connect industry-standard data sources** like Common Event Format (CEF), Syslog, or REST API

## Detect threats
Use both built-in analytics and custom rules to detect threats.

**Built-in analytics** use templates designed by Microsoft's security team, which can be customized
**Custom analytics** are rules you crate to search for specific criteria in your environment

### Investigate and respond
When Azure Sentinel detects suspicious events, you can investigate alerts or incidents (group of related alerts) with an investigation graph.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/protect-against-security-threats-azure/media/3-investigate-incidents-54765923.png">

**Azure Workbooks** allows for automating responses to threats, by opening a ticket in a reporting system, sending Teams or Slack messages, or emails with block or ignore options for a specific IP.

<hr>

## Store and manage secrets by using Azure Key Vault
A centralized cloud service for storing an apps secrets in a single, central location.

It can:
- **Manage secrets** access tokens, passwords, certificates, API keys, and other secrets
- **Manage encryption keys** as a key management solution
- **Manage SSL/TLS certificates** provision, manage, and deploy your public ans private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for both your Azure resources and your internal resources
- **Store secrets backed by hardware security modules (HSMs)** which can be protected either by software or FIPS 140-2 Level 2 validated HSMs

<hr>

## Azure Dedicated Host
Provides dedicated physical servers to host your Azure VMs for Windows and Linux.

### Benefits
- Visibility into, and control over the server infrastructure that's running your Azure VMs
- Helps address compliance requirements by deploying your workloads on an isolated server
- Lets you choose the number of processors, server capabilities, VM series, and VM sizes within the same host

### Availability considerations for Dedicated Host
For high availability, you can provision multiple hosts in a host group, and deploy your VMs across this group. VMs on dedicated hosts can also take advantage of maintenance control. This feature enables you to control when regular maintenance updates occur, within a 35-day rolling window.

### Pricing considerations
You're charged per dedicated host, independent of how many VMs you deploy to it. The host price is based on the VM family, type (hardware size), and region.

<hr>

## Summary
- Azure Security Center provides visibility of your security posture across all your services, both on Azure and on-premises
- Azure Sentinel aggregates security data from many different sources, and provides additional capabilities for threat detection and response
- Azure Key Vault stores your application's secrets, such as passwords, encryption keys, and certificates, in a single, central location
- Azure Dedicated Host provides dedicated physical servers to host your Azure VMs for Windows and Linux

<hr>

## Secure network connectivity on Azure

### What is defense in depth?
The objective of defense in depth is to protect information and prevent it from being stolen by those who aren't authorized to access it.

### Layers of defense in depth

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/secure-network-connectivity-azure/media/2-defense-depth.png">

Role of each layer:
- Physical security protects hardware
- Identity and access layer controls access to infrastructure and change control
- Perimeter layer users DDoS protection to filter large-scale attacks before they can cause a denial of service for users
- Network layer limits communication between resources through segmentation and access controls
- Compute layer secures access to virtual machines
- Application layer helps that applications are secure and free from vulnerabilities 
- Data layer controls access to business and customer data that you need to protect

### Security posture
The common principals used to define a security posture are confidentiality, integrity, and availability, known collectively as CIA.

- **Confidentiality**: The principal of least privilege means restricting access to information only to individuals explicitly granted access, at only the level that they need to perform their work. This includes protection of user passwords, email content, and access levels to applications and underlying infrastructure.
- **Integrity**: Prevent unauthorized changes to information, at rest and in transit. This can be implemented via a one-way hashing algorithm.
- **Availability**: Ensure services are functioning and can be accessed only by authorized users.

<hr>

## Protect virtual networks by using Azure Firewall
Azure Firewall is a managed, cloud-based network security service that helps protect resources in your Azure virtual networks.

- Is stateful, which analyzes the complete context of a network connectivity, not just an individual package of network traffic, and has high-availability and unrestricted cloud scalability
- Provides a central location to create, enforce, and log application and network connectivity polices across subscriptions and virtual networks
- Uses a static public IP address for your virtual network resources, which enables outside firewalls to identify traffic coming form your virtual network
- Integrated with Azure Monitor to enable logging and analytics

Features:
- Built-in high availability
- Unrestricted cloud scalability
- Inbound and outbound filtering rules
- Inbound Destination Network Address Translation (DNAT) support
- Azure Monitor logging

### Configuration
With Azure Firewall, you can configure:
- Application rules that define fully qualified domain names (FQDNs) that can be accessed from a subnet
- Network rules that define source address, protocol, destination port, and destination address
- Network Address Translation (NAT) rules that define destination IP addresses and ports to translate inbound requests

Azure Application Gateway also provides a firewall that's called the web application firewall (WAF). WAF provides centralized, inbound protection for your web applications against common exploits and vulnerabilities.

<hr>

## Protect from DDoS attacks by using Azure DDoS Protection
Azure DDos Protection (Standard) helps protect your Azure resources from DDoS attacks.

- Identifies the attacker's attempt to overwhelm the network and blocks further traffic from them, makes sure they don't reach your resources
- Legitimate traffic from customers still flows without any interruption
- Can also help you manage your cloud consumption

### Service tiers available to DDoS Protection
- **Basic**: automatically enabled for free as part of your Azure subscription with always-on traffic monitoring
- **Standard**: provides additional mitigation capabilities that are tuned specifically to Azure Virtual Network resources

### What kinds of attacks can DDoS Protection help prevent?
The standard service tier can help prevent:
- Volumetric attacks
- Protocol attacks
-Resource-layer (application-layer) attacks (only with application firewall)

<hr>

## Filter network traffic by using network security groups
A way to protect internal networks on Azure with network security groups (NSGs).

### What are network security groups?
- Enables you to filter network traffic to and from Azure resources within an Azure virtual network
- Like an internal firewall, containing multiple inbound and outbound security rules that enable you to filter traffic to and from resources by source and destination IP address, port, and protocol

### How do I specify NSG rules?
When you create a network security group, Azure creates a series of default rules to provide a baseline level of security. You can't remove default rules, but ou can override them by creating new rules with higher priorities.

<hr>

## Combine Azure services to create a complete network security solution
Here are some recommendations on how to combine Azure services to create a complete network security solution.

### Secure the perimeter layer
The perimeter layer is about protecting your organization's resources from network-based attacks. To do this:
- Use Azure DDoS Protection to filter large-scale attacks before they can cause a denial of service for users
- Use perimeter firewalls with Azure Firewall to identify and alert on malicious attacks against your network

### Secure the network layer
At this layer, the focus is on limiting network connectivity across all your resources to allow only what's required.

- Limit communication between resources by segmenting your network and configuring access controls
- Deny by default
- Restrict inbound internet access and limit outbound where appropriate
- Implement secure connectivity to on-premises networks

### Combine services
You can combine Azure networking and security services to manage your network security and provide increased layered protection. Here are two ways you can combine services:

- **Network security groups and Azure firewall**: Together these provide better defense-in-depth network security
- **Azure Application Gateway web application firewall and Azure Firewall**

## Knowledge check
1. An attacker can bring down your website by sending a large volume of network traffic to your servers. Which Azure service can help Tailwind Traders protect its App Service instance from this kind of attack? -> Azure DDoS Protection
2. What's the best way for Tailwind Trader to limit all outbound traffic from VMs to known hosts? -> Crate application rules in Azure Firewall
3. How can Tailwind Traders most easily implement a deny by default policy so that VMs can't connect to each other? -> Create a network security group rule that prevents access from another VM on the same network

<hr>
<hr>

## Part 4: Secure access to your applications by using Azure identity services

## Authorization vs Authentication
- Authentication: process of establishing the identity of the person or service that wants access
- Authorization: process of establishing what level of access an authenticated person or service has

<hr>

## Azure Active Directory
Provides identity services  that enable your users to sign in and access both Microsoft cloud applications and cloud applications that you develop.

### Azure AD vs Active Directory
Active Directory was built to be ran on-prem, Azure AD takes this functionality and applies it to the cloud.

### What services does Azure AD provide?
- **Authentication**: Verifies identity to access applications and resources as well as self-service support
- **Single sign-on**: Enables you to remember only one username and one password to access multiple applications
- **Application management**: Manage apps with features like Application Proxy, SaaS apps, and my My Apps portal
- **Device management**: Azure AD supports the registration of devices

<hr>

## Multifactor authentication and conditional access

### What's multifactor authentication?
Process where user is prompted during sign-in for an additional form of identification (fingerprint or code on their mobile phone).

Authenticates user by requiring two or more elements to fully authenticate.

- **Something the user knows** like an email address and password
- **Something the user has** like a code sent to a phone
- **Something the user is** like a biometric property such as fingerprint or facial recognition

### What's conditional access?
- A tool that Azure Active Directory uses to allow (or deny) access to a resource based on identity signals such as who the user is, where the user is, and what device the user is requesting accessing from
- This helps IT administrators empower users to be productive wherever and whenever and protect the organizations assets
- Provides a more granular MFA experience for users

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/secure-access-azure-identity-services/media/4-conditional-access-signal-decision-enforcement.png">

The use Conditional Access, you need an Azure AD Premium P1 or P2 license.

<hr>

## Knowledge check
1. How can the IT department ensure that employees at the company's retail stores can access company applications only from approved tablet devices? -> Conditional Access
2. How can the IT department use biometric properties, such as facial recognition, to enable delivery drivers to prove their identities? -> Multifactor authentication
3. How can the IT department reduce the number of times user must authenticate to access multiple applications? -> SSO

<hr>

## Build a cloud governance strategy on Azure


### Azure role-based access control
Azure provides built-in roles that describe common access rules for cloud resources. You can also define your own roles.

Role-based access control is applied to a scope, which is a resource or set of resources that this access applies to

Scopes include:
- A management group (a collection of multiple subscriptions)
- A single subscription
- A resource group
- A single resource

Kinds of users or accounts:
- Observers
- Users managing resources
- Admins
- Automated processes

User Azure RBAC when you need to:
- Allow one user to manage VMs in a subscription and other user to manage virtual networks
- Allow a database administrator group to manage SQL databases in a subscription
- Allow a user to manage all resources in a resource group, such as virtual machines, websites, and subnets
- Allow an application to access all resources in a resource group

### How is Azure RBAC enforced?
Azure RBAC is enforced on any action that's initiated against an Azure resource that passes through Azure Resource Manager. 

Azure RBAC doesn't enforce access permissions at the application or data level. Application security must be handled by your application.

RBAC uses an allow model. When you're assigned a role, RBAC allows you to perform certain actions, such as read, write, or delete.

### Who does Azure RBAC apply to?
You can apply RBAC to an individual or to a group. 

### How do I manage Azure RBAC permissions?
You can access permissions on the Access control (IAM) pane in the Azure portal. This pane shows who has access to what scope and what roles apply.

<hr>

## Prevent accidental changes by using resource locks
A resource lock prevents resources from being accidentally deleted or changed.

### How do I manage resource locks?
Azure portal, PowerShell, the Azure CLI, or from an Azure Resource Manager template.

To view, add, or delete locks in the Azure portal, got to the **Settings** section of any resource's **Locks** pane in the Azure portal.

### What levels of locking are available?
You can apply locks to a subscription, a resource group, or an individual resource. You can set the lock level to **CanNotDelete** or **ReadOnly**.

- **CanNotDelete**: means authorized people can still read and modify the resource, but they can't delete the resource without first removing the lock.
- **ReadOnly**: means authorized people can read a resource, but they can't delete or change the resource.

### How do I delete or change a locked resource?
To modify a locked resource, you must first remove the lock. Resource locks apply regardless of RBAC permissions. Even if you're an owner of the resource, you must still remove the lock before you can perform the blocked activity.

### Combine resource locks with Azure Blueprints
To make the protection process more robust, you can combine resource locks with Azure Blueprint, which enables you to define the set of standard Azure resources that your organization requires. For example, you can define a blueprint that specifies that a certain resource lock must exist. Azure Blueprints can automatically replace the resource lock if that lock is removed.

<hr>

## Organize your Azure resources by using tags
One way to organize related resources is to place them in their own subscriptions You can also use resource groups to manage related resources. Resource tags are another way to organize resources. Tags provide extra information, or metadata, about your resources. This metadata is useful for:
- **Resource management**: Tags enable you to locate and act on resources that are associated with specific workloads, environments, business units, and owners.
- **Cost management and optimization**: Tas enable you to group resources so that you can report on costs, allocate internal cost centers, track budgets, and forecast estimated cost
- **Operations management**: Enable you to group resources according to how critical their availability is to your business. This grouping helps you formulate SLAs.
- **Security**: Tags enable you to classify data by its security level, such as public or confidential.
- **Governance and regulatory compliance**: Identify resources that align with governance or regulatory compliance requirements. Tags can also be part of your standard enforcement efforts. for example, you might require that all resources be tagged with an owner or department name.
- **Workload optimization and automation**: Help you visualize all resources that participate in complex deployments.

### How do I manage resource tags?
You can add, modify, or delete resource tags through PowerShell, the Azure CLI, Azure Resource Manager templates, the REST API, or the Azure portal.

You can also manage tags by using Azure Policy. For example, you can apply tags to a resource group, but those tags aren't automatically applied to the resources within that resource group.You can use Azure Policy to ensure that a resource inherits the same tags as its parent resource group.

### Example tagging structure
A resource tag consists of a name and a value. You can assign one or more tags to each Azure resource.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/build-cloud-governance-strategy-azure/media/8-vm-tags-7c63fa8a.png">

Keep in mind that you don't need to enforce that a specific tag is present on all your resources. For example, you might decide that only mission-critical resources have the Impact tag. All non-tagged resources would then not be considered as mission-critical.

<hr>

## Control and audit your resources by using Azure Policy
Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit your resources. These policies enforce different rules across all of your resource configurations so that those configurations stay compliant with corporate standards.

### How does Azure Policy define policies?
Azure Policy enables you to define both individual policies and groups of related policies, known as initiatives. Azure Policy evaluates your resources and highlights resources that aren't compliant with the policies you've created. Azure Policy can also prevent noncompliant resources from being created.

Azure Policy comes with built-in policy and initiative definitions for Storage, Networking, Compute, Security Center, and Monitoring. For example, if you define a policy that allows only a certain SKU (stock-keeping unit) size for the VMs to be used in your environment, that policy is invoked when you create a new VM and whenever you resize existing VMs. Azure Policy also evaluates and monitors all current VMs in your environment.

Azure Policy can also automatically remediate noncompliant resources, like applying a tag if it was missing.

It also integrates with Azure DevOps by applying any continuous integration and delivery pipeline policies that pertain to the pre-deployment and post-deployment phases of your applications.

### Azure Policy in action
Implementing a policy in Azure Policy involves three tasks:

1. Create policy definition
2. Assign the definition to resources
3. Review the evaluation results

### Task 1. Create a policy definition
A policy definition expresses what to evaluate and what action to take. For example, you could prevent VMs from being deployed in certain Azure regions. You also could audit your storage accounts to verify that they only accept connections from allowed networks.

Every policy definition has conditions under which it's enforced. Here are some example policy definitions:
- **Allowed virtual machine SKUs**: This policy enables you to specify a set of VM SKUs that your organization can deploy.
- **Allowed locations**: This policy enables you to restrict the locations that your organization can specify when it deploys resources. Its effect is used to enforce your geographic compliance requirements.
- **MFA should be enabled on accounts with write permissions on your subscription**
- **CORS should not allow every resource to access your web applications**
- **System updates should be installed on your machines**

### Task 2. Assign the definition to resources
To implement your policy definitions, you assign definitions to resources. A policy assignment is a policy definition that takes place within a specific scope. This scope could be a management group (a collection of multiple subscriptions), a single subscription, or a resource group.

Policy assignments are inherited by all child resources within that scope. If a policy is applied to a resource group, that policy is applied to all resources within that resource group. You can exclude a subscope from the policy assignment if there are specific child resources you need to be exempt from the policy assignment.

### Task 3. Review the evaluation results
When a condition is evaluated against your existing resources, each resource is marked as compliant or noncompliant. You can review the noncompliant policy results and take any action that's needed. Policy evaluation happens about once per hour.

### What are Azure Policy initiatives?
An Azure Policy initiative is a way of grouping related policies together. The initiative definition contains all of the policy definitions to help track your compliance state for a larger goal.

For example, Azure Policy includes an initiative named **Enable Monitoring in Azure Security Center**. Its goal is to monitor all of the available security recommendations for all Azure resource types in Azure Security Center.

Under this initiative, the following policy definitions are included:

- **Monitor unencrypted SQL Database in Security Center**: monitors for unencrypted SQL databases and servers
- **Monitor OS vulnerabilities in Security Center**: monitors servers that don't satisfy the configured OS vulnerability baseline
- **Monitor missing Endpoint Protection in Security Center**: monitors for servers that don't have an installed endpoint protection agent

The **Enable Monitoring in Azure Security Center** initiative contains over 100 separate policy definitions.

### How do I define an initiative?
You define initiatives by using the Azure portal or command-line tools. From the Azure portal, you can search the list of built-in initiatives that are built into Azure. You can also create your own custom policy definition.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/build-cloud-governance-strategy-azure/media/3-define-initiatives-a834dde7.png">

### How do I assign an initiative?
Like a policy assignment, an initiative assignment is an initiative definition that's assigned to a specific scope of a management group, a subscription, or a resource group.

Even if you have only a single policy, an initiative enables you to increase the number of policies over time. Because the associated initiative remains assigned, it's easier to add and remove policies without the need to change the policy assignment for your resources.

<hr>

## Govern multiple subscriptions by using Azure Blueprints
With Azure Blueprints you can define a repeatable set of governance tools and standard Azure resources that your organization requires. In this way, development teams can rapidly build and deploy new environments with the knowledge that they're building within organizational compliance with a set of built-in components that speed the development and deployment phases.

Azure Blueprints orchestrates the deployment of various resource templates and other artifacts, such as:
- Role assignments
- Policy assignments
- Azure Resource Manager templates
- Resource groups

### Azure Blueprints in action
Azure Blueprints can be used to scale your governance practices throughout the organization.

Implementing a blueprint in Azure Blueprint involves these three steps:
1. Create an Azure blueprint
2. Assign the blueprint
3. Track the blueprint assignments

With Azure Blueprints, the relationship between the blueprint definition (what should be deployed) and the blueprint assignment (what was deployed) is preserved. In other words, Azure creates a record that associates a resource with the blueprint that defines it. This connection helps you track and audit your deployments. Blueprints are also versioned, which enables you to track and comment on changes to your blueprint.

### What are blueprint artifacts?
Each component in the blueprint is known as an artifact.

It is possible for artifacts to have no additional parameters (configurations). An example is the **Deploy threat detection on SQL servers** policy, which requires no additional configuration.

Artifacts can also contain one or more parameters that you can configure. The following screenshot shows the **Allowed locations** policy. This policy includes a parameter that specifies the allowed locations.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/build-cloud-governance-strategy-azure/media/10-allowed-locations-d139a119.png">

You can specify a parameter's value when you create the blueprint definition or when you assign the blueprint definition to a scope. In this way, you can maintain one standard blueprint but have the flexibility to specify the relevant configuration parameters at each scope where the definition is assigned.

<hr>

## Accelerate your cloud adoption journey by using the Cloud Adoption Framework for Azure
The Cloud Adoption Framework for Azure provides you with proven guidance to help with your cloud adoption journey. The Cloud Adoption Framework helps you create and implement the business and technology strategies needed to succeed in the cloud.

The Cloud Adoption Framework consists of tools, documentation, and proven practices. The Cloud Adoption Framework includes these stages:

1. Define your strategy
2. Make a plan
3. Ready your organization
4. Adopt the cloud
5. Govern and manage your cloud environments

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/build-cloud-governance-strategy-azure/media/2-framework-stages-9b54ccbe.png">

### Define your strategy
Here, you answer why you're moving to the cloud and what you want to get out of cloud migration. Do you need to scale to meet demand and reach new markets? Will it reduce costs or increase business agility? When you define your cloud business strategy, you should understand cloud economics and consider business impact, turnaround time, global reach, performance, and more.

Here are the steps in this stage:

1. **Define and document your motivations**: Meeting with stakeholders and leadership can help you answer why you're moving to the cloud
2. **Document business outcomes**: Meet with leadership from your finance, marketing, sales, and HR groups to help you document your goals
3. **Evaluate financial considerations**: Measure objectives and identify the return expected from a specific investment
4. **Understand technical considerations**: Evaluate those technical considerations through the selection and completion of your first technical project


### Make a plan
Here you build a plan that maps your aspirational goals to specific actions. A good plan helps ensure that your efforts map to the desired business outcomes.

Here are the steps in this stage:

1. **Digital estate**: Create an inventory of existing digital assets and workloads that you plan to migrate to the cloud
2. **Initial organizational alignment**: Ensure that the right people are involved in your migration efforts, both from a technical standpoint as well as from a cloud governance standpoint
3. **Skills readiness plan**: Build a plan that helps individuals build the skills they need to operate in the cloud
4. **Cloud adoption plan**: Build a comprehensive plan that brings together the development, operations, and business teams toward a shared cloud adoption goal

### Ready your organization
Here, you create a landing zone, or an environment in the cloud to begin hosting your workloads.

Here are the steps in this stage:

1. **Azure setup guide**: Review the Azure setup guide to become familiar with the tools and approaches you need to use to create a landing zone
2. **Azure landing zone**: Begin to build out the Azure subscriptions that support each of the major areas of your business. A landing zone includes cloud infrastructure as well as governance, accounting, and security capabilities
3. **Expand the landing zone**: Refine your landing zone to ensure that it meets your operations, governance, and security needs
4. **Best practices**: Start with recommended and proven practices to help ensure that your cloud migration efforts are scalable and maintainable

### Adopt the cloud
Here, you begin to migrate your applications to the cloud. Along the way, you might find ways to modernize your applications and build innovative solutions that use cloud services.

The Cloud Adoption Framework breaks this stage into two parts: migrate and innovate.

**Migrate**: Here are the steps in the migrate part of this stage.

1. **Migrate your first workload**: Use the Azure migration guide to deploy your first project to the cloud
2. ***Migration scenarios**: Use additional in-depth guides to explore more complex migration scenarios
3. **Best practices**: Check in with the Azure cloud migration best practices checklist to verify that you're following recommended practices
4. **Process improvements**: Identify ways to make the migration process scale with requiring less effort

**Innovate**: Here are the steps in the innovate part of this stage.

1. **Business value consensus**: Verify that investments in new innovations add value to the business and meet customer needs
2. **Azure innovation guide**: Use this guide to accelerate development and build a MVP for your idea
3. **Best practices**: Verify that your progress maps to recommended practices before you move forward
4. **Feedback loops**: Check in frequently with your customers to verify that you're building what they need

### Govern and manage your cloud environments
Here you begin to form your cloud governance and cloud management strategies. As the cloud estate changes over time, so do cloud governance processes and polices. You need to create resilient solutions that are constantly optimized.

**Govern**: Here are the steps in the govern part of this stage.

1. **Methodology**: Consider your end state solution. Then define a methodology that incrementally takes you from your first steps all the way to full cloud governance
2. **Benchmark**: Use the governance benchmark tool to assess your current state and future state to establish a vision for applying the framework
3. **Initial governance foundation**: Create an MVP that captures the first steps of your governance plan
4. **Improve the initial governance foundation**: Iteratively add governance controls that address tangible risks as you progress toward your end state solution

**Manage**: Here are the steps in the manage part of this stage.

1. **Establish a management baseline**: Define your minimum commitment to operations management. A management baseline is the minimum set of tools and processes that should be applied to every asset in the environment
2. **Define business commitments**: Document supported workloads to establish operational commitments with the business and agree on cloud management investments for each workload
3. **Expand the management baseline**: Apply recommended best practices to iterate on your initial management baseline
4. **Advanced operations and design principles**: For workloads that require a higher level of business commitment, perform a deeper architecture review to deliver on your resiliency and reliability commitments

<hr>

## Knowledge check
1. How can Tailwind Traders allow some user to control the VMs in each environment but prevent them from modifying networking and other resources in the same resource group or Azure subscription? -> Create a role assignment through Azure role-based access control (Azure RBAC)
2. Which is the best way for Tailwind Traders to ensure that the team deploys cost-effective virtual machine SKU sizes? -> Create a policy in Azure Policy that specifies the allowed SKU sizes
3. Which is likely the best way for Tailwind Traders to identify which billing department each Azure resource belongs to? -> Apply a tag to each resource that includes the associated billing department

<hr>

## Summary
There are several services and features in Azure to support these efforts:

- Azure role-based access control (Azure RBAC) enables you to create roles that define access permissions
- Resource locks prevent resources from being accidentally deleted or changed
- Resource tags provide extra information, or metadata, about your resources
- Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit your resources
- Azure Blueprints enables you to define a repeatable set of governance tools and standard Azure resources that your organization requires

<hr>
<hr>

## Examine privacy, compliance, and data protection standards on Azure

### Which compliance categories are available on Azure?
Here are some of the more popular compliance offerings that are available on Azure.

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/examine-privacy-compliance-data-protection-standards/media/2-compliance-matrix-383090ad.png">

<hr>

## Access the Microsoft Privacy Statement, the Online Services Terms, and the Data Protection Addendum

**Microsoft Privacy Statement**: explains what personal data Microsoft collects, how Microsoft uses it, and for what purposes. This covers all of Microsoft's services, websites, apps, software, servers, and devices.

**Online Services Terms**: a legal agreement between Microsoft and the customer. It details the obligations by both parties with respect to the processing and security of customer and personal data. It applies specifically to Microsoft's online services that you license through a subscription, including Azure, Dynamics 365, Office 365, and Bing Maps.

**Data Protection Addendum**: further defines the data processing and security terms for online services. These terms include:
- Compliance with laws
- Disclosure of processed data
- Data Security, which includes security practices and policies, data encryption, data access, customer responsibilities, and compliance with auditing
- Data transfer, retention, and deletion

To access the DPA:
1. Go to the Licensing Terms and Documentation
2. In the search bar, enter **DPA**
3. From the search results, local the link to the DPA in your preferred language. Alternatively, in the search bar that appears, enter your preferred language to filter the results

<hr>

## Explore the Trust Center
The Trust Center showcases Microsoft's principles for maintaining data integrity in the cloud and how Microsoft implements and supports security, privacy, compliance, and transparency in all Microsoft cloud products and services. The Trust Center is an important part of the Microsoft Trust Cloud Initiative and provides support for resources for the legal and compliance community.

The Trust Center provides:
- In-depth information about security, privacy, compliance offerings, policies, features, and practices across Microsoft cloud products
- Additional resources for each topic
- Links to the security, privacy, and compliance blogs and upcoming events

<hr>

## Access Azure compliance documentation
The Azure compliance documentation provides you with detailed documentation about legal and regulatory standards and compliance on Azure.

Here you find compliance offerings across these categories:
- Global
- US government
- Financial services
- Health
- Media and manufacturing
- Regional

There are also additional compliance resources, such as audit reports, privacy information, compliance implementations and mappings, and white papers and analyst reports. Country and region privacy and compliance guidelines are also included. Some resources might require you to be signed in to your cloud service to access them.

<hr>

## What is Azure Government?
Azure Government is a separate instance of the Microsoft Azure service. It addresses the security and compliance needs of US federal agencies, state and local governments, and their solution providers. Azure Government offers physical isolation from non-US government deployments and provides screened US personnel.

Azure Government services handle data that is subject to certain government regulations and requirements:
- Federal Risk and Authorization Management Program (FedRAMP)
- National Institute of Standards and Technology 
- International Traffic in Arms Regulations (ITAR)
- Internal Revenue Service (IRS) 1075
- Department of Defense (DoD) L4
- Criminal Justice Information Service (CJIS)

To provide the highest level of security and compliance, Azure Government uses physically isolated datacenters and networks located only in the U.S. Azure Government customers, such as US federal, state, and local government or their partners, and subject to validation of eligibility. Azure Government provides the broadest compliance and Level 5 DoD approval and is available in eight geographies.

<hr>

## What is Azure China 21Vianet?

It's a physically separated instance of cloud services located in China. Azure China 21Vianet is independently operated and transacted by Shanghai Blue Cloud Technology Co.

### Azure products and services available in China
The Azure services are based on the same Azure, Office 365, and Power BI technologies that make up the Microsoft global cloud service, with comparable service levels. Azure agreements and contracts in China, where applicable, are signed between customers and 21Vianet.

<hr>

## Knowledge check
1. Where can the team access details about the personal data Microsoft processes and how the company processes it, including Cortana? -> Microsoft Privacy Statement
2. Where can the legal team access information around how the Microsoft cloud helps them secure sensitive data and comply with applicable laws and regulations? -> Trust Center
3. Where can the IT department find reference blueprints that it can apply directly to its Azure subscriptions? -> Azure compliance documentation

<hr>

## Summary
- The Microsoft Privacy Statement provides trust in how Microsoft collects, protects, and uses customer data
- The Trust Center provides you with documentation about compliance standards and how Azure can support your business
- The Azure compliance documentation includes detailed information about legal and regulatory standards and compliance on Azure

<hr>
<hr>

## Part 6: Describe Microsoft Cost Management and service level agreements

## Compare costs by using the Total Cost of Ownership Calculator

### What's the TCO Calculator?
The TCO Calculator helps you estimate the cost savings of operating your solution on Azure over time compared to operating in your on-premises datacenter.

With the TCO Calculator, you'll enter the details of your on-premises workloads. Then you can review the suggested industry-average cost (which you can adjust) for related operational costs. These costs include electricity, network maintenance, and IT labor. 

<img width="517" alt="image" src="https://docs.microsoft.com/en-us/learn/azure-fundamentals/plan-manage-azure-costs/media/2-tco-report-bar-graphs.png">

Note: You don't need an Azure subscription to work with the TCO Calculator.

### How does the TCO Calculator work?
Working with the TCO Calculator involves three steps:

1. Define your workloads
2. Adjust assumptions
3. View the report

### Step 1: Define your workloads
First, you'll enter the specifications of your on-premises infrastructure into the TCO Calculator, based on these four categories:

- **Servers**: includes operating systems, virtualization methods, CPU cores, and memory (RAM)
- **Databases**: includes database types, server hardware, and Azure service you want to use, which includes the expected maximum concurrent user sign-ins
- **Storage**: includes storage type and capacity, which includes any backup or archive storage
- **Networking**: includes the amount of network bandwidth you current consume in your on-premises environment

### Step 2: Adjust assumptions
Next, you'll specify whether your current on-premises licenses are enrolled for Software Assurance, which can save you money by reusing those licenses on Azure. You'll also specify whether you need to replicate your storage to another Azure region for greater redundancy.

Then, you can see key operating cost assumptions across several different areas such as:
- Electricity price per kilowatt hour (KWh)
- Hourly pay rate for IT administration
- Network maintenance cost as a percentage of network hardware and software costs

## Step 3: View the report
Choose a timeframe between one and five years. The TCO Calculator generates a report that's based on the information you've entered.

<hr>

## Purchase Azure services

### What types of Azure subscriptions can I use?
Azure subscription provides you with access to Azure resources such as VMs, storage, and databases. The types of resources you use affect your monthly bill.

Azure offers both free and paid subscription options to fit your needs and requirements.

- **Free trial**: provides you with 12 months of popular free services, a credit to explore any Azure service for 30 days, and more than 25 services that are always free. Your Azure services are disabled when the trial ends or when your credit expires for paid products, unless you upgrade to a paid subscription.
- **Pay-as-you-go**: lets you pay for what you use by attaching a credit or debit card to your account. Organizations can apply for volume discounts and prepaid invoicing.
- **Member offers**: certain Microsoft products and services might provide you with credits for your Azure account, and reduced rates on Azure services.

### How do I purchase Azure services?

There are three main ways to purchase services on Azure. They are:

- **Through an Enterprise Agreement**: Larger customers, known as enterprise customers, can sign an Enterprise Agreement with Microsoft. This agreement commits them to spending a predetermined amount on Azure services over a period of three years. The service fee is typically paid annually. As an Enterprise Agreement customer, you'll receive the best customized pricing based on the kinds and amounts of services you plan on using.
- **Directly from the web**: Here, you can purchase Azure services directly from the Azure portal website and pay standard prices. You're billed monthly, either as a credit card payment or through an invoice. This purchasing method is known as Web Direct.
- **Through a Cloud Solution Provider**: A CSP is a Microsoft Partner that helps you build solutions on top of Azure. Your CSP bills you for your Azure usage at a price they determine.

### What factors affect cost?
The way you use resources, your subscription type, and pricing from third-party vendors are common factors. Let's take a quick look at each.

### Resource type
A number of factors influence the cost of Azure resources. They depend on the type of resource or how you customize it.

### Usage meters
When you provision a resource, Azure creates meters to track that resource's usage. Azure uses these meters to generate a usage record that's later used to help calculate your bill.

### Resource usage
In Azure, you're always charged based on what you use. However, just because you decommission a VM doesn't mean you aren't being charged for that VM. If the VM still exists it is potentially incurring storage and hardware costs.

### Does location or network traffic affect cost?
Certain locations cost more than others, and data transfer between regions also incurs a cost.

<hr>

## Knowledge check
1. Which is the best first step the team should take to compare the cost of running these environments on Azure versus in their datacenter? -> Run the Total Cost of Ownership Calculator
2. What's the best way to ensure that the development team doesn't provision too many virtual machines at the same time? -> Apply spending limits to the development team's Azure subscription
3. Which is the most efficient way for the testing team to save costs on virtual machines on weekends, when testers are not at work? -> Deallocate VMs when they're not in use
4. Resources in the Dev and Test environments are each paid for by different departments. What's the best way to categorize costs by department? -> Apply a tag to each virtual machine that identifies the appropriate billing department

<hr>

## What are service-level agreements (SLAs)?
A service-level agreement is a formal agreement between a service company and the customer. 

### What's in a typical SLA?
- **Introduction**: explains what to expect in the SLA, including its scope and how subscription renewals can affect the terms
- **General terms**: contains terms that are used throughout the SLA so that both parties (you and Microsoft) have a consistent vocabulary
- **SLA details**: defines the specific guarantees for the service, commonly measured as a percentage (99%, 99.9%, 99.95%, and 99.99%)

### What are service credits?
A service credit is the percentage of the fees you paid that are credited back to you according to the claim approval process.

An SLA describes how Microsoft responds when an Azure service fails to perform to its specification. For example, you might receive a discount on your Azure bill as compensation when a service fails to perform according to its SLA.

### What's the SLA for free services?
Free products don't typically have an SLA.

### How do I know when there's an outage?
Azure status provides a global view of the health of Azure services and regions. If you suspect there's an outage, this is often a good place to start your investigation.

### How can I request a service credit from Microsoft?
Typically, you need to file a claim with Microsoft to receive a service credit. If you purchase Azure services from a Cloud Solutions Provider (CSP) partner, your CSP typically manages the claims process.

Each SLA specifies the timeline by which you must submit your claim and when Microsoft processes your claim. For many services, you must submit your claim by the end of the calendar month following the month in which the incident occurred.

<hr>

## Design your application to meet your SLA
When you know the required SLA uptime for your application, then you design your application to meet your SLA uptime percentage.

### Identify your workloads
A workload is a distinct capability or task that's logically separated from other tasks, in terms of business logic and data storage requirements. Each workload defines a set of requirements for availability, scalability, data consistency, and disaster recovery.

### Combine SLAs to compute the composite SLA
The process of combining SLAs helps you compute the composite SLA for a set of services. Computing the composite SLA requires that you multiply the SLA of each individual service.

### What happens when your composite SLA doesn't meet your needs? 
You might have to customize options that fit your required SLA. 

<hr>

## Access preview services and preview features
As Azure develops new services, they go from the preview phase to being a generally available product integrated into Azure.

### What is the service lifecycle?
The service lifecycle defines how every Azure service is released for public use.

Every Azure service starts in the development phase. In this phase, the Azure team collects and defines its requirements, and begins to build the service.

Next, the service is released to the public preview phase. During this phase, the public can access and experiment with it and provide real-world feedback. 

After a new Azure service has been validated and tested, it's released to all customers as a production-ready service. This is know as general availability (GA).

## How can I stay updated on the latest announcements?
The Azure updates page provides information about the latest updates to Azure products, services, and features, and product roadmaps and announcements.

<hr>

## Summary
A service-level agreement (SLA) is the formal agreement between a service company and the customer. For Azure, this agreement defines the performance standards that Microsoft commits to for its customers.

When defining your SLA requirements, be sure to consider both your business needs and the time it takes to restore a component after a failure. Also consider how the use of preview services and preview features might affect your systems in production.

<hr>

## Review

1. Which Azure Active Directory (Azure AD) feature is used to provide access to resources based on organizational policies? -> Conditional Access
2. Single sign-on is what kind of method? -> An authentication method
3. What is the purpose for each service?

- Pricing calculator -> estimates workload costs
- TCO calculator -> estimates the cost savings by comparing datacenter costs to running the same workload on Azure
- Cost management -> helps control, analyze, and optimize workload costs

4. Which Azure service is a repeatable set of governance tools that helps development teams quickly build and create new environments while adhering to organizational compliance to speed up development and deployment? -> Azure Blueprints
5. Match the services on the left to the correct descriptions on the right.

- Infrastructure as a service (IaaS) -> Provides servers and virtual machines, storage, networks, and operating systems on a pay-as-you-go basis
- Platform as a service (PaaS) -> Provides a fully managed environment for developing, testing, delivering, and managing cloud-based applications
- Software as a service (SaaS) -> Provides hosting and management of an application and its underlying infrastructure, as well as any maintenance, upgrades, and security patching

6. Which cloud approach is used by organizations to take full advantage of on-premises technology investments and allows data and applications to be shared between two environments? -> Hybrid cloud
7. Which type of storage copies data to a secondary region from the primary region across multiple datacenters that are located many miles apart? -> Geo-redundant storage (GRS)
8. Which option is used to set the communication between on-premises VPN device and an Azure VPN gateway through an encrypted tunnel over the internet? -> Site-to-Site VPN
9. How do you organize resources in an Azure subscription? -> Resource groups
10. Which defense in depth layer users distributed denial of service (DDoS) protection? -> Perimeter layer
11. Which Azure serverless computing technology provides the ability to execute workflows to automate business scenarios by using triggers without writing any code? -> Azure Logic Apps
12. What can you use to launch the Azure Cloud Shell? -> Azure portal
13. What enables you to scale to thousands of virtual machines for high-performance and large-scale parallel jobs? -> Azure Batch
14. Match the services on the left to the correct descriptions on the right:

- Azure Resource Locks -> Prevents resources from being accidentally deleted or changed
- Azure Blueprints -> Rapidly provisions and runs new environments with the knowledge that they are in line with the organization's compliance requirements
- Azure Policy -> Enforces standards and assess compliance across your organization

15. What enables you to provision a group of matching and load-balancing VMs in Azure? -> An Azure virtual machine scale set
16. What in Azure enables you to deploy Azure resources close to the users? -> Geo-distribution
17. What is supported by ExpressRoute for connecting on-premises network to Azure? -> A point-to-point Ethernet connection
18. Which Azure feature enables you to organize multiple subscriptions in hierarchies for unified policies and compliance? -> Management groups
19. What alerts you when service issues occur in an Azure environment, such as a regional Azure outage that affects all Azure customers? -> Azure Service Health
20. Authorization vs Authentication? -> Authentication confirms identity of person, authorization grants the proper access to a legitimate user

