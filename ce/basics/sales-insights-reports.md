---
title: "Sales insights reports (Dynamics 365 for Customer Engagement) | MicrosoftDocs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.service: crm-online
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
applies_to: 
  - Dynamics 365 for Customer Engagement apps
  - Dynamics 365 for Customer Engagement Version 9.x
ms.assetid: d8029ee8-6c19-4ce8-96eb-3a74b48c4d37
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: brycho
search.audienceType: 
  - enduser
search.app: 
  - D365CE
---
# Reports for sales insights

[!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] includes many system reports that you can use to gain insights into how your business is doing. You can use these reports as is or customize them for your needs. For more information about customized reports, see [Customize and organize reports](../customize/customize-organize-reports.md). The following will provide insights into your sales efforts: 

|Description|More information|  
|-----------------|----------------------|  
|Sales team performance against competitors|[Competitor Win Loss report](#BKMK_CompetitorWinLoss)|  
|Activity patterns|[Activities report](#BKMK_Activities)|  
|Sales progress against goals|[Progress Against Goals report](#BKMK_ProgressGoals)|  
|Sales performance of reps|[Sales History report](#BKMK_SalesHistory)|  
|Potential sales opportunities|[Sales Pipeline report](#BKMK_SalesPipeline)|  
|Compare effectiveness of lead sources for generating opportunities|[Lead Source Effectiveness report](#BKMK_LeadSource)|  
|Leads that haven’t been contacted|[Neglected Leads report](#BKMK_NeglectedLeads)|  

<a name="BKMK_CompetitorWinLoss"></a>   
## Competitor Win Loss report
Use this report to compare how your sales team performs against your competitors. The report displays opportunities that have competitors associated, with information on open, closed, won, and lost opportunities.  
  
 The report displays only opportunities that have competitors associated that you have permission to see, in the country/region and time period that you specify.  
 
<a name="BKMK_Activities"></a>   
## Activities report
Get a quick view of all the activities associated with opportunities such as phone calls, tasks, emails, appointments, and closed opportunities.  Use the information in this report to look at the details of each activity and identify patterns to make improvements in how you work to turn opportunities into leads, and leads into closed deals.  
  
 When you run the report, choose **Show All** to get a detail view of all the activity. Activities can be grouped by owner or activity type, or by the record the activity is associated to.  
  
 ![Exmple of an Activities Report in Dynamics 365 for Customer Engagement](../basics/media/activities-report.png "Exmple of an Activities Report in Dynamics 365 for Customer Engagement")  
  
<a name="BKMK_ProgressGoals"></a>   
## Progress Against Goals report
The information in this report helps you see how your sales team is performing against their sales goals. This report displays a chart of your target goals and your actual goals.  
  
> [!NOTE]
>  The report is generated from data that is rolled up to the goals at a set time. If the data is not up-to-date, then wait until the next time the data is rolled up. For more information, contact your Dynamics 365 for Customer Engagement appsadmin.  
  
 ![Progress Against Goals Report in Dynamics 365 for Customer Engagement](../basics/media/progress-against-goals-report.png "Progress Against Goals Report in Dynamics 365 for Customer Engagement")  

<a name="BKMK_SalesHistory"></a>   
## Sales History report
Use this report to see how your sales reps have performed and how much revenue they have generated for your business. See which sales reps closed the most sales – so you can award them for their great work. And also see which opportunities were lost so you can help your sales team do better next time.  
  
 The report uses data from closed opportunities that were either won or lost and then calculates earned and lost revenue.  
  
 ![Sales History report in Dynamics 365 for Customer Engagement](../basics/media/sales-history-report.png "Sales History report in Dynamics 365 for Customer Engagement")  

<a name="BKMK_SalesPipeline"></a>   
## Sales Pipeline report
Use the information in this report to forecast future revenue and set goals for your sales team.   
The report helps you see expected potential sales opportunities. The report displays a chart  
 of potential sales grouped by user, sales territory, customer territory, date, products, rating, or sales stage.  
  
 When you run the report, on the chart, click **Show All** to get a detail view of the report.  
  
 ![Sales Pipeline Report in Dynamics 365 for Customer Engagement](../basics/media/sales-pipeline-report.png "Sales Pipeline Report in Dynamics 365 for Customer Engagement")  

<a name="BKMK_LeadSource"></a>   
## Lead Source Effectiveness report
Find out which type of lead is most beneficial in helping you grow your business. This report helps you compare how effective your lead sources are at generating quality opportunities.  
  
 The report lists the percentage of qualified leads, and leads that generate revenue for each lead category.  
  
 ![Lead Source Effectiveness report in Dynamics 365 for Customer Engagement](../basics/media/lead-source-effectiveness.png "Lead Source Effectiveness report in Dynamics 365 for Customer Engagement")  
  
<a name="BKMK_NeglectedLeads"></a>   
## Neglected Leads report
Keep your sales teams on the alert for possible business opportunities.   
Use this report to have your sales team follow-up on leads that they haven’t contacted in a while.  
  
 When you run the report, specify the number of days that leads have been neglected.   
The report displays a chart of active leads that have had no activities or notes.   
Click **Show All** to drill down into the report.  
  
 ![Neglected Leads Report in Dynamics 365 for Customer Engagement](../basics/media/neglected-leads-report.png "Neglected Leads Report in Dynamics 365 for Customer Engagement")  
 
### See also  
 [Run a report](../basics/run-report.md)   
 [Troubleshoot problems with data not displaying in a report](../basics/troubleshoot-reports.md)   
 [Customize and organize reports](../customize/customize-organize-reports.md)
