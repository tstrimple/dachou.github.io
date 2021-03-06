---
layout: post
title:  "Supply Chain Management Solution in Windows Azure (PDC2008)"
date:   2009-01-01 12:00:00 -0700
---

On November 3, 2008, Microsoft Chief Software Architect Ray Ozzie introduced Windows Azure and Azure Services Platform during the PDC2008 opening keynote. I played a small role as part of the team ([more details here]({{ site.baseurl }}{% post_url 2008-12-01-meba %})) that spent a couple of months earlier in the year working on one of the projects demonstrated during the day 1 keynote presentation. 

Specifically, it was the RedPrairie supply chain management solution discussed during Bob Muglia's (Senior Vice President of the Server and Tools Business) keynote (fast forward to about 48 minutes into the video at <https://channel9.msdn.com/Blogs/pdc2008/KYN01>).

![redprairie](/assets/20081103-redprairie-architecture.png)

This wasn't a world-changing event like Apple's announcement of the iPhone, and probably a scenario that not a lot of people are familiar with, but it addresses a real business need in the supply chain management space, and how the cloud can serve as an effective solution for the currently fragmented landscape of B2B business processes.

![b2b scm landscape](/assets/20081103-b2b-landscape.png)

There's a more detailed discussion of the challenges in the earlier post about [Multi-Enterprise Business Applications]({{ site.baseurl }}{% post_url 2008-12-01-meba %}). Basically, the current B2B business process domain is fraught with a diverse set of standards and protocols, a myriad of technologies, and each widely varied custom implementations at each of the many organizations involved in a supply chain relationship.

From a supply chain management persective, when a manufacturer needs to issue a recall, it often requires sending out information to thousands of partners and customers in a very timely fashion, while meeting compliance requirements for managing and monitoring the process, so they understand what the overall impact of the recall will be. Adding to the challenge is the custom communications infrastructure, such as VPNs and dedicated circuits, that are used to communicate with partners. These one-to-one connections are very costly to deploy and maintain for everyone.

The cloud provides an effective solution in helping to centralize and minimize the custom work each organization has to implement, in order to communicate with others. For example, with buiness processes managed in the cloud, organizations only need to implement the necessary communication protocols and security measures with the cloud platform (in this case one-to-one with Windows Azure), as opposed to needing to do something customized for each organization (many-to-many).

![one button recall architecture](/assets/20081103-onebuttonrecall-architecture.png)

Here we have Contoso which is a (fictional) company that manufactures batteries. They use the RedPrairie software running on-premises, from which we can initiate a product recall with their supply chain partners. At the click of the "Recall" button, the application initiates a recall by submitting a message to the .NET Service Bus, operating in Windows Azure, which then relays the message to the .NET Workflow Service, also in the cloud, which sends out recall notifications to all of the warehouses, distribution centers, and stores that have this item. Windows Azure's .NET Services handles all this communications and routing.

The process demonstrated in this "One Button Recall" solution used these services in Windows Azure:
- .NET Service Access Control
- .NET Service Workflow Services
- .NET Service Bus
- SQL Data Services

The RedPrairie Cloud-Based "One Button Recall" solution demonstrated in the keynote represents a multi-enterprise business application that leverages Windows Azure, to deliver a sophisticated product recall orchestration between multiple partners (in this case - AdventureWorks, Contoso, Fabrikam, and Litware) in a dynamic supply chain network. The cloud services implementation helps articulate business and technical values of the S+S model, and how the cloud services platform add value to RedPrairie’s current software solutions, by connecting, managing, and interacting with on-premise solutions across enterprise boundaries.

Again, this is a neat scenario because it isn't about running existing server-based software in the cloud (treating it as another outsourced hosting service). RedPrairie's existing business product management software can continue to run on-premises to orchestrate the process across the multiple partners (who also have their software still running on-premises), but the communication, authentication, authorization, and message orchestration can be implemented and managed in the cloud, simplifying the solution each organization needs to implement in order to automate the entire supply chain.

