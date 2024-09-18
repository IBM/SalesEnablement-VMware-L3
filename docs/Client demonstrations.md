Deciding on *what* to demonstrate to a client can be a daunting task, especially with a complex offering like IBM Cloud for VMware Solutions. When designing your demonstration, here are a few things to consider:

- The client's business and industry.
- The client's business challenges and needs.
- The role of individuals in the audience (for example, are they C-level executives, technical, or both).
- What VMware offerings will the client be most interested in (VMware Cloud Foundation [VCF] for Classic, VCF as a Service multitenant, or VCF as a Service single-tenant)?
- Are there specific use cases the client is interested in?
- How much time is alloted for the demonstration?
- What questions do you anticipate the audience asking?
- What challenges do you anticipate the audience presenting?

The more information and answers to these and other questions you have, the easier it will be to develop the story you want to demonstrate to the client. 

As an example, if the client is interested in a new disaster recovery solution for a small sub-set of their on-premises VMware workloads, you may want to demonstrate capabilities around VCF as a Service multitenant with reserved capacity. But for a client needing to vacate a data center with a large VMware footprint, VCF for Classic may be a better fit. 

And as mentioned, knowing the roles of the audience is important. You need to address the demonstrate at the right level of detail and the benefits of the solution that will best resonate with the audience's roles.

Demonstrating *infrastructure* solutions is challenging. If the benefit you want to highlight is the ease of deploying complex environments, like VCF for Classic or maybe some deployable architecture in iBM Cloud, you must consider the time it takes to deploy the solution. In the case of VCF for Classic, it can take half a day more more. The best demonstration solution in these cases is using a "baking show" approach. In baking shows on television, the chef will walk through the steps to prepare a dish and then slide it in the oven. But instead of waiting 30-40 minutes for it to cook, the chef pulls out one that is already fully baked to show the audience. This approach works well for demonstrating the ease of making a provisioning request for a cloud-based solution and then instead of waiting for the new infrastructure, you switch to an already provisioned instance. The click-through demonstrations in this learning plan can be leveraged for this type of demonstration or the IBM Cloud Portal can be used up to the point of clicking create, and then switching to the already provisioned instance.

The other challenge is focusing the demonstration on the value add of the solution running on IBM Cloud versus the value of the end product, in this case VMware. As you saw in the previous modules, once a VCF for Classic or VCF as a Service instance is provisioned, there are management aspects that IBM Cloud provides that add a lot of value versus on-premises or hosted solutions. These are the benefits to focus on versus just demonstrating that you can create a VM in VMware vCloud Director (VCD). For a technical audience, you may still want to show that step, just to highlight the fact it is VCD as you know it and your skills and processes work the same in IBM Cloud as they do with their on-premises deployments.

Here are just a few high-level demonstration flows you may want to consider:

- **VCF as a Service multitenant**
    - Client's need:
        - Meet business growth demands
        - No increase VMware administration headcount
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
        - Access vCloud director and deploy a VM
        - Utilize Veeam add-on service to easily protect data
  
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
    
Mock client demonstrations of both to these are available in the {{learningplan.name}} learning plan in YourLearning (for IBMers) and learn.ibm.com (for Business Partners). 

When preparing for a client demonstration, or for IBMers doing their stand and deliver recording, don't wait to the last minute. Make sure the IBM Technology Zone (ITZ) environment that you need is up and running and the reservation is not about to expire. If the demonstration is to be given virtually, make sure everything works with the e-meeting technology you are using. For those demonstrating VCF for Classic, a second version of the **Managing an instance of VCF for Classic** is available. In this version, there is a menu to allow you to quickly jump to key locations in the demonstration. In addition, there are home, back, and forward buttons located in the bottom left corner of all subsequent slides for quicker navigation.

**Click-through demonstration with a start menu:** <a href={{clickthru.vcsManagingMenu}} target ="_blank">Managing an instance of VCF for Classic</a>

Make sure you practice the demonstration flow. There is nothing more embarrassing than a demonstration that fails. Know the steps that you are going to take. Know what you will say. Plan on handling errors that might occur. If you are using the "baking show" approach, practice what you will say in the transition from canceling the creation of a resource to moving to a fully provisioned instance. And most importantly, practice, practice, practice.
