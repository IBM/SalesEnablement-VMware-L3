![type:video](./_videos/VMware L3 Welcome.mp4)
!!! tip "WAYS TO WATCH"
    In addition to the embedded video, IBMers and Business Partners can also <a href="https://ibm.seismic.com/Link/Content/DCFGW2RT6jVGm82VTDMJ6TdDJC4V" target="_blank">download the recording from Seismic</a>.

Welcome to the **IBM Cloud for VMware Solutions - Level 3** course and demonstration guide! The goal is to provide IBM and Business Partner Sales and Technical Sales with the knowledge and tools to perform click-thru demonstrations of **VMware Shared** and **VMware Dedicated** plans via the IBM Cloud.

!!! warning "LIMITED ACCESS"
    For this Level 3 course, full access to a live IBM Technology Zone or IBM Cloud account is **NOT** provided, due to the potentially high costs this may incur and the challenges with providing a multi-tenant VMware environment across a global audience of sellers and business partners. Instead, click-thru demos and recorded walkthroughs have been provided to simulate a live VMware Solutions instance.

    Participants can leverage the click-thru demos in front of clients as part of a "live" demonstration; similarly, IBM Sellers and Technical Sellers can use the demos for recording a Stand & Deliver presentation for their Level 3 accreditation.

There are four flavors currently provided for VMware on IBM Cloud: ```VMware Shared```, ```VMware as a Service```, ```VMware vSphere```, and ```VMware vCenter Server```. For the purposes of this Level 3, we will delve deeply into the IBM Cloud elements of the ```VMware Shared``` and ```VMware Dedicated``` instances. This course is not intended to serve as a deep dive into VMware-specific topics. Numerous links and pointers to additional context around VMware-specific features have been peppered into each of the chapters and modules of this course. However, for the purposes of this Level 3 accreditation, the topics and demonstrations covered by the coursework will focus squarely on how to provision and manage VMware Solutions on the IBM Cloud.

All modules are accompanied by recordings and narrated instructions, delivered by your team of authors. Be sure to watch these for a visual demonstration of how to perform the hands-on lab components. In particular, it is strongly recommended that IBM Sellers and Technical Sellers watch these recordings — they will be useful for you as you go about creating and recording your own Stand & Deliver presentations for Level 3 accreditation.

!!! tip "ACCREDITATION"
    To receive Level 3 accreditation, IBMers and Business Partners must demonstrate mastery of the skills learned throughout the various modules of these hands-on labs and coursework. Level 3 accreditation requirements— and the way participants will be evaluated before receiving accreditation —differs depending on job role.

**Business Partners** must pass an accreditation quiz after completing the hands-on portion of the course. The quiz consists of multiple choice questions, with four possible responses (and only one correct answer) for each question.

**IBM Sales and Tech Sales** must develop and record a Stand & Deliver presentation. This video is intended to simulate your delivery of a “live” demo in front of a client — on camera. IBMers will have flexibility in defining a hypothetical client, the pain points that customer has, and the goals they aspire to achieve. The recording will then cover the seller’s hands-on demonstration and pitch to the client of the value of the IBM solution using the environments and techniques of this lab.

Specific criteria that must be demonstrated as part of the Stand & Deliver recordings is provided within the documentation that accompanies the Level 3 course. Before jumping into the next module, please read the guidance below. Your comprehension of the information outlined below will save you time while completing the lab work.

!!! tip "FIND HELP"
    If at any point during the hands-on material you need help from the team of authors and other IBM experts, please connect with us via the #cloud-platform-demo-feedback Slack channel. Any comments or suggestions are also welcome in this channel.

#
# Navigating the Lab Guide
-----------------------------

The Level 3 demonstration guide is organized into two chapters, covering ```VMware Shared``` and ```VMware Dedicated``` plans respectively, of the **IBM Cloud for VMware Solutions** offering. Both chapters contain modules that provide an *Introduction* to offering, provide an overview on how to *Provision* a deployment, and explore the ways into which clients are *Managing* their instance through the vCloud Director console. Most chapters contain numbered steps, which are actions to be performed.

Throughout the guide, images are used as examples of the IBM Cloud Portal and vCloud Director web-based console.

!!! warning "WARNING"
    The agile nature of cloud means that the interface and layout of the IBM Cloud Portal, as well as the IBM Cloud for VMware Solutions offering, will change on a regular basis. Screenshots and videos captured within this documentation may not always reflect the latest versions available from IBM Cloud — although we strive to the best of our abilities to update these assets with changes as they roll out.

In some images, the following styles of highlighting are utilized:

- **Action highlight box**: Illustrates where to click, enter, or select an item.
![](_attachments/welcome-1.png)

- **Path/explore highlight box**: Illustrates one of two things: the path to follow to get to a specific location in the user interface; or areas to explore.
![](_attachments/welcome-2.png)

- **Copy to clipboard box**: The text is copied to the clipboard. Click the copy icon (highlighted below) and then paste using the operating systems paste function; for example, entering ```Ctrl+v```, ```Cmd+v```, or right-click and select ```Paste```.
![](_attachments/welcome-3.png)

- **Click-thru interactive demonstrations**: Links to click-thru demonstrations will open in a new browser window or tab with a screen similar to the image below. Click the ```(>)``` icon to get started and follow the steps outlined within this L3 demonstration guide. If unsure of where to click to proceed, click anywhere on the screen and a highlight box will appear indicating where to click next.
![](_attachments/welcome-4.png)


#
# Acronyms
-----------------------------

The following acronyms and short-form terminology are used throughout the guide:
```
Application programming interfaces (APIs)
Classless inter-domain routing (CIDR)
Control (ctrl) - The control key on keyboard
Command (cmd) - The command key on keyboard
Disaster Recovery (DR)
Gigabyte (GB)
High Availability (HA)
IBM Cloud Object Storage (COS)
IBM Power Systems Virtual Server (PowerVS)
IBM Technology Zone (TechZone)
Infrastructure as a Service (IaaS)
Input/output operations per second (IOPs)
Internet Protocol (IP)
Operating System (OS)
Random access memory (RAM)
Reliability, Availability, and Serviceability (RAS)
Secure Socket Shell (SSH)
User identification (ID)
Virtual Machine (VM)
```
