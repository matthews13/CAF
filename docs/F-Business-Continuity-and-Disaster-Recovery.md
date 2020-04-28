## Navigation Menu
* [Overview](../README.md)
* [North Star Architecture](./NorthStar-Architecture.md)
    -	[Design Principles](./Design-Principles.md)
* [Design Guidelines](./Design-Guidelines.md)
    -	[A - Enterprise Enrolment and Azure AD Tenants](./A-Enterprise-Enrolment-and-Azure-AD-Tenants.md)
    -	[B - Identity and Access Management](./B-Identity-and-Access-Management.md)
    -	[C - Management Group and Subscription Organisation](./C-Management-Group-and-Subscription-Organisation.md)
    -	[D - Network Topology and Connectivity](./D-Network-Topology-and-Connectivity.md)
    -	[E - Management and Monitoring](./E-Management-and-Monitoring.md)
    -	**F - Business Continuity and Disaster Recovery**
    -	[G - Security, Governance and Compliance](./G-Security-Governance-and-Compliance.md)
    -	[H - Platform Automation and DevOps](./H-Platform-Automation-and-DevOps.md)
* [Implementation Guide](./Implementation-Guide.md)
---

# F. Business Continuity and Disaster Recovery

### 1. Planning for BCDR

This section strives to help readers capture customer disaster recovery requirements, to design suitable platform level capabilities that application workloads can subsequently consume to meet their specific RTO and RPO requirements.

***Design Considerations***

-   Application and data availability requirements and the relative use of active-active and active-passive availability patterns i.e. workload RPO and RTO requirements.

-   BCDR for PaaS services and the availability of native DR and HA features.

-   Support for multi-region deployments, such as for failover purposes.

    -   Component proximity for performance reasons.

-   Application operation with reduced functionality or degraded performance in the presence of an outage.

-   Workload suitability for Availability Zones or Availability Sets.

    -   Data sharing and dependencies between zones.

    -   Impact of Availability Zones on update domains compared to Availability Sets; percentage of workload that can be simultaneously under maintenance.

    -   Support for specific VM SKUs with Availability Zones.

    -   If Ultra-Disks are used, usage of Availability Zones is mandatory.

-   Consistent backups for application state and data.

    -   VM snapshots and the use of Azure Backup and Recovery Service Vaults.

    -   Subscription limits restricting the number of Recovery Service Vaults and the size of each vault.

    -   Geo-replication and disaster recovery capabilities for PaaS services.

-   Network connectivity in the case of a failover.

    -   Bandwidth capacity planning for ER.

    -   Paired failover regions.

    -   Traffic routing in the case of region/zone/network outage.

-   Planned and unplanned failovers.

    -   IP address consistency requirements and the potential need to maintain IP addresses after failover and failback.

    -   Maintained engineering capabilities such as DevOps.

-   Key Vault DR for application keys, certificates and secrets.

***Design Recommendations***

-   Employ Azure Site Recovery for Azure to Azure Virtual Machine DR scenarios, to replicate workloads across regions.

-   Utilize native PaaS service DR capabilities, such as geo-replication for Azure Storage.

-   Leverage Azure native backup capabilities, such as Azure Backup, to transfer data to Azure Storage.

-   Use multiple regions and on-premise peering locations, connected using ExpressRoute.

<!-- -->

-   Avoid using overlapping IP address range for Production and DR sites.
