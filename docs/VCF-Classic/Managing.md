Now it is time to provision a VMware Cloud Foundation (VCF) for Classic instance. Use the click-through demonstration below to practice provisioning a VCF for Classic instance.

!!! Important "About the IBM Technology Zone (ITZ) environment"

    The steps that follow are specific to the management capabilities of VCF for Classic as of August 2024. 
 
    The steps **CANNOT** be used in the ITZ environment that was reserved for this course. To save costs, the VCF for Classic instance was removed after the creation of the associated click-through demonstrations. 

!!! tip
    
    When using the click-through demonstration, if you are not sure where to click or what to do next, simply click anywhere on the screen and the place to click next will be highlighted. Text entry fields are pre-populated in the click-through demonstration.

1. Open the link below and then click the play button ![](_attachments/ClickThruPlayButton.png) to begin the demonstration.

    **Click-through demonstration:** <a href={{clickthru.vcsManaging}} target ="_blank">Manage an instance of VCF for Classic</a>

2. Click the **VMware** ![](_attachments/VMicon.png) icon in the left menu.

3. Click **VCF for Classic** under **Resources** in left menu.
4. Click **{{itz.dedicated.instanceName}}** in the table of VCF for Classic instances.

    The **Summary** page provides information about the VCF for Classic instance including software versions deployed, instance ID, location, and root and single sign-on domain.

5. Click the **Actions** drop-down list.

    There are 2 actions that be performed from the **Actions** menu. The **Refresh** option updates the information about the instance. 
    
    The **Delete instance** option removes the VCF for Classic instance. When deleting the instance, all resources that are associated with the instance are permanently deleted, including vCenter Server, hosts, VMs, VLANs, subnets, services, and licenses. This action cannot be undone. To delete some of the resources in the instance and keep others, a support ticket must be opened. For instances that are part of a multi-site configuration, there are additional steps that must be followed. Refer to the documentation <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletinginstance_multi" target="_blank">here</a>.

6. Click **Refresh**.
7. Click the **Access information** tab.

    The **Access information** page provides the details required to access the core VMware components of the VCF for Classic deployment including IP addresses, fully qualified domain names (FQDN), administrative identities, and passwords.

8. Click the **information** (![](_attachments/infoIcon.png)) icon next to **Access information**.

    It is the client's responsibility to manage the VCF for Classic deployment. All of the administrative passwords for the VMware components should be changed and recorded in the clients own password management system. Once changed, the passwords shown on the **Access information** page will no longer be valid.

9. Click the **information dialog** to dismiss it.
10. Click the **Infrastructure** tab.

    The **Infrastructure** page lists all clusters associated with the VCF for Classic instance. Recall, this instance was provisioned with a single **consolidated cluster**. Had a **workload** or **gateway** cluster been created, those items would be listed. Summary information about the cluster is provided. Individual clusters can be deleted from the page.

    The **Infrastructure** page is where new clusters can be added to the instance.

11. Click **Create**.
    
    The **Create cluster** form should look familiar. It is very similar to part of the form used when the VCF for Classic instance was created.

    This form can be used to create both **workload** and **gateway** clusters. First, explore adding a **workload** cluster.

12. Select **Select a different location**.

    If a different location is selected, the cluster will be provisioned in a data center that is different from the one of the VCF for Classic instance. Network latency might occur between the instance and the hosts, and between customer workloads that communicate from different locations.

13. Select **pod 04** for the data center location.
    
    Notice the new **workload** cluster can use a different server configuration than the initial cluster created. Clients may want smaller or larger **workload** clusters that are right-sized for particular workloads.

14. Click the **information** (![](_attachments/infoIcon.png)) icon next to **Number of bare metal servers**.

    A minimum of two (2) bare metal servers are required to create a cluster.

15. Click the **information dialog** to dismiss it.

    New **workload** clusters can choose NFS or vSAN for the cluster storage.

16. Click the **Hostname prefix** entry field.

    In the **Network interface** section the same network parameters can be specified as when first creating the VCF for Classic instance. In addition, either the existing virtual local area networks (vLANS) of the instance can be used or new ones can be created.

17. Read and then click the **information** dialog regarding vLANs. 

    It is critical that the VMware management components like VMware vCenter Server are able to communicate with the new cluster. Learn more about the topic <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-deploy-day2ops" target="_blank">here</a>.

18. Click the **Private VLAN** drop-down list.
19. Select **Allocate a new one**.
20. Click the **Secondary private VLAN** drop-down list.
21. Select **Allocate a new one**.
22. Select the **I understand that the following account will be charged** agreement.
23. Select the **I have read and agreed to the following third-party service** agreement.

    At this point, the user would click create and the new cluster would start to provision.

    Now, explore the steps to create a new **Gateway cluster**.

24. Select **Gateway cluster**.

    Notice the **Data center location** is set and cannot be changed.

25. Select **Dual Intel Xeon Silver 4210** for the CPU model.

    Notice the additional parameters that can be specified for the gateway cluster.

26. Select the **I understand that the following account will be charged** agreement.
27. Select the **I have read and agreed to the following third-party service** agreement.

    At this point, the user would click create and the new cluster would start to provision.

28. Click the **vce-se-l3 (primary)** in the breadcrumb trail.
29. Click **{{itz.dedicated.clusterName}}** in the cluster table.
    
    The details page for a cluster provides information about all the components of the cluster including the servers running ESXi, storage, and network. In addition, additional servers and storage can be added to the cluster from this page.

30. Click **Add** in the **ESXi servers** table.
    
    When adding servers to the cluster, the new servers can either use the same CPU model and configuration or a new configuration. While it is a best practice to have all servers in a cluster be heterogeneous, that is not always possible as CPU models age out and are replaced by newer models. Another scenario is if there is a desire to upgrade all the servers in a cluster to a different CPU model and configuration.

31. Click the **information** (![](_attachments/infoIcon.png)) icon next to **Maintenance mode**.

    In most circumstances administrators do not want workloads to be assigned to new hosts until all customizations and updates to the host are complete. Bring the hosts up in **Maintenance mode** prevents that from occurring.

32. Click the **information dialog** to dismiss it.
33. Click **Next**.
34. Review the screen and click **Next**.
    
    The new host or hosts can either use the same primary subnets or a different one. The subnets must already exist and be reachable by the VMware management components.

    The next step would be to accept the agreements and then click **Add**. For this demonstration, a new server will not be added.

35. Click the **x** to close the **Add ESXi server** dialog.
36. Select the **host-mf000.se.l3.com** server in the table.

    Notice, when one or more hosts are selected, the **Delete** option becomes available.

37. Click **Cancel** in the **ESXi servers** table.
38. Click **Add** in the **Storage** table.

    Additional NFS storage shares can be added to the cluster. The size and performance tier can be specified for each share.

    Note, if the cluster used vSAN storage, the ability to add new servers and storage for the vSAN cluster would be presented.

39. Click the **x** to close the **Add NFS storage** dialog.
40. Select **management-share** in the **Storage** table.
    
    Notice, when one or more shares are selected, the **Delete** option becomes available.

41. Click **Cancel** in the **Storage** table.
    
    The **Network interface** section provides detailed information on the vLANs used in the instance. Notice the **download** (![](_attachments/downloadIcon.png)) icon above the vLAN tables. Use this button to download a comma separated value (CSV) file of all the associated subnets and IP addresses associated with the cluster.

42.  Expand the **10.213.88.128/25** subnet in the **Private VLAN** table.

    All of the IP addresses in the subnet are listed along with a status and the use of the address. In this case, these are the IPs associated with the NSX portable subnet.

43.  Collapse the **10.213.88.128/25** subnet.
44.  Click the **Secondary Private VLAN** tab.

    This table shows the subnets used for private storage and vMotion of VMs in the cluster.

45.  Click the **Public VLAN** tab.

    If enabled with public network access, this section shows the primary subnet for hosts and virtual server instances, public subnet for customer workload edge, and the public subnet for the management edge.

46. Click **View resource**.

    This link opens a new browser tab or window to the IBM Cloud portal page associated with the networking elements in the table.

47. Click the **x** to the new browser tab.
48. Click the **All clusters** link to return to the main **Infrastructure** page.
49.  Click the **Services** tab.

    The **Services** page lists all services that have been deployed into the VCF for Classic instance during the provisioning process. The ability to add new services is also available.

50. Click **Add**.

    Any available service that was not added during the initial provisioning can be added from this screen. Note, some services may require additional capacity to be added beforehand. For more information on the additional services, refer to the product documentation <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-addon-services" target="_blank">here</a>.

51. Click the **vcs-se-l3 (primary)** link in the breadcrumb trail.
52. Click **Veeam**.

    Information needed to access the Veeam console is shown here. The **Open Veeam Console** button is part of this click-through demonstration and is not part of the IBM Cloud portal.

53. Click **Open Veeam Console**.

    The **Veeam* suite of tools are deployed on a Microsoft Windows server. This can be a Windows Server VM deployed in the VCF for Classic infrastructure, a virtual server instance (VSI) on IBM Cloud, or a bare metal server on IBM Cloud. The specific steps to establish a virtual private network (VPN), configure the local hosts file, and opening a remote desktop client are not detailed in this click-through demonstration. To learn about that process, review the documentation <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-interconnectivity-vpn" target="_blank">here</a>.

54. Click the first **Veeam Backup** icon on the desktop.

    The credentials to authenticate to the Veeam system was displayed on the service detail page in the IBM Cloud portal. Note, users should change the initial passwords of all services.

55. Deselect **Use windows session authentication**.
56. Click the **Password** entry field.
57. Click **Connect**.
    
    This demonstration is not meant as a deep dive on using Veeam and its associated tools. Refer to the Veeam documentation and Veeam training available on Veeam's web site <a href="www.veeam.com" target="_blank">here</a>. However, in the next steps, create a simple Veeam backup job.

58. Click **Inventory** in left menu.
59. Click **vcssel3-vc-se.l3.com** in the Virtual Infrastructure directory tree.
60. Click **VMware-Aria-Operations-for-Logs-Master**.

    The steps to select multiple hosts in the lists is simplified for this click-through demonstration. 

61. Click the selected hosts.

    The steps open the context menu is simplified as a single click. In the actual console, users would right-click on the lists of selected hosts.

62.  Click **Add to backup job**.
63.  Click **New job**.
    
    The **New Backup Job** wizard walks through the process of defining a backup job.

64. Explore the settings on the page and click **Next**.
65. Explore the **Virtual Machines** page and click **Next**.
66. Explore the **Storage** page and click **Next**.
67. Explore the **Guest processing** page and click **Next**.
68. Select **Run the job automatically**.
69. Explore the **Schedule** page and click **Apply**.
70. Select **Run the job when I click Finish**.
71. Click **Finish**.
72. Click **Home**.

    Notice the job has been started and is scheduled for future runs as specified when the job was defined.

73. Click **Return to IBM Cloud Portal**.
74. Click **x** to close the **Veeam** service page.
75. Click **VMware Aria Operations and VMware Aria Operations for Logs Enterprise Edition**.

    Details to access the VMware Aria Operations Manager console and the VMware Aria Operations for Logs console are displayed. Initial passwords should be changed. Accessing the Aria consoles requires a VPN.

    Note, the buttons to open the consoles are part of the IBM Cloud portal.

76. Click **VMware Aria Operations Manager console**.

    Note, the initial log in screen was not captured. It is identical to the one below shown for the **VMware Aria Operations for Logs console**.

77. Click **Next** on the **Welcome** page.
78. Click **I accept the terms of this agreement**.
79. Click **Next**.
80. Click **Next** on the license key page.
81. Click **Next** on the **Customer Experience Improvement Program** page.
82. Click **Finish**.

    **VMware Aria Operations** enables proactive IT operations, management, logging, and diagnostics management for VCF. To learn more about **VMware Aria Operations**, refer to this <a href="https://www.vmware.com/products/cloud-infrastructure/cloud-foundation-operations#features" target="_blank">VMware site</a>.

83. Click **Troubleshoot**.
84. Click **Alerts**.

    The console provides insights into events occurring in the VMware environment. 

85. Click **NSX Management service has failed**.

    View the alert messages. Note, these alerts were generated during the automated provisioning process for the VCF for Classic instance. The issues related to the alerts were rectified as the instance became fully deployed and active.

86. Click **Log Analysis** in left menu.

    The console provides insights into the thousands of log messages that occur during the normal operation of a VMware deployment.

87. Click **Visualize** in left menu.
88. Click **Dashboards** in left menu.
89. Click **Assess Cost**.

    Since this is a new deployment, there is limited data; however, VMware Aria Operations Manager can help organizations reduce costs and improve efficiency through real-time, predictive capacity and cost analytics.

90. Click **Home**.
91. Click **Inventory**.

    The **Inventory** dashboard shows the number of resources in the environment and help quantify the number of resources based on various perspectives and relationships within the environment.

92. Click **vSphere Inventory Summary**.
93. Click **Environment** in left menu.
    
    More detailed information on the inventory is also available.

94. Click **x** to close the VMware Aria Operations Manager console tab.
95. Click **VMware Aria Operations for Logs console**.
96. Click **Login**.

    Vmware Aria Operations for Logs provides organizations with centralized log management, deep operational visibility, and intelligent analytics for troubleshooting and auditing across a VCF for Classic instance.

    Review the data shown shown on the **Overview** page.

97. Click **Problems** in left menu and review the data presented.
98. Click **VMware - vROPs 6.7+** in left menu and review the data presented.
99. Click **Cluster - Threads Overview** in left menu and review the data presented.
100. Click **VMware - vSphere** in left menu and review the data presented.
101. Click **x** to close the browser tab for the VMware Aria Operations for Logs console.
102. Click **x** to close the service details page.
103. Click the **Deployment history** tab.

    The **Deployment history** shows the output of the various deployment steps performed for the instance. This view was taken just after the VCF for Classic completed the initial provisioning process.

104. Click **vCenter console**

    Like the other consoles for the add on services, accessing the **vCenter Console** is done through a VPN. The steps and links to establish the VPN are provided on the dialog and were performed outside of this click-through demonstration.

105. Click **Go to vCenter console**.
    
    Review the summary information provided for the deployed environment including capacity and usage data.

106. Click the **Hosts** tab.

    All the ESXi hosts provisioned as part of the consolidate cluster are shown along with their respective, consumption metric and high availability (HA) state.

107. Click the **Datastores** tab.

    Both the user specified datastores (the two [2] NFS 3 stores of 1,000 gigabytes [GB]) and the datastores required as part of the base infrastructure are displayed.

108. Click the **Networks** tab.
    
    The **Networks** pages lists all the port groups configured in the instance.

109. Click the **x** to close the **vCenter Server console** tab.
110. Click the **x** to close the dialog.
    
That concludes the click-through demonstration for managing a VCF for Classic instance. 
