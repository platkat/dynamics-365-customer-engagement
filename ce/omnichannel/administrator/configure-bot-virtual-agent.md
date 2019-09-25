---
title: "Configure a bot | MicrosoftDocs"
description: "Instructions to configure a bot in Omnichannel for Customer Service."
keywords: ""
author: sbmjais
ms.author: kataylor
manager: shujoshi
applies_to: 
ms.date: 11/01/2019
ms.service: dynamics-365-customerservice
ms.topic: article
ms.assetid: B76E910B-0018-4499-B21F-6FEBDFBB2A22
ms.custom: 
---

# Preview: Integrate a Virtual Agent bot

[!INCLUDE[cc-use-with-omnichannel](../../includes/cc-use-with-omnichannel.md)]

[!include[cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

> [!IMPORTANT]
> - A preview is a feature that is not complete, as it may employ reduced privacy, security, and/or compliance commitments, but is made available before it is officially released for general availability so customers can get early access and provide feedback. Previews are provided “as-is,” “with all faults,” “as available,” and without warranty.​
> - This preview features does not come with technical support and Microsoft Dynamics 365 Technical Support won’t be able to help you with issues or questions.  If Microsoft does elect to provide any type of support, such support is provided "as is," "with all faults," and without warranty, and may be discontinued at any time.​
> - Previews are not meant for production use, especially to process Personal Data or other data that is subject to heightened compliance requirements, and any use of "live" or production data is at your sole risk.  All previews are subject to separate [Terms and Conditions](../../legal/dynamics-insider-agreement.md).

A bot is a program that provides automated responses in a conversational manner to a customer. It can also help in resolving customer queries by using case deflection. A bot can also collect basic information from a customer and then provided it to a customer service agent to work further on the issue raised by the customer.  

A bot eases the load on your customer service agents by handling basic queries. This saves your agents' time and they can work on more complex issues. You can configure your bots to escalate the query to a human agent as and when required by the customer.

In Omnichannel for Customer Service, you can integrate a bot to start the conversation with a customer, provide automated responses, and then shift the conversation to a human agent, if required. Let's now see how to integrate a bot with Omnichannel for Customer Service.

## Integrate a bot with Omnichannel for Customer Service 

**Prerequisites**: You must have a bot that is built using Microsoft Bot Framework. For more information on how to build a bot, see [Azure Bot Service Documentation](https://docs.microsoft.com/en-us/azure/bot-service/?view=azure-bot-service-4.0).



### Set escalation rules

Escalation rules allow you to create rules for the bot to escalate the queries to the appropriate agent. For escalation rules, you must create a context variable and appropriate routing rules to route the customer queries.

If the bot escalates the customer query, it is routed to the appropriate queue as per the defined routing rule. If the customer query in redirected to the same queue, another agent in the queue will pick the conversation as per the capacity. For information on working with queues, see [Work with queues in Omnichannel for Customer Service](queues-omnichannel.md).

> [!NOTE]
> If you've only one queue with bot and agents, and you didn't create a routing rule, the customer query is redirected to the same queue in case of escalation and picked up by an agent.

#### Create a context variable

You must create a context variable for the bot to handle the customer queries appropriately. The context variable is used in routing the incoming customer queries to the appropriate bots and agents. For information on creating context variables, see [Understand and create work streams](work-streams-introduction.md).

#### Create routing rules

Routing rules route the incoming customer queries to their respective queues. Each routing rule has a condition and a destination queue. If the condition is evaluated as true, the customer query is routed to the destination queue. For bots, the condition is built by using the context variable.

Bots are developed to receive customer queries first, gain information of the query,  and then pass the query to a human agent, if required. To achieve this behavior, you must add a bot user to the queue and configure routing rules in a way that the incoming customer queries are routed to the queue with bot user.

Ensure to map the routing rules to the correct queues so that the queries are routed appropriately. For information on creating a routing rule, see [Create and manage routing rules](routing-rules.md).

## Sample configuration to integrate a bot

This sample provides exact steps and configuration values to integrate a bot and then escalate the query to a human agent. In this sample, three queues and three routing rules will be created. A bot user is added to one queue and agents are added to two other queues. Routing rules are defined in a way that whenever a customer initiates a chat, it will be sent to the bot first and then escalated to a human agent as per the conditions defined in the routing rules. The work stream used in this sample is **ChatWorkStream**.

<!-- create a bot user, create queues, (add code snippet - is that relevant at all?) -->

This example uses three queues for you to add users as follows:
    - **BotQueue**: Add the bot user to this queue.
    - **CreditCardQueue**: Add agents who will handle credit card related queries.
    - **HomeLoanQueue**: Add agents who will handle home loan related queries.

Follow the instructions in [Step 4](#step-4-set-escalation-rules) to create escalation rules. Let's say you create a context variable named **BotHandoffTopic** in the **ChatWorkStream** work stream. 

5.	Create three routing rules in the **ChatWorkStream** work stream in the following order:
    - **BotRule**: Specify the work stream and queue as **ChatWorkStream** and **BotQueue** respectively. Add the condition as follows:
        > [!div class=mx-imgBorder]
        > ![Create a rule to send customer query to bot](../media/bot-rule.png "Create a rule to send customer query to bot")
    - **CreditCardRule**: Specify the work stream and queue as **ChatWorkStream** and **CreditCardQueue** respectively. Add the condition as follows:
        > [!div class=mx-imgBorder]
        > ![Create a rule to send customer query from bot to an agent](../media/credit-card-rule.png "Create a rule to send customer query from bot to an agent")
    - **HomeLoanRule**: Specify the work stream and queue as **ChatWorkStream** and **HomeLoanQueue** respectively. Add the condition as follows:
        > [!div class=mx-imgBorder]
        > ![Create a rule to send customer query from bot to an agent](../media/home-loan-rule.png "Create a rule to send customer query from bot to an agent")

When a chat is initiated by a customer, the query is routed to the bot through the **BotRule** routing rule. If the bot escalates the query, it is sent to the appropriate agent as per the configured routing rules. The bot needs to send the correct context variable and its value in the escalation request to route the query appropriately. For more information on setting up of context variable and escalation request, see [Enable a bot to escalate and end conversation](../developer/bot-escalate-end-conversation.md).

## Privacy notice

You understand that your data may be transmitted and shared with external systems and that your data may flow outside of your organization's compliance boundary (even if your organization is in a Government Cloud environment). For example, your messages will be shared with the bot which could be interacting with a third-party system based on the integration done by you. For more information on how we process your data, please refer to the [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement).

### See also

[Understand and create work streams](work-streams-introduction.md)<br>
[Work with queues in Omnichannel for Customer Service](queues-omnichannel.md)<br>
[Create and manage routing rules](routing-rules.md)<br>
[Add a chat widget](add-chat-widget.md)<br>
[Enable a bot to escalate and end conversation](../developer/bot-escalate-end-conversation.md)
