The following module guides business partners and IBM sellers through the myriad of features and management tools available from within the VMware Shared platform dashboard on IBM Cloud. You will explore various elements of the management panels and tooling, including: data centers, applications, virtual machines, networking, libraries, platform administration, and system monitoring.

VMWare Solutions, including the **Shared** plan and other tiers, are accessible through the <a href="https://cloud.ibm.com/vmware" target="_blank">VMware portal on IBM Cloud</a>.

#
# Accessing the vCloud Director console

1. Ensure that your IBM Cloud account is using the ```ITZ-VMWARE``` account that you were invited to as part of the prerequisite setup for this hands-on material. From the IBM Cloud dashboard, click the **VMware** tab from the left-hand navigation menu, or alternatively search for ```VMware Solutions``` in the search bar.

!!! warning "WARNING"
    If you continue with the following instructions using your _personal_ IBM Cloud account, there is a risk that your account (and credit card associated with that personal account) will be billed for provisioning a VMware Solutions deployment. To avoid any unwanted charges, ensure that your account is switched to ```ITZ-VMWARE``` before continuing.

2. Drill down into the **Resources** tab within the left-hand navigation menu.

![](_attachments/shared-managing-1.png)

3. From the variety of VMware Solutions plans available, click on the **VMware Shared** tab.

![](_attachments/shared-managing-2.png)

An instance of VMware Shared should already be set up, having completed the <a href="https://ibm.github.io/SalesEnablement-VMware-L3/Shared/Provisioning/" target="_blank">Provisioning</a> section earlier.

4. Locate the instance— ```Dallas Director 01``` in the example screenshot below, although the naming of your instance may differ —and click the **name** of the instance to pull open a Summary page.

![](_attachments/shared-managing-3.png)

The browser will load a Summary panel for the VMware Shared instance, supplying details on access controls for your platform, virtual data centers associated with the deployment, and additional services that can be used in conjunction with the platform.

5. Before you can connect to the VMware Shared instance, you need to set an administrative password for the **vCloud Director console**. Do so by clicking the **Reset site admin password** button as shown.

![](_attachments/shared-managing-4.png)

A dialogue window will open, asking you to confirm an administrative password reset for the instance. Confirm the selection and wait for the reset to complete. The **User name** will always be set to ```admin``` by default. The **Password** will be uniquely generated each time a reset is conducted.

6. Click the "eyeball" icon to view the password and the "box" icon to copy the password to your machine's clipboard. **Record** both of these values to a notepad — you will need to reference these later for connecting to the vCloud Director Console. Click the **Close** button to continue.

![](_attachments/shared-managing-5.png)

7. Back on the Summary page, locate the **vCloud Director console** button near the top-right of the screen. Before resetting the admin password, this button would have been greyed out and inaccessible. With the password reset complete, the button is now active — click it to continue to the console login page.

![](_attachments/shared-managing-6.png)

8. A new tab or window will open, prompting you to log in to the vCloud Director console. Use the ```admin``` and ```password``` fields recorded in **Step 6** to log in to the console.

![](_attachments/shared-managing-7.png)

Having been successfully authenticated, your browser will redirect and open to the **vCloud Director console**. From this page, you will be able to access many of the administrative functions for your VMware Shared platform (restricted from full administrative purposes for the purposes of this hands-on, shared environment). By default, the console will load to the **Data Centers** tab. Here you can inspect details on the virtual data center supporting your environment, which in the case of the example screenshot below is the ```bienko-vdc``` environment which was set up during the <a href="https://ibm.github.io/SalesEnablement-VMware-L3/Shared/Provisioning/" target="_blank">Provisioning</a> section earlier. A summary of the VDC's CPU, memory, and storage utilization is provided at the bottom of the page.

9. Let's explore other elements of the vCloud Director console. From the navigation menu along the top of the console dashboard, click the **Applications** tab.

![](_attachments/shared-managing-8.png)

#
# Managing Applications and Virtual Machines

The console's **Applications** dashboard allows for the centralized management and deployment of all applications— which are categorized as either *virtual machines* or *virtual applications* —within the VMware Shared environment. A virtualized application, or *vApp*, consists of one or more virtual machines (VMs) that communicate over the Shared plan's network, makes use of the Shared plan's resources, or invokes services that the Shared plan supports. A single vApp can consist of one, or multiple, VMs as part of its backbone.

10. Let's try drafting a new virtualized application from scratch. Do so by clicking the **New vApp** button from the menu at the bottom of the page.

![](_attachments/shared-managing-9.png)

11. The first order of business is selecting which Virtual Data Center that the virtual application will be assigned to. By default, you should see the VDC environment that was created earlier (```bienko-vdc``` in the example screenshot below).

12. Click **Next** to continue.

![](_attachments/shared-managing-10.png)

13. The new vApp will require a **Name** (```vAppSample```) and a **Description** (```Demonstration purposes only.```). The **Power On** toggle can be left *off* for now, as we will not be deploying this example vApp to a live state.

14. No virtual machines currently exist within the VMware Shared VDC environment, but if they did they would be listed within the table presented on this page. Instead, you will need to craft your own. Click the **Add Virtual Machine** button below the table to define a new VM.

![](_attachments/shared-managing-11.png)

15. A new configuration window will open. Provide a **Name** (```BienkoVM```) and **Computer Name** (```BienkoVM```), as well as an optional **Description**, for the new VM.

16. The VM can either be crafted from scratch (**New**) or from a pre-designed template (**From Template**). One of the advantages of the VMware Shared plan on IBM Cloud is the wealth of templates available out of the box with the offering. Select the **From Template** option and then scroll through the template repository.

17. We recommend selecting the ```vm-redhat8``` template, which corresponds to the Red Hat 8 official template (RHEL8), for the purposes of this demonstration — although you are free to choose any of your liking. Scroll down the page to reveal more configuration options.

![](_attachments/shared-managing-12.png)

18. **Storage** for the VM is the next consideration. As described earlier in the Provisioning module, there are a variety of storage options available for virtual machines and virtual applications deployed within the VMware Shared environment. Each storage tier conveys different levels of throughput (IOPs) and levels of isolation (multi-tenant versus single-tenant), with differing levels of billable rates and charges associated with each tier. For our purposes, we recommend the ```Standard (VDC Default)``` tier of **Storage Policy**.

19. **Compute** is dictated by the VDC sizing configuration that was set during the Provisioning module. The resources available to the VM we are defining here are restricted by the hardware configurations assigned to the VDC (```bienko-vdc```) when it was deployed earlier.

20. **NICs**, or Network Interface Cards, provides the network interface needed by the virtual machine for communication with the public internet, IBM Cloud, and on-premises resources. The *Primary NIC* will have been configured by default and no other adjustments are required.

21. When satisfied, click the **OK** button at the bottom of the panel to return to the vApp definition.

![](_attachments/shared-managing-13.png)

#
# Creating vApps from a Template

22. An alternative to defining a vApp from scratch is to select from the pre-built catalog of vApps that are packaged with every VMware Shared deployment on IBM Cloud. To inspect the resources available, click the **Add vApp from Catalog** button at the bottom of the page.

![](_attachments/shared-managing-14.png)

23. A configuration window will open to configure a cataloged virtual application. First, select from the list of pre-built templates. For our demonstration purposes, we recommend selecting the ```CentOS-7-Template-Official```, but do take the time to browse the available options for yourself before continuing.

24. When satisfied with your selection, click **Next**.

![](_attachments/shared-managing-15.png)

25. The vAPP will require a **Name** (```BienkoVAppTemplate```) and optional **Description**.

The **Runtime lease** field determines the length of time that the vApp can run within the VDC before its access to system resources is paused. The **Storage lease** field sets the time that the vApp remains available, from the moment it is stopped (when the *Runtime lease* expires); after the *Storage lease* has expired, clean-up of the vApp resources and associated data will begin automatically.

26. For our demonstration purposes, both fields can be set to ```Never Expires```.

27. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-16.png)

The resources that the vApp will have permission to access are configured on the following page. As described in **Step 18**, there are a variety of **Storage Policies** available — with differing metering and pricing metrics associated with each tier.

28. For the purposes of our demonstration, configure the ```vm-centos07``` vApp to utilize the ```Standard``` Storage Tier.

29. **Per-Disk Storage Policies** are configured in the second table of this panel. You must **Select a VM**, which should be automatically populated to ```vm-centos07``` (or the VM naming that you specified earlier). The *Storage Policy* will inherit by the default the type of storage specified in **Step 28** (```Standard```).

30. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-17.png)

31. The vApp's **Compute Policies** are configured next. The total number of vCPUs that the vApp can access are determined by the **Virtual CPUs** field (```2```) and the constraints on **Cores per Socket** that can be accessed per vCPU are determined by the second field (```1```). The **Number of Sockets** is fixed at ```2``` for our example.

32. The maximum amount of RAM available to the vApp is determined by the **Memory** field (```8 GB```).

33. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-18.png)

34. The **Customize Hardware** panel will allow you to configure the hardware— storage, in our case —available to the virtual machines running as a part of this vApp. Recall that a vApp can be comprised of one, or many, virtual machines. The **Hard Disks** associated with the vApp have been configured automatically to a size of ```64 GB```.

35. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-19.png)

Via the **Configure Networking** panel, you can specify and constrain the virtual networks that VMs running within the vApp will be able to connect to. These variables can also be adjusted after the vApp has been configured and launched. The vApp (```vm-centos07```) to which these networking configurations will be applied has been selected automatically.

36. You must specify the **Network** field for this vApp: select the ```vAppNet-vro-template-network``` from the list of pre-configured networking templates.

37. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-20.png)

38. Additional properties can be configured via the **Custom Properties** tab. Should you wish, you can assign a custom hostname for guests via the ```guest.hostname``` property for this vApp. Leave this field blank.

39. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-21.png)

The **Ready to Complete** panel provides a full summary of your vApp (from Template) configurations. Here you can review the vApp before choosing to commit to a deployment, or discard the vApp configuration completely.
!!! warning "CAUTION"
    For our purposes, it is **NOT** necessary to deploy the vApp — this will incur costs to the IBM Cloud account.

40. Click the **Cancel** button to avoid any billing charges.

![](_attachments/shared-managing-22.png)

The web browser will automatically be redirected back to the **Applications** tab of the vCloud Director console.

#
# Managing Networks

41. From the dashboard of the vCloud Director console, switch to the **Networking** tab using the navigation bar along the top of the page.

From this management screen, you can access information on the VMware Shared plan's available Networks, Edge Gateways, Data Center Groups, and Security Tags. By default, the Networks associated with the deployment will be displayed first — at this time, your environment should contain no defined networks.

42. Click the **New** button, as shown in the screenshot below, to create a new network configuration.

![](_attachments/shared-managing-23.png)

A new page will load to guide you through the process of defining an organization-wide virtual data center (VDC) network. The first element to be defined is the overall **Scope** of the network.

43. The **Scope** of the network can be constrained to either an *organization-wide VDC* (providing connectivity only across the virtual machines belonging to that particular VDC), or across a *data center group* (connectivity across all VDCs belonging to that group, inclusive of all VMs belonging to those VDCs). Select the **Organization Virtual Data Center** option to keep networking connectivity restricted to only one VDC.

44. Given the selection made in **Step 43**, you will need to specify the organization VDC to which these constraints will apply. Select the VDC defined earlier (```bienko-vdc``` in this example).

45. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-24.png)

You must now decide the **Network Type** appropriate for this deployment. There are two options available:

- *Routed*: A network type that utilizes an edge gateway to enable controlled access to networks and machines external to (outside of) the VDC.

- *Isolated*: A network type that is only accessible by the VDC (or associated VDC Groups) specified in **Step 44**, thereby providing a fully isolated environment.

46. Select the **Routed** Network Type.

47. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-25.png)

48. Given our selected of a Routed network type in **Step 46**, which makes use of an edge gateway for regulated access to the network, we must now define an **Edge Connection** for the organization VDC. The configuration tool will automatically designate an edge connection (```edge-dal10-67c6f68e``` for the Dallas Director 01 data center) with ```2``` External Networks and ```0``` Org VDC Networks.

Next, you must choose the type of Edge Connection to be applied. There are three options available:

- *Internal*: For connecting to one of the edge gateway's internal interfaces. The maximum number of supported network connections is 9.

- *Distributed*: For connecting via fast and efficient *East-West* routing. The network will be connected to an internal interface of a distributed router that is exclusively associated with this gateway. The maximum number of supported network connections is 400.

- *Subinterface*: For connecting to the edge gateway's internal trunk interface. The maximum number of supported network connections is 200.

49. Select the **Internal** Edge Connection type.

50. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-26.png)

51. Time for some bookkeeping. Provide a unique **Name** for the organization VDC network (```BienkoNetwork```) and optionally a basic **Description** to its purpose.

A **Gateway CIDR** must be assigned, which includes the IP address of the gateway. This value cannot be changed once assigned. In our example, the CIDR of ```192.168.100.14/24``` represents the gateway address of ```192.168.100.14``` and its associated routing prefix of ```192.168.100.0```; or equivalently, its subnet mask of ```255.255.255.0```.

52. Assign a CIDR of ```192.168.100.14/24``` and leave the **Dual-Stack Mode** option disabled.

53. For our purposes, the network is not to be **Shared** and as such this option should remain disabled.

54. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-27.png)

55. **Static IP Pools** must now be assigned to the Gateway CIDR assigned earlier in **Step 52**. Verify that the CIDR displayed on this panel matches the one that you designated previously.

56. You may enable whichever range of IP addresses you wish; however, for the sake of example, let's assign a range of 7 IP addresses by entering ```192.168.100.14 - 192.168.100.20``` into the form as shown. Portable IP addresses are available to all resources on a VLAN, whereas static IP addresses are available to the resource identified as their routing endpoint.

57. Click the **Add** button after entering the IP address ranges to add them to the Static IP Pool.

58. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-28.png)

**DNS**, or the Domain Name System, provides the mapping between IP addresses (such as the ones specified earlier) and the "name" addreses that you typically enter into a web browser. A DNS relay can be enabled for the edge gateway we have configured thus far; however, it must be configured before deployment and cannot be modified after the fact.

59. **Enable** the **Use Edge DNS** slider. The remaining fields below can remain blank.

60. When satisfied, click **Next** to continue.

![](_attachments/shared-managing-29.png)

The **Ready to Complete** panel provides a full summary of your organization VDC network configurations. Here you can review the details of the network before choosing to commit to a deployment, or discard the network configuration completely.

61. Click the **Finish** button to create the network.

![](_attachments/shared-managing-30.png)

Your browser will automatically redirect to the **Networking** tab of the vCloud Director console.

62. From the list of subdirectories along the top of the screen, drill down into the **Edge Gateways** panel as shown.

63. The panel will summarize all of the Edge Gateways currently deployed on the VMware Shared platform, including the one we just created (```edge-dal10-67c6f68e```). Click the **Name** of that Edge Gateway (your name may differ from the example shown) to expand additional details on it.

![](_attachments/shared-managing-31.png)

Generalized information about the Edge Gateway are displayed on the details page.

64. Explore each of the subdirectories— *Services*, *Redeploy*, *Enable Distributed Routing*, *Sync Syslog*, and *Open in VDC Context* —to glimpse more of the administrative options available for your newly-created Edge Gateway and organization VDC network.

65. Information and configuration options related to **External Networks** are available from the navigation menu on the left side of the panel.

![](_attachments/shared-managing-32.png)

#
# Additional Capabilities and Tooling

For the purposes of this hands-on demonstration, we won't go too deeply into detail on other areas of the VMware Solutions Shared plan environment. Until live applications, virtualized machines, and a workforce of users are actively engaged with the platform, these other areas of the vCloud Director console will remain relatively quiet. However, we have included pointers below to relevant areas that may spark interest and conversations with clients. Feel free to peruse these areas and explore topics that may be pertinent to your customer engagements.

66. Using the navigation tabs along the top of the console, explore the **Libraries** tab. Here you can investigate more details on the vApp templates that were leveraged earlier in this hands-on material. Users can expand the templates available within their own environment by importing them directly from VMware's vCenter.

![](_attachments/shared-managing-33.png)

67. From the **Administration** tab, a myriad of options for user management and access control are available.

68. Here, VMware Shared users with administrative privileges can create new users, groups for those users, and roles for users to be assigned to. Identity providers, policies, certificates, and other security settings can also be implemented from this page.

![](_attachments/shared-managing-34.png)

69. As an example, the screenshot below emulates the **Create User** panel. A user ```vAppAuthor``` is defined and an authentication password is assigned.

70. The **Roles** field determines the level of privileged access and capabilities granted to the user. An administrator responsible for creating the user will be able to select from a variety of Roles (pre-built or admin-defined), such as ```vApp Author```, that enable a user to complete their expected job responsibilities without compromising the security of the VMware Shared platform as a whole.

71. **Quotas** can be applied to the user, limiting how many VMs (running or paused) that said user can manage within the platform.

72. Save or discard changes to users using the interface at the bottom of the panel.

![](_attachments/shared-managing-35.png)

73. Lastly, from the **Monitoring** tab it is possible for administrative users to inspect running *Tasks* and *Events* across the platform.

74. Click on any of the Task or Event names to drill down into more granular details surrounding that item.

75. When you have completed your tour of the vCloud Director console, click the username dropdown in the top-right corner of the dashboard and **Log Out** to end your session.

![](_attachments/shared-managing-36.png)

At this point in time, you have successfully explored the myriad of features and management tools available from within the VMware Shared platform dashboard on IBM Cloud. You now have a greater familiarity and expertise surrounding the various elements of the management panels and tooling, including: how to manage data centers, building application and virtual machines through the guided web interface, establishing networking rules, and the wealth of tooling available for managing the environment once in production.
