The following module guides Business Partners and IBM sellers through the process of provisioning a **VMware Cloud Foundation (VCF) as a Service (VMwaaS) *multitenant*** instance with the IBM Cloud portal. Extra context on parameters and options is provided illustrating the value of features to users along with links to reference material.

!!! Important "About the IBM Technology Zone (ITZ) environment"

    The steps that follow are specific to the provisioning process of VCF as a Service as of August 2024. 
    
    The steps can also be used in the IBM Cloud portal. Users can perform these steps in the ITZ environment that was reserved up until the last step to create the instance. **If using the ITZ cloud account and the *Create* button is clicked, an error will occur.** This is expected as users added to the IBM Cloud for the ITZ environment do **NOT** have permission to provision or modify existing resources. 

    **If the steps are performed in a different IBM Cloud account where the user has permission to create new resources, the account will be charged for any and all resources provisioned!**

# click-through demonstration
 Use the click-through demonstration to practice the provisioning process.

!!! tip
    
    When using the click-through demonstration, if you are not sure where to click or what to do next, simply click anywhere on the screen and the place to click next will be highlighted. Text entry fields are pre-populated in the click-through demonstration.

## Step-by-step Instructions
### Provision a multitenant Virtual Data Center (VDC)
1. Open the click-thru demo and then click play ![](_attachments/ClickThruPlayButton.png) to begin the demonstration.

    **Click-thru demo:** <a href={{clickthru.vcsaasmtProvisioning}} target ="_blank">Provision an instance of VCF as a Service - Multitenant</a>
     <!-- **Click-thru demo:** <a href="https://ibm.github.io/SalesEnablement-VMware-L3/includes/VMwaaS-mt-provisioning/index.html" target ="_blank">Provision a multitenant instance of VMwaaS</a> -->

2. Click the VMware (![](_attachments/VMicon.png)) icon in the left menu.
3. Click the **VMware Cloud Foundation (VCF) as a Service** tile.

    Notice the three (3) tiles under **What would you like to create?"**. For this demonstration, a **Multitenant Virtual data center** will be created. The other two tiles are related to the **Single-tenant** option, one tile to create a VMware Cloud Director (VCD) site, and one tile to create a Virtual data center in the VCD site. 


4. Click **VDC details** in left menu.
5. Click in the **Name** field.

    A descriptive name for the VDC should be used. Once created, the name cannot be changed.

6. Click the **Resource group** drop-down list.

    Resource groups are used to help manage resources and billing in an IBM Cloud account.

7. Click the **{{itz.resourceGroup}}** resource group.
8. Click the **Data center** drop-down list.

    Refer to the product <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-tenant-plan-deploy#tenant-plan-deploy-locations" target="_blank">documentation</a> or the IBM Cloud Portal for the list of currently supported locations.

9. Click **DAL13**.
10. Enable the **Fast provisioning of VMs using linked clones** **information** switch.

    The **Fast provisioning of VMs using linked clones** option saves time by using linked clones for virtual machine provisioning. You can enable fast provisioning for any VDC created within the resource pool. If not enabled, all provisioning operations use full clones. To learn more about fast provisioning, check out VMware's documentation <a href="https://docs.vmware.com/en/VMware-Cloud-Director/10.4/VMware-Cloud-Director-Tenant-Portal-Guide/GUID-4C232B62-4C95-44FF-AD8F-DA2588A5BACC.html" target="_blank">here</a>. 

### Network settings
There are several network settings available for the multitenant option.

Clients choose to create the VDC with a network edge. VDCs connect to the public and IBM private networks through edges. Edges can also be used to connect multiple VDC networks together. Disabling this option removes the next two selections for **Network connection**.

Clients can choose to expose the VDC to both the public (internet) and private networks or just the private network.
When you select private-only workload connectivity, the VDC does not have an incoming or outgoing connectivity path to the public internet and can access IBM Cloud Services only over the private IBM network. 

VDCs can connect to IBM Cloud Transit Gateway to enable the workloads to securely connect to other workloads outside of the private network. For more information, see <a href="https://cloud.ibm.com/docs/vmware-service?topic=vmware-service-tgw-adding-connections" target="_blank">Using Transit Gateway to interconnect VCF as a Service with IBM Cloud services</a>.

The connection is made available through the network edge. There are four options for the network edge. Note the number of vCPUs, memory, and pricing associated with each option: 

- **Efficiency** These edges allocate networking resources that can be used by up to 64 VDCs before another efficiency edge needs to be created. The first time an efficiency edge is selected new CPU, RAM, and storage resources are required. CPU and RAM are used from the single-tenant site. New edge storage is allocated at a cost. Subsequent VDCs up to 64 can use this edge at no extra cost. This option is suitable for saving resources and costs with independent networking control per VDC.

- **Performance - M** This option is suitable when only Layer 2 (L2) through L4 features such as Network Address Translation (NAT), routing, and L4 firewall are required and the total throughput requirement is in the range 2-6 gigabits per second (Gbps).

- **Performance - L** This option is suitable when only L2 through L4 features such as NAT, routing, and L4 firewall are required and the total throughput is in the range 2-10 Gbps. This option is recommended for high traffic.

- **Performance - XL** This option provides the highest level of edge services and throughput over 10 Gbps.

For this demonstration, the default Network settings are used.

### Pricing plan
11. Click **Pricing plan** in left menu.

    Notice the 2 pricing plan tiles. Clients can choose either an on-demand or reserved pricing model. Learn more about the available pricing plans <a href="https://cloud.ibm.com/vmware/vmware_as_a_service/provision/vdc_mt#about" target="_blank">here</a> (scroll down to **Details and pricing**). It is important to understand that with the on-demand model, resources are not preallocated. Delays might occur when requesting extra resources. With the reserved model, resources are preallocated and availability is guaranteed. However, clients are charged for the resources even if they are not used.

### Consumption limits
vCPU and RAM charges for on-demand virtual data centers are based on the amount that is used for running workloads. To control cost, clients can use limits to restrict the maximum amount of vCPU and RAM usage in the virtual data center.

12. Click the **vCPU limit (cores)** entry box to set it to 100.

    Note the range of the vCPU limit is from 1 to 2000 vCPUs.

13. Click the **RAM limit (GB)** entry box to set it to 200.

    Note the range of RAM is between 1 and 40960 gigabytes (GB).

14. Click the **I have read and agreed to the following license agreements** checkbox in **Summary** panel.
15. Click the **Create** button.

The provisioning process is automated. Provisioning time varies based on the configuration and network edge option selected. When the ITZ environment used for this learning plan was originally created, the provisioning of the VDC took approximately 15 minutes.

Now that a multitenant **VDC** is provisioned, it is time to look at the management capabilities through the IBM Cloud portal.