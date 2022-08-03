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

## Part 1: Core Azure Concepts
### Covers:
- Benefits of cloud computing and how it can save you time and money
- Cloud concepts such as high availability, scalability, elasticity, agility, and disaster recovery
- Core Azure architecture components such as subscriptions, management groups, resources and resource groups
- Summary of geographic distribution concepts such as Azure regions, region pairs, and availability zones

## Part 2: Core Azure Services
### Covers:
- Benefits of cloud computing and how it can save you time and money
- Cloud concepts such as high availability, scalability, elasticity, agility, and disaster recovery
- Core Azure architecture components such as subscriptions, management groups, resources and resource groups
- Summary of geographic distribution concepts such as Azure regions, region pairs, and availability zones

### Azure Virtual Network Fundamentals
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

