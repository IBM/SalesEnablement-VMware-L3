Having completed the earlier modules on provisioning a VMware Cloud Foundation (VCF) as a Service multitenant instance, it is now time to operate and use the VCF environment.

VCF provides a robust private cloud environment running on public cloud infrastructure (like IBM Cloud). VCF includes the full VMware stack of products including vSphere for compute, vSAN for storage, NSX for networking, and Aria for management. 

These VMware products are large, complex, and full of many, many features. The intent of this module is not to demonstrate all the capabilities of VCF, rather to provide basic education and demonstration capabilities that illustrate:

- How the *"on IBM Cloud"* capabilities of the **VCF as a Service multitenant** are exposed through the VMware web console (VMware vCloud Director [VCD]).
  
- How to provision basic resources including data center groups, networks, and virtual machines using VCD.

- Illustrate how a **VCF as a Service multitenant** instance on IBM Cloud is just like VCF in a client's enterprise data center.

!!! Important "About the IBM Technology Zone (ITZ) environment"

    The steps that follow are specific to the ITZ environment reserved as part of the {{learningplan.name}} learning plan. If you don't already have an active reservation, refer to [Reserve the IBM Technology Zone environment](../../TechZoneEnvironment.md).

    ** The images shown in this document will look different than the live environment you will be using.** The resources described here will have already been created and other users may have created additional resources.
    
    All of the steps described in this module **CAN** be completed by every user of the shared ITZ environment using VMware vCloud Director (VCD). However, in some instances, creating new resources (like networks) will be discouraged. 

    **If you opt to create a resource, please delete the resource before your ITZ reservation expires!** Doing so will reduce ongoing maintenance costs of the environment and help preserve the usability of the shared environment.

1. Click the link below to open a browser to the IBM Cloud portal.

    <a href="https://cloud.ibm.com/vmware/resources/vdc" target="_blank">IBM Cloud portal</a>

2. If not already in the {{itz.account}}, switch to the {{itz.account}} IBM Cloud account.

    Depending on the size of the browser window, the switch account menu will vary as seen in these two animated images.

    ![](_attachments/switchAccount3.gif)

    ![](_attachments/switchAccount4.gif)

3. Click **{{itz.VCFaaSmt.name}}** in the virtual data centers (VDC) table.

    ![](_attachments/vcf-mt-opeartingVCDtable.png)

4. Click **VMware console**.

    ![](_attachments/vcf-mt-opeartingVCDinstanceSummary.png)

5. Click **SIGN IN WITH OIDC**.

    Single sign-on has been enabled as part of the **VCF as a Service** integration with VCD. The integration is between the VMware components and IBM Cloud Identity and Access Management (IAM). OpenID Connect (OIDC) is an identity layer built on top of the OAuth 2.0 framework. It allows third-party applications to verify the identity of the end-user and to obtain basic user profile information. Learn more about OIDC <a href="https://auth0.com/docs/authenticate/protocols/openid-connect-protocol" target="_blank">here</a>. Learn more about the IBM Cloud IAM and VMware sign in capabilities <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration" target="_blank">here</a>.

    ![](_attachments/vcd-LoginScreen.png)

    !!! Warning "You may be asked to reauthenticate to IBM Cloud"

        After clicking the **SIGN IN WITH OIDC** button, you may be asked to re-authenticate to IBM Cloud. IBM employees and business partners that have multi-factor authentication (MFA) enabled in their IBM Cloud account may also have additional authentication steps to perform. These steps are not detailed here.

6. Explore the information displayed on the **Data Centers** summary page and then click the {{itz.VCFaaSmt.name}} tile.

    The screen capture shown below was taken before any resources were provisioned in the **VCF as a Service** instance. Your view will be different and reflect any currently provisioned resources.

    ![](_attachments/vcd-DataCentersSummary.png)

### Networking
The network for a **VCF as a Service** environment is a critical element that clients must plan carefully. Some information on network planning is provided in the IBM Cloud documentation <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-vcd-ops-guide#vcd-ops-guide-networking" target="_blank">here</a>. VMware also has good documentation that is accessible through the vCloud Director web console or <a href="https://docs.vmware.com/en/VMware-Cloud-Director/10.4/VMware-Cloud-Director-Tenant-Portal-Guide/GUID-0544FE2A-B036-43E0-B549-40BACDF261B6.html" target="_blank">here</a>. The network implementation in this demonstration environment is minimal and should not be considered as a best of practice.

The next steps show how to create a data center group, expand the scope of an edge gateway, and create a network that can be used by virtual machines (VMs). Data center groups allow administrators to group VDCs together to share network resources. In this ITZ environment, a group of only one VDC will be created. However, in most client environments, there will be multiple VDCs, and connectivity will need to be established between them. To allow network connectivity to VMs, a data center group and network needs to be created in the virtual data center. 

!!! Warning "In the ITZ enviroment, you can, but you don't need to"

    While you can create a new data center group and network in the instance, there is no need to as they have already been created in the ITZ environment. If you do create new ones, please delete yours, and only yours before your ITZ reservation expires.

7. Click the **Networking** tab.

    ![](_attachments/vcd-dataCenters-NetworkingTab.png)

8. Click the **Data Center Groups** tab.

    ![](_attachments/vcd-network-DCGtab.png)

9. Click **New**.

    ![](_attachments/vcd-dcgNewButton.png)
    
10.  Select the **{{itz.VCFaaSmt.name}}** VDC and click **NEXT**.

    ![](_attachments/vcd-dcgNewSelectVDCNext.png)

11.  Enter a **unique name** and **description** and click **NEXT**.

    ![](_attachments/vcd-dcgNewNameDescNext.png)

12.  Click **NEXT** on the **Participating VDCs** screen.

    ![](_attachments/vcd-dcgParticipatingNext.png)

13.  Click **CANCEL**.

    A VDC group has already been created in the shared environment, so no need to create one. However, if you really want to, you can click *Finish*, but please be sure to remove any resources you create.

    ![](_attachments/vcd-dcgCancel.png)

    It takes just a few seconds for the VDC group to be created.

14.  Click the **Edge Gateways** tab.

    Notice the **Recent Tasks** table at the bottom of the page and the status of the recent actions.

    ![](_attachments/vcd-dcgToEGTabpng.png)

15.  Click {{itz.VCFaaSmt.name}} in the table. Note the name in the table will have a unique ID appended to it.

    ![](_attachments/vcd-eg-Table.png)

16. Click **INCREASE SCOPE**.

    !!! Important "Scope has already been increased"

        When the network was initially created, the scope was increased. The **DECREASE SCOPE** option will be visible now.

    The scope needs to be increased to include the VDC group created earlier.

    ![](_attachments/vcd-eg-IncreaseScopeButton.png)

17. Click **DISCARD**.

    This action has already been performed on the existing edge gateway. If you were to create a new one, you would select the group in the table and click *OK*.

    ![](_attachments/vcd-eg-IncreaseScope.png)

18. Click the **Networks** tab.

    ![](_attachments/vcd-eg-NetworksTab.png)

19. Click **NEW**.

    ![](_attachments/vcd-Networks-AddButton.png)

20. Select **Data Center Group** and select the **vdc-group-mt-se-l3** group then click **NEXT**.

    ![](_attachments/vcd-network-Scope.png)

21. Review the **Network Type** page and then click **NEXT**.

    A Routed network is chosen to allow the virtual machines to communicate with each other within the VDCs, and potentially outside to other resources like the Internet or other IBM Cloud services.

22. Enter a **Name** and **Description** and then specify a new CIDR and click **NEXT**.

    In this demonstration environment, a network is created using the non-routable private network CIDR of 192.168.1.1/24. 

    The *Dual-Stack Mode* enables support for both IPv4 and IPv6 addressing. The *Distributed Routing* option provides fast and efficient East-West routing. This can be disabled to connect to the service router and force all VM traffic through the service router.

    ![](_attachments/vcd-network-General.png)

23. Review the **Static IP Pools** page and then click **NEXT**.
24. Enter **161.26.0.10** and **161.26.0.11** for the **Primary DNS** and **Secondary DNS** and click **NEXT**.

    The 161.26.0.10 and 161.26.0.11 addresses are the IBM Cloud public DNS addresses.

    ![](_attachments/vcd-network-DNS.png)

25. Click **CANCEL** and then **YES** in the **Cancel Wizard** dialog.

    This action has already been performed on the existing network. If you were to create a new one, you would click *FINISH*.

    ![](_attachments/vcd-network-Cancel.png)

    Once the network is created and the status turns to **Normal**, the next step is to activate dynamic host configuration protocol (DHCP) so VMs are automatically assigned network addresses when they are provisioned.

26. Click **vdc-mt-se-l3-defaultNetwork** in the table.

    ![](_attachments/vcd-network-TableCreated.png)

27. Click **DHCP** in left menu.

    ![](_attachments/vcd-network-DHCPMenu.png)

!!! Important "Please read about the next few steps"

    The next few steps **cannot** be performed with the default network already created in the ITZ environment. You can perform them if you create a new network. The steps are provided for education purposes. The next step you can actually perform is step 33.

28. Click **ACTIVATE**.

    Note, this option will not be available for the network already created, rather you will see *DEACTIVATE*. **DO NOT** *deactivate* DHCP for the default network!

    ![](_attachments/vcd-network-DHCPActivate.png)

29. Review the **General Settings** and click **NEXT**.

    ![](_attachments/vcd-network-DHCPGeneral.png)

30. Click **ADD** and then enter a valid IP Range for the network's CIDR and then click **NEXT**.

    ![](_attachments/vcd-network-DHCPPool.png)

31. Enter **161.26.0.10** and **161.26.0.11** for the **DNS Servers** and click **NEXT**.

    ![](_attachments/vcd-network-DHCPDNS.png)

32. Review the settings and click **FINISH**.

    ![](_attachments/vcd-network-DHCPFINISH.png)

The network is now setup and ready to be used.
### Create a Virtual Application (vApp)
 A VMware vApp is a collection of virtual machines (and potentially other vApp containers) that are operated and monitored as a unit. 

!!! Important "About the IBM Technology Zone (ITZ) environment"

    You have permissions to create up to 4 vApps or virtual machines (VMs) in the ITZ environment. The steps below create a vApp with two VMs. If you create your own vApps or VMs in the environment, be sure to remove them before your ITZ reservation expires.


33. Click **Applications**.

    ![](_attachments/vcd-network-DHCPAppsTab.png)

34. Click the **NEW** drop-down list and select **New vApp**.

    ![](_attachments/vcd-vAPP-new.png)

35. Select the **{{itz.VCFaaSmt.name}}** data center and click **NEXT**.

    ![](_attachments/vcd-vApp-setVCD.png)

36. Enter a unique **Name** and a **Description** and then select **Power on** and then click **ADD VIRTUAL MACHINE**.


    ![](_attachments/vcd-vApp-NewvApp-AddVM.png)

37. Enter a unique **Name** and **Computer Name**.

    The **Computer Name** will autofill with the specified **Name** unless it does not conform to a valid hostname.

    ![](_attachments/vcd-vApp-NewvApp-NewVMName.png)

38. Select a **Template** from the table.

    The **CentOS-7-Template-Official** is a good choice as VMs using this template boot quickly.

    ![](_attachments/vcd-vApp-NewvAPp-templateOK.png)


39. Scroll down and change set the **Storage Policy** to **2 IOPS/GB**.

    Review the storage options available. Recall when the **VCF as a Service multitenant** instance was created, there were no storage options specified. Storage is defined at the **site** level and in the case of the **multitenant** offering, managed by IBM. Charges for storage vary by the storage policy selected.

    ![](_attachments/vcd-vApp-NewvApp-NewVMStorage.png)

40. Review the **Compute** and **NICs** settings and click **OK**.

    **a**. The **Compute** settings are defined by the template selected.

    **b**. The network interface cards (NICs) is set to the default network, which was created earlier, and DHCP is selected.

    ![](_attachments/vcd-vApp-NewvApp-cpunics.png)

41. Click **ADD VIRTUAL MACHINE** and **repeat steps 37 through 40** specifying a new name for the 2nd VM.

    After repeating steps 37-40, you should now have 2 VMs listed in the table.

42. Click **Create**.

    ![](_attachments/vcd-vApp-NewvAppCreate.png)

43. Observe the **Recent Tasks** as the vApp and VMs are created and started and then click **the vApp tile**.

    ![](_attachments/vcd-vApp-UpAndRunning.png)

44. Observe the VMs in the vApp and the options available.

    **a**. Notice the state of the VMs. It may take a few minutes for them to show **Powered on**.
    
    **b**. Try accessing the VM using the **VM console** link. Note, the VM web console tool does not appear to work with the Safari browser! If you want to log into the VM, retrieve the password from the VM details page. To see the auto-generated password, edit the **Guest OS Customization**.
    
    **c**. Review the **Network Diagram** that VMware generates for the vAPP.

    ![](_attachments/vcd-vApp-Details.png)

At this stage, continue to explore the other capabilities exposed through the VMware web console.






