Deciding on *what* to demonstrate to a client can be a daunting task, especially with a complex offering like IBM Cloud for VMware Solutions. In planning a demonstration, consider:

- The client's business and industry.
- The client's business challenges and needs.
- The role of individuals in the audience (for example, are they C-level executives, technical-level, or both).
- What VMware offerings is the client most interested in (VMware Cloud Foundation [VCF] for Classic, VCF as a Service multitenant, or VCF as a Service single-tenant)?
- Are there specific use cases that the client is interested in?
- How much time is allotted for the demonstration?
- What questions will the audience ask?
- What challenges will the audience present?

The more information and answers to these and other questions you have, the easier it is to develop the story you want to demonstrate to the client. 

As an example, if the client is interested in a disaster recovery solution for a subset of their on-premises VMware workloads, consider demonstrating the capabilities of VCF as a Service multitenant with reserved capacity. But for a client needing to vacate a data center with a large VMware footprint, VCF for Classic may be a better fit. 

And as mentioned, knowing the roles of the audience is important. You need to address and demonstrate at the right level of detail. You need to explain the benefits of the solution so they resonate with the audience's roles.

Demonstrating *infrastructure* solutions is challenging. If the benefit you want to highlight is the ease of deploying complex environments, you must consider the time it takes to deploy the solution. VCF for Classic can take half a day or longer to provision. The best demonstration solution in these cases is using a "baking show" approach. In baking shows on television, the chef walks through the steps to prepare a dish and then slide it in the oven. But instead of waiting 30-40 minutes for it to cook, the chef pulls out one that is already fully baked to show the audience. This approach works well for demonstrating the ease of making a provisioning request for a cloud-based solution. Instead of waiting for the new infrastructure to provision, you switch to an already provisioned instance. The click-through demonstrations in this learning plan can be used for this type of demonstration or the IBM Cloud Portal can be used to the point of clicking create, and then switching to the already provisioned instance.

The other challenge is focusing the demonstration on the added value of the solution on IBM Cloud versus the value of the end product, in this case VMware. As seen in the previous modules, after a VCF for Classic or VCF as a Service instance is provisioned, there are management capabilities that IBM Cloud provides that add value over on-premises or hosted solutions. For a technical audience, show VMware vCloud Director (VCD) to highlight the fact that it is VCD as they know it and their skills and processes work the same in IBM Cloud as they do on-premises.

A few high-level demonstrations to consider:

- **VCF as a Service multitenant**
    - Client's need:
        - Meet business growth demands
        - No increase in VMware administration headcount
        - Reduce costs
    - Goals:
        - Ease of provisioning VCF as a Service instance
        - Ease of controlling costs and consumption
        - Minimal VMware admin requirements
    - Benefits:
        - Rapid deployment
        - Ease of scale
        - Ability to easily manage consumption limits
    - Demonstration method:
        - Baking show demonstration with pre-provisioned IBM Technology Zone environment
        - Show information required to provision a VCF as a Service multitenant instance
        - Show how to adjust consumption limits
        - Access VCD and deploy a VM
        - Use Veeam add-on service to easily protect data
  
- **VCF for Classic**
    - Client's need:
        - Move to cloud
        - Data center evacuation
    - Goals:
        - Ease of provisioning a complete VCF stack based on clients needs
        - Ease of growing the deployment on demand
    - Benefits:
        - Rapid deployment
        - Elasticity and cloud pricing model
        - Preserve current VMware skills and processes
    - Demonstration method and flow:
        - click-through demonstrations to provision and then manage a VCF for Classic instance
    
Mock client demonstrations are available in the {{learningplan.name}} learning plan in YourLearning (for IBMers) and learn.ibm.com (for Business Partners). 

In preparing for a client demonstration, or for IBMers doing their stand and deliver recording, don't wait to the last minute. Make sure the IBM Technology Zone (ITZ) environment that you need is up and running and the reservation is not about to expire. If the demonstration is to be given virtually, make sure everything works with the e-meeting technology you are using. For those demonstrating VCF for Classic, a second version of the **Managing an instance of VCF for Classic** is available. In this version, a menu allows you to quickly jump to key locations in the demonstration. A home, back, and forward button located in the lower-left of all subsequent slides provide quick navigation.

**Click-through demonstration with a start menu:** <a href={{clickthru.vcsManagingMenu}} target ="_blank">Managing an instance of VCF for Classic</a>

Make sure that you practice the demonstration flow. There is nothing more embarrassing than a demonstration that fails. Know the steps that you are going to take. Know what you will say. Plan on handling errors that might occur. If you are using the "baking show" approach, practice what you will say in the transition from canceling the creation of a resource to moving to a fully provisioned instance. And most importantly, practice, practice, practice.
