---
layout: post
title: The Landano technical architecture
date: 2024-04-15T10:05:00.000Z
image: /assets/uploads/2024-04-23-landano-technical-architecture-v1.jpg
thumbnail: /assets/uploads/2024-04-23-landano-technical-architecture-v1.jpg
---
Landano is a software platform for creating and managing decentralized land right records using the [Cardano](https://cardano.org) blockchain.

We created a proof-of-concept application during Landano’s kick-off stage in 2022. We eased from software development in 2023 to focus on better understanding our potential user base, business opportunities, and matching up to investor profiles. We’ve summarized a lot of that activity in this [update video](https://youtu.be/m8eFfN4BBsw?si=tsHOEfJsMKsBcyYs).

The Landano project is now ready to combine these efforts into a Minimum Viable Product that will perform core Landano functions on Testnet first before launching on Cardano Mainnet for our users in Ghana and Mozambique. 

This is a good time to check-in behind the curtains and get a better understanding of the technology architecture we’re implementing to deliver the Landano software platform in 2024.

## The Mendix solution

The Landano MVP we created in 2022 was developed using the [Mendix](https://www.mendix.com/) low-code platform. Our CTO Dorus van der Kroft is a senior Mendix consultant and is leading the development and implementation of the Landano software. Over the course of the past two years we did investigate a number of other candidate technologies on which to build our off-chain components to interact with our on-chain Cardano code. However, Mendix is the right fit for a platform like ours, which we consider to be in the enterprise software market, given that we intend to onboard millions of users. 

Mendix is primarily used to create and manage large portfolios of business-critical applications across organizational and technical boundaries. It is an integrated application platform-as-a-service (aPaaS) offering for designing, building, deploying, and managing enterprise apps. Mendix is classified by [Gartner](https://www.mendix.com/evaluation-guide/gartner-forrester-mendix/) as a low-code application platform that solves complex software development at scale and with speed. 

Mendix applications are cloud native by default making all components built on the platform very scalable, resilient, and portable. The low-code methodology also means developers can use Mendix to deliver software quickly to ensure that products and services are brought to market faster while optimizing operational processes.
