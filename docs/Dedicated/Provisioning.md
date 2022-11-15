Now it is time to provision a VMware vCenter Server (VCS) instance. Use the click-thru demonstration below to practice provisioning a VCS instance.

Note, fields that require a text entry (e.g. service name) are pre-populated in the click-thru demonstration.

!!! tip
    Not sure where to click or what to do next? Simply click anywhere on the screen and the spot to click next will be highlighted.

1. Open the link below and then click the play button ![](_attachments/ClickThruPlayButton.png) to begin the demonstration.

**Click-thru demo:** <a href="https://ibm.github.io/SalesEnablement-VMware-L3/includes/VMware-Dedicated-Provisioning/index.html" target ="_blank">Provision an instance of IBM Cloud VMware Solutions **Dedicated**</a>

2. Click the **VMware** ![](_attachments/VMicon.png) icon in the left-hand menu bar.
3. Click the **VMware vCenter Server** tile.
4. Click in the **Instance name** text entry field.

The Instance name field will automatically change to {{itz.dedicated.instanceName}}.

5. Click the **Resource Group** pull-down menu.
6. Select the **{{itz.resourceGroup}}** option.

### NEED TO DISCUSS INSTANCE TYPES

### NEED TO DISCUSS LICENSING

7. Click **Licensing** in the left-hand menu.
8. Under the **NSX** section, click the pull-down menu that currently shows **Data Center SP Professional**.
9. Select the **Data Center SP Advanced** option.

In this deployment, a single **Consolidated** cluster will be used. **Consolidated** clusters are used for both the management components of the VCS deployment as well as client workloads. This is typically fine for small deployments, and will potentially save the client some money.  However, for larger deployments with varying performance requirements for workloads, separating the management cluster from other workload clusters is the preferred architecture. Refer to the documentation for more details on management and workload clusters <a href="https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-consoli" target="_blank">here</a>.

Later the other options for to provision dedicated **Workload** and **Edge services** clusters will be explored, but for this environment a single **Consolidated** cluster is used.

10. Under **Data center location**, click the **Geography** pull-down menu that currently shows **NA South**.

Notice, VCS instances can be deployed in many of the IBM Cloud data centers located around the world.

11. Select the **NA West** option.
12. Select the **SJC04** data center option.

Next, a hardware configuration for the bare-metal servers needs to be specified. VCS can be provisioned on many different hardware configurations, including SAP certified hardware.

11. Click the **Dual Intel Xeon Silver 4210** radio button in the **CPU model** table.
12. Click the **RAM** pull-down menu that currently shows **768 GB**.
13. Select the **128 GB** option.


### NEED TO DISCUSS # of servers, storage, vsan/nfs, shares, network type, uplink speeds, and vlans


14. Click the **Include a separate, additional workload cluster.** checkbox.

Notice the form expands to allow a new hardware configuration to be specified for a separate **Workload** cluster just like for the **Consolidated** cluster. If a client desires to separate their workload cluster from the management cluster, this option should be selected. Often clients will opt for multiple workload cluster based upon the CPU, memory, and storage requirements of the workloads.

15. Click the **Include a separate, additional workload cluster.** checkbox again to disable the separate **Workload cluster**.
16. Click the **Edge services cluster** checkbox.

A dedicated **Edge services** cluster is often desirable for large deployments that require additional separation of the edge services and custom firewall components. Notice the hardware options for the **Edge services** cluster are fewer than for the **Consolidate** and **Workload** clusters.

16. Click the **Edge services cluster** checkbox agin to disable the separate **Edge services cluster**.
17. Click the **Domain name** text entry field under the **Network interface** section.

### NEED TO DISCUSS DNS CONFIGURATION OPTIONS

A valid **Domain name** needs to be specified for the VCS deployment. The Domain name field will automatically change to **myroot.mydomain.com** for this environment. Notice how both the **Hostname prefix** and **Domain name** fields are used to specify the complete hostnames for the bare-metal servers. The **Configure host names individually** checkbox can be used for clients that desire to specify hostnames individually.

18. Click the **Add-on services** option in left-hand menu.

### intro to additional Services

19. Click the **Edit** link in the **Veeam 11** tile under **Recommended services**.

## discuss Veeam

20. Click the **Name** text entry field in the **Configure Veeam** dialog.

The **Name** field will automatically change to **veeam-l3**.

21. Click the **Storage size** pull-down menu that currently shows **4000 GB**.
22. Select the **2000 GB** option.


## discuss sizing veeam

23. Click the **Storage performance** pull-down menu that currently shows **0.25 IOPS/GB**.

## discuss storage performance

24. Select the **0.25 IOPS/GB** option.
25. Click **Save**.
26. Click the **Edit** link in the **Caveonix RiskForesight 4.0.0** add-on services tile.

## discuss Caveonix

27. Click **Cancel**.
28. Click the toggle switch in the **Caveonix RiskForesight 4.0.0** add-on services tile to disable Caveonix.
29. Click the **Business continuity and migration** pull-down menu.

## discuss HCX and Zerto

30. Click the **Business continuity and migration** pull-down menu again.
31. Click the **Security and compliance** pull-down menu.

## discuss Entrust, F5, Fortigate, and Juniper

32. Click the **Security and compliance** pull-down menu again.
33. Click the **Transformation and modernization of VMware applications** pull-down menu.

## discuss Openshift

34. Click the **Transformation and modernization of VMware applications** pull-down menu again.
35. Click the **Management tools** pull-down menu.

## discuss vROPS and Log Insight

35. Click the **Management tools** pull-down menu again.
36. Click the **I understand that the account listed below will be charged for infrastructure** checkbox.
37. Click the **I have read and agreed to the third-party service agreements listed below** checkbox.
38. Click **Create**.

Notice the messages being displayed. The status of the provisioning process can be observed.

39. Click **Resources** in left-hand menu.
40. Click **vCenter Server** under **Resources** in left-hand menu.
41. Click the **{{itz.dedicated.instanceName}}** in the table.

Notice the **Creating** status at the top of the screen by the instance name.

42. Click the **Infrastructure** option in left-hand menu.

Notice the single, consolidated cluster requested earlier listed in the table and the status is **Initializing**.

43. Click the **Deployment history** option in left-hand menu.

Notice the steps and timestamps as the VCS instances is being provisioned.
Now, fast forward 11 hours.

44. Click anywhere on the screen.

Notice 11 hours has elapsed and the VCS instance is now ready to use. Proceed to the next chapter of this demonstration script to learn how to manage a VCS instance.
