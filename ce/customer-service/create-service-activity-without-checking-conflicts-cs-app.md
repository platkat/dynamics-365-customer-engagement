---
title: Force an activity into a time slot (Dynamics 365 for Customer Service) | MicrosoftDocs
description: See how to force an activity into a time slot in Dynamics 365 for Customer Service
keywords: Force an activity; Dynamics 365 for Customer Engagement; Customer Service; Service schedule
author: anjgupta
applies_to: 
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
ms.author: anjgup
manager: shujoshi
ms.date: 06/01/2018
ms.topic: article
ms.service: dynamics-365-customerservice
ms.assetid: e2050e36-3e95-49b1-9f2b-f0025eb7022c
ms.custom: dyn365-customerservice
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365CS
---

# Force an activity into a time slot in the service schedule (Customer Service app)

You can create a service activity by finding the next available times of resources for a service or simply without checking for conflicts. If needed, you can force a service activity into a time slot to squeeze another service activity into the leftover time from a previous service activity. If you save a service activity without finding available times in the schedule, then [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] displays the service activity in the schedule without checking for conflicts.  
  
 One reason to force a service activity into a time slot is to squeeze another service activity into the leftover time from a previous service activity.  
  
1. Make sure you have the Scheduler security role or equivalent permissions in Microsoft Dynamics 365 for Customer Engagement.  
  
2. [!INCLUDE[proc_service_service_calendar](../includes/proc-service-service-calendar.md)]  
  
3. On the command bar, select **Service Activity**.  
  
4. On the Service Activity form, type or change information in the text boxes.  
  
    Hovertips provide hints on what to enter.  
  
5. When you’re ready to save your data, select **Save**.  
  
> [!TIP]
>  You can record a customer's preferences for a specific time, day, service, facility, equipment, and customer service representative in the customer record on the **Administration** tab. As you are scheduling a service activity, the customer's preference is displayed in the **Form Assistant** pane.  
  
> [!NOTE]
> - If at any time before you save this service activity you want to search the schedule for an available time, you can select **Schedule** in the **Actions** group to open the **Schedule Service Activity** dialog box.  
> - To check the schedule for conflicts, in **Service Calendar**, in the **Actions** group, select **Conflicts**.  
  
### See also  

[Overview of service and service scheduling](basics-service-service-scheduling.md)   
