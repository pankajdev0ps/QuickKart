# Challenge 1: Understand the Business Problem and Design a High-level Architecture Diagram.

## Problem Statement:
Peter, the Chief Technical Officer (CTO) and Vice President of Engineering at Quick-Kart E-commerce, wants to employ cloud services for their application, relieving Quick-Kart E-commerce of any need for on-premises hardware. 

Their infrastructure team and software developers are well-versed in using Azure services (IAAS) and want to take advantage of this chance to create a cutting-edge product that may serve as a roadmap for later employing PAAS to modernize their current applications and infrastructure.

Though the Quick-Kart architects have outlined a high-level overview of their ideal API, there is still skepticism within the group over the methods they ought to employ for endpoint construction and access.  

The Quick-Kart engineers have some experience working with.NET MVC and Web API apps, thus the architects think an HTTP-based REST API using traditional endpoints like GET and POST would be best.  The architects have all agreed that they will heavily rely on Microsoft's recommendations because they are not as comfortable as they would like to be with Azure services. 

All of them are certain that their software developers could handle either REST API, but they all want to learn about best practices and grasp what functions in Azure the most effectively.

The backend application would like Quick-Kart E-commerce to manage a single API. 

For a proof of concept, Quick-Kart E-commerce would want to have two endpoints implemented: one used for sign-in and one used for backend. In reality, QuickKart E-commerce anticipates something in the range of 15 to 20 endpoints to accommodate the breadth of their application suite. All customer orders should be managed by Quick-Kart E-commerce in guaranteed FIFO sequences.

Beyond what you develop for the proof of concept, Quick-Kart software developers are expected to implement all API endpoints for the application; however, different endpoints may be implemented over time by several independent teams. 

The goal of Peter and the architects was to make this system as easy to operate as feasible. Although the Engineering department has an operations team, that group frequently feels overburdened with current responsibilities and has very little time to manage new software solutions.  The ideal situation would be for the software engineers to be able to instrument, oversee, and manage these endpoints on their own, but Quick-Kart E-commerce currently lacks a strong DevOps culture. While they are headed in that path, they would value any tools, procedures, or product choices that would make the instrumentation, monitoring, and management processes for their software developers simpler.

## Task
1. Form a team of 4 members
2. Desing a High-Level Architecture Diagram