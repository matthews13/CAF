## Navigation Menu
* [Overview](../README.md)
* [North Star Architecture](./NorthStar-Architecture.md)
    -	**Design Principles**
* [Design Guidelines](./Design-Guidelines.md)
    -	[A - Enterprise Enrolment and Azure AD Tenants](./A-Enterprise-Enrolment-and-Azure-AD-Tenants.md)
    -	[B - Identity and Access Management](./B-Identity-and-Access-Management.md)
    -	[C - Management Group and Subscription Organisation](./C-Management-Group-and-Subscription-Organisation.md)
    -	[D - Network Topology and Connectivity](./D-Network-Topology-and-Connectivity.md)
    -	[E - Management and Monitoring](./E-Management-and-Monitoring.md)
    -	[F - Business Continuity and Disaster Recovery](./F-Business-Continuity-and-Disaster-Recovery.md)
    -	[G - Security, Governance and Compliance](./G-Security-Governance-and-Compliance.md)
    -	[H - Platform Automation and DevOps](./H-Platform-Automation-and-DevOps.md)
* [Implementation Guide](./Implementation-Guide.md)
---

# Design Principles

The “North Star” architecture prescribed within this playbook is underpinned by following fundamental design principals, which serve as a compass for subsequent design decisions across critical technical domains. Readers are strongly advised to familiarize themselves with these principals to better understand their impact and the trade-offs associated with non-adherence.

**Subscription Democratisation**

Subscriptions should be used as a unit of management and scale aligned with business needs and priorities, to support business areas and portfolio owners to accelerate application migrations and net-new application development. Subscriptions should be provided to business lines to support the design and development/testing of both migrating and net-new workloads.

**Policy Driven Governance**

Azure Policy should be used to provide the “guard-rails” and ensure the continued compliance of the customer platform and applications deployed onto it, whilst also providing application owners sufficient freedom and a secure unhindered path to cloud.

**Single Control and Management Plane**

The “North Star” architecture should not consider any abstraction layers such as customer developed portals or tooling and should provide a consistent experience for both AppOps (centrally managed operation teams) and DevOps (dedicated application operation teams). Azure provides a unified and consistent control plane across all Azure resources and provisioning channels which should be used to establish a consistent set of policies and controls for governing the entire customer estate, subject to RBAC and policy driven controls.

**Application Centric and Archetype-Neutral**

The “North Star” architecture should focus on application centric migrations and development rather than a pure infrastructure “lift and shift” migration (i.e. movement of virtual machines) and should not differentiate between old/new applications or IaaS/PaaS applications. Ultimately, it should provide the foundation for all application types to be deployed onto the customer Azure platform securely and safely.

**Azure Native Design and Roadmap Aligned**

The North Star architecture strongly advocates the use of native platform services and capabilities wherever possible, which should be fully aligned with Azure platform roadmaps from the offset to ensure new capabilities are swiftly made available within customer environments. More specifically, Azure platform roadmaps should help to inform the migration strategy and ”North Star” trajectory.

-   Be prepared to trade off functionality as not everything will likely be required on day one.
-   Leverage preview services and take dependencies on service roadmaps in order to remove technical blockers.
