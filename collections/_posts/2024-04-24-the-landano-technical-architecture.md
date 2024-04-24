---
layout: post
title: Technical architecture update
date: 2024-04-15T10:05:00.000Z
image: /assets/uploads/screenshot-2024-04-23-at-5.25.02 pm.png
thumbnail: /assets/uploads/screenshot-2024-04-23-at-5.25.02 pm.png
categories:
  - development
  - Cardano
  - project
---
Landano is a software platform for creating and managing decentralized land right records using the [Cardano](https://cardano.org) blockchain.

We created a proof-of-concept application during Landano’s kick-off stage in 2022. We eased from software development in 2023 to focus on better understanding our potential user base, business opportunities, and matching up to investor profiles. We’ve summarized a lot of that activity in this [update video](https://youtu.be/m8eFfN4BBsw?si=tsHOEfJsMKsBcyYs).

The Landano project is now ready to combine these efforts into a Minimum Viable Product that will perform core Landano functions on Testnet first before launching on Cardano Mainnet for our users in Ghana and Mozambique. 

This is a good time to check-in behind the curtains and get a better understanding of the technology architecture we’re implementing to deliver the Landano software platform in 2024.

## The Mendix solution

The Landano MVP we created in 2022 was developed using the [Mendix](https://www.mendix.com/) low-code platform. Our CTO Dorus van der Kroft is a senior Mendix consultant and is leading the development and implementation of the Landano software. Over the course of the past two years we did investigate a number of other candidate technologies on which to build our off-chain components to interact with our on-chain Cardano code. However, Mendix is the right fit for a platform like ours, which we consider to be in the enterprise software market, given that we intend to onboard millions of users. 

Mendix is primarily used to create and manage large portfolios of business-critical applications across organizational and technical boundaries. It is an integrated application platform-as-a-service (aPaaS) offering for designing, building, deploying, and managing enterprise apps. Mendix is classified by [Gartner](https://www.mendix.com/evaluation-guide/gartner-forrester-mendix/) as a low-code application platform that solves complex software development at scale and with speed. 

Mendix applications are cloud native by default making all components built on the platform very scalable, resilient, and portable. The low-code methodology also means developers can use Mendix to deliver software quickly to ensure that products and services are brought to market faster while optimizing operational processes.

![The Mendix platform](/assets/uploads/screenshot-2024-04-23-at-5.26.23 pm.png "The Mendix platform")

\
The platform is accessible to developers and administrators through the Developer Portal, which provides access to apps as well as services for requirements management, development, and deployment in the operation and administration of apps and app services. The platform includes Mendix Studio Pro as well as the Mendix Marketplace, which features hundreds of publicly available building blocks to speed up development. 

The Landano project received a Project Catalyst [Fund 11 grant](https://cardano.ideascale.com/c/idea/112624) recently to leverage the work we have done so far with our Landano platform to create generic Cardano plugins for the Mendix Marketplace using our Landano code. This will allow the large ecosystem of Mendix enterprise developers to use Cardano NFTs and smart contracts from within the Mendix development environment directly. This sub-project holds a lot of potential for bringing in new enterprise software development talent into the Cardano ecosystem.

Mendix allows our Landano team to develop on one core code base and use it to deliver both desktop and mobile applications. You can find the most recent version of our mobile apps in this [Github repo](https://github.com/landano/resources). Keep in mind that this is still the experimental proof-of-concept version at the moment.

## \
Deployment architecture

Mendix Cloud is a PaaS-based cloud offering based on Cloud Foundry technology that runs on the IaaS layer of Amazon Web Services. 

![Mendix deployment architecture](/assets/uploads/screenshot-2024-04-23-at-5.30.45 pm.png "Mendix deployment architecture")

Our Landano Mendix application runs in a container provided by Cloud Foundry. These have standard support for horizontal and vertical scaling as well as auto-healing. Scaling up and down can be done without any downtime by simply adding or removing containers. The Mendix Cloud Foundry layer is deployed in multiple availability zones for each AWS region. An availability zone is a physical data-center location of AWS within a region.

A Mendix application needs a database and file storage to operate. In the Mendix Cloud, these aPaaS services are directly consumed from the AWS service layer. For the database, the Mendix Cloud makes use of RDS PostgreSQL, and for the file storage, it makes use of S3. Both of these services are Multi-AZ configured, so data is replicated across data centers.\
\
All this Mendix infrastructure is used as a processing pipeline for the Landano application modules. There are no permanent records stored within the Mendix platform. The records generated by Landano are stored as Cardano NFTs with supporting documentation packages provided on the permissionless Arweave storage network. This is described further below.

The Landano platform and the Mendix plug-ins we are creating allow low-code developers to combine the best of battle-tested enterprise software with the trust guarantees provided by the decentralized Cardano blockchain through its eUTXO NFTs and smart contracts.
