!!! Warning "Maintenance outage on Thursday, January 11 starting at 1p.m. EST"

    On Thursday, January 11, 2024 beginning at 1p.m. EST, one of the VMware as a Service (VMwaaS) instances (**se-le-site**) wil undergo maintenance. During this maintenance, the underlying VMware NSX-T deployment will be upgraded. This event is expected to last approximately 4 hours. The site and the 2 associated virtual data centers (se-l3-development and se-l3-test) will be unavailable during this period. This outage only affects your ability to complete the **Using VMware Cloud Director** section of this demonstration.

    Once the maintenance is complete, this warning message will be removed.  

    Thanks, and we appreciate your patience.


In previous chapters, the IBM Cloud Portal was used to provision a VMware as a Service instance or site, a provider virtual data center (PVDC), infrastructure clusters, and virtual data centers (VDCs). Now it is time to switch gears and use the VMware Cloud Director (vCloud Director or vCD) to provision virtual machines (VMs) to run the client's workloads. 

However, since most workloads consist of more than single machines that run isolated from other resources, some network configuration needs to be done first.

In the next chapter, learn how the VMwaaS network in the ITZ demonstration environment was setup by stepping through one last click-thru demonstration.