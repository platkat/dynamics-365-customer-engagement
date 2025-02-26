---
title: "Maximize email deliverability (Dynamics 365 for Marketing) | Microsoft Docs"
description: "How to design and send marketing email messages that avoid spam filters and get opened by customers in Dynamics 365 for Marketing"
keywords: administration; spam; deliverability; SPF; best practice
ms.date: 03/08/2019
ms.service: dynamics-365-marketing
ms.custom: 
  - dyn365-marketing
ms.topic: article
applies_to: 
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
ms.assetid: d6e63962-e06a-4bc2-90d2-e7bca4e12d61
author: kamaybac
ms.author: kamaybac
manager: shellyha
ms.reviewer:
topic-status: Drafting
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365Mktg
---

# Best practices for email marketing

Sending marketing email is not the same as sending personal email as most people know it. They might seem similar, but there is an important difference: personal emails get delivered to just one or a few people, whereas marketing emails get delivered to many thousands or more every month.

In response to various email abuses, such as widely targeted spam and scams, most companies and email providers now implement filtering and blocking mechanisms to defend their bandwidth and keep their users' inboxes clean. So, when somebody begins sending a large volume of email, the internet takes notice and defensive mechanisms might begin to kick in, which might result in keeping your messages out of your contacts' inboxes. Individual email clients also apply their own filtering algorithms that, among other things, can filter based on each user's personal history of interactions, which can mean that an identical message that gets delivered to one recipient could get blocked by another recipient's email client.

These systems are not intended to stop all forms of legitimate marketing email, just to block abuse. [!INCLUDE[pn-ms-dyn-365](../includes/pn-ms-dyn-365.md)] is designed to be one of the good guys—to facilitate collaborative, opt-in marketing—but you do need to be aware of how to work in the context of common filtering strategies, anti-spam laws and other anti-abuse mechanisms to help make sure your marketing messages get delivered to your contacts rather than stuck in their spam filters.

## Build and protect your sender reputation

When a message goes out over the internet, the IP address that sent it is available to each server that processes that message. Third-party watchdog organizations, such as ReturnPath, monitor activity, message content, and complaints associated with sending addresses and generate a reputation score for each sending IP address and/or domain name. The lower your reputation score, the more likely your messages are to get dropped or filtered out; if your score gets low enough, you'll end up on a block list and none of your messages will get delivered.

Large email providers (such as Hotmail or Gmail), and private email systems at large organizations, use similar techniques to generate their own, internal, sender reputations and scores, which apply yet another layer of filtering.

In addition to sender reputation, many countries and regions have laws that regulate commercial email messages, and breaking these laws can expose you to expensive litigation. Examples of these include CAN-SPAM in the United States and CASL in Canada. The new [GDPR regulations](gdpr.md) in the European Union also establish strict rules for how companies are permitted to handle data and communicate digitally with individuals.

So what can you do to maximize your deliverability and remain within the law, and how can Dynamics 365 for Marketing help? Read the following subsections to find out. For more information about deliverability and sender reputation, search with [!INCLUDE[pn-bing](../includes/pn-bing.md)] for many more good articles about this topic.

### Create clean, collaborative, and responsible content

Both spam filters and sender-reputation systems analyze the content of the messages you are trying to send. They look for signs that you are working together with your recipients and are identifying yourself honestly. Common requirements here are the presence of unsubscribe links and your organization's physical street address in the message body. Messages in HTML format should also include a plain-text version that has the same information. Dynamics 365 for Marketing provides features to make it easy to include these essential items in your messages, and helps prevent you from leaving them out by mistake.

### Authenticate your messages, sending IP, and domain

Several standards are in place to help ensure that sending IP addresses really do represent the organizations they claim to, and that messages coming from those IPs are authentic and untampered with. These include _Sender Policy Framework_ ([SPF](http://www.openspf.org/FAQ)) and _DomainKeys Identified Mail_ ([DKIM](http://dkim.org/info/dkim-faq.html)). 

In a standard setup, Microsoft implements SPF for you and does what it can to maintain a good sender reputation for all Microsoft sender IPs. In addition, Dynamics 365 for Marketing provides a feature that enables you to set up DKIM to link your Dynamics 365 for Marketing sending domain with your own email domain. For complete details on why this is important and how to do it, see [Set up DKIM for your sending domain](#dkim).

### Avoid sending to invalid and inactive email addresses

If you send a message to an invalid, inactive, or canceled email address, the message is typically returned as what is called a "hard bounce." Hard bounces happen, but the reputation watchdogs, public providers, and private hosts  will notice, and the more hard bounces you have associated with your sending IP, the lower your reputation score will be. Addresses associated with a hard bounce will probably never come back online, so you don't want them in your database; Dynamics 365 for Marketing will automatically stop sending to hard-bouncing addresses for six months before trying them again.

Microsoft needs to defend the reputation of our sending IPs, so organizations that consistently generate a large number of hard bounces and/or spam complaints may be contacted by Microsoft Support with advice for how to improve their sending lists and/or messaging. Organizations that continue to generate hard bounces and spam complaints may eventually risk having their accounts closed.

Dynamics 365 for Marketing provides detailed analytics and KPIs for how your contacts interact with your marketing email messages (and other initiatives), including counts of opens, clicks, bounces, and forwards. Use this information to evaluate your success in engaging contacts and to keep your database free of hard-bouncing addresses. [!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Analyze results to gain insights](insights.md)

> [!NOTE]
> Dynamics 365 for Marketing won't try to send to a known hard-bouncing address during the six-month quarantine period. However, your email insights will still indicate a hard-bounce result for each such delivery that you have requested. These "virtual" hard bounces don’t impact your sending IP reputation, but they do count against your monthly send quota in Dynamics 365 for Marketing&mdash;and these addresses will be tried again after the six-month quarantine. We therefore recommend that you regularly check your results for hard bounces, and remove the hard-bouncing addresses from your contact records.

### Don't use purchased or rented mailing lists

Dynamics 365 for Marketing is designed to facilitate _opt-in marketing_, in which all contacts have chosen to receive marketing messages from your organization, and can easily choose to stop doing so at any time. The app helps you build your mailing lists organically and in collaboration with your current and prospective customers by providing features such as [double opt-in](double-opt-in.md), [subscription management](set-up-subscription-center.md), and [consent-management for GDPR compliance](gdpr.md). [Marketing pages](create-deploy-marketing-pages.md) and the [event website](set-up-event-portal.md) also provide avenues for new customers to join your database and sign up for mailing lists.

We strongly recommend that you do not purchase or rent mailing lists because such lists may violate GDPR consent laws and other local laws in other countries/regions. Rented and purchased lists are also ineffective because they are likely to contain many expired addresses that will hard bounce, and they are likely to contain many contacts that aren't interested in your products and who may complain about receiving unsolicited email (possibly to legal authorities); both complaints and hard bounces will lower your sending reputation, and with it, your deliverability rate.

### Send consistent volumes

High-scoring sender reputations are associated with IP addresses that send a consistent volume of email. A sudden spike will lower the score, as will intermittent send volumes. Microsoft maintains several IP addresses dedicated to sending messages from Dynamics 365 for Marketing in each region, and balances the sending load among them to keep sending volume consistent over time for each IP. Each time we add a new sending IP to a region, we "warm it up" by gradually increasing the volume it sends until it eventually reaches the same level as the other IPs in that region. For most Dynamics 365 for Marketing subscribers this is handled automatically and invisibly, but new subscribers who plan to send marketing messages to very large numbers of recipients (in the millions) might need to start small and ramp up over time before reaching full volume; in this case, Microsoft Support will notify you and help you during this process.

<a name="dkim"></a>

## Set up DKIM for your sending domain

One of the most common online scams, also known as *phishing*, occurs when a fraudulent message pretends to come from a well-known online service or financial institution. The goal is to trick recipients into responding to the message by providing private details such as passwords or credit card numbers. One way to prevent phishing is for email recipients to authenticate the from-address for each message to confirm it really was sent from a domain that belongs to the company or organization it claims to belong to. A technology called DKIM (DomainKeys Identified Mail) helps accomplish this by incorporating the following elements:

- A public/private key signature that proves the message was sent from a server owned by a known organization.
- A central register of authenticated signatures, which enables the DNS (Domain Name System) to confirm that each signature is legitimate and that the sending domain and claimed from-address both belong to the same organization.

When you send email from Dynamics 365 for Marketing, your messages come from a domain owned by Microsoft (such as `contosomarketing.onmicrsoft.com`), but the from-address will probably belong to one of your own marketing, sales, or account managers using a more well-known domain that belongs to your organization (such as `you@contoso.com`). This discrepancy can be a red flag when an inbound email server does a DKIM check on incoming messages, which is why a full implementation of DKIM is so important for ensuring high deliverability, especially when you are using a third-party sending service like Dynamics 365 for Marketing.

Dynamics 365 for Marketing helps you to generate, register, and confirm DKIM keys for each of your sending domains. See [Authenticate your domains](marketing-settings.md#authenticate) for instructions.

> [!IMPORTANT]
> If your organization uses _Domain-based Message Authentication, Reporting and Conformance_ ([DMARC](https://dmarc.org/wiki/FAQ)) to protect against phishing attacks involving your domain, then it's extra important that you set up DKIM for your sending domains as described in [Authenticate your domains](marketing-settings.md#authenticate). This will help to prevent false positives during DMARC checks made by receiving systems.

## Test your deliverability

Once you have all of the relevant email-authentication systems in place, we highly recommend that you test your deliverability to all of the major email hosts (such as Gmail, Outlook.com, Yahoo mail, and more), and to as many private domains as your can (including your own). To do this:

1. Set up an email account that you can read on as each of as many services and domains as you can.
1. Set up a contact record for each of these addresses in Dynamics 365 for Marketing.
1. Run a [simple email campaign](create-simple-customer-journey.md) that targets all of your test contacts.
1. Inspect the inbox for each account to confirm your messages arrive in the inbox and don't get labelled as junk.

## Microsoft's spam policy for email marketing

Throughout this topic, we've stressed the importance of maintaining clean, opted-in send lists combined with valued content and collaborative sending behavior. These are all important aspects of building a strong sender reputation and thereby achieving high deliverability and in-box placement. Because email sent by Dynamics 365 for Marketing is delivered from shared sending domains, Microsoft constantly monitors all delivery results, spam complaints, and blacklists to make sure our sending domains maintain their high reputation for the benefit of all customers.

To help protect you, the responsible marketer, against the behavior of bad actors beyond your control, we have implemented an anti-spam policy that protects your sending reputation. Here’s how it works:

### Stage 1: Inform and warn

When we notice that a particular customer is generating a relatively high rate of bounces or spam complaints, we'll let them know right away that something is wrong with the way they are using the system and will offer our assistance to help sort it out.
When this occurs, we will send a notification directly to the administrator by email. This communication will urge the customer to contact Microsoft Support for assistance as soon as possible.

### Stage 2: Move to a higher risk sending pool

If the problem persists for more than a few days and the customer still has not contacted Microsoft Support, then we will move that customer to a higher risk sending pool, which has a lower reputation than the high-deliverability sending pool provided to compliant customers.

When this occurs, we will send email notification to alert the customer that we have moved them to a higher risk sending pool and to urge them to contact Microsoft Support for assistance. It may still be possible for the customer to return to the low-risk email sending pool, but not before contacting Microsoft Support and learning how to address the issue going forward.

## Using a custom, dedicated sender IP

In a standard [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] setup, all sender IPs are managed by Microsoft and shared among customers that have similar reputation scores. This lets us manage reputation, balance the send load, and warm up new IPs as needed. However, some organizations prefer to use one or more of their own, dedicated sender IPs, especially if they will be sending very high volumes.

> [!NOTE]
> Dedicated sender IPs are not part of the standard [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] subscription agreement, and Microsoft does not generally recommend them because they introduce extra complexity and expense—and can result reduced deliverability compared to our standard sender IPs. Microsoft considers applications for dedicated sender IPs on a case-by-case basis, and we can support multiple dedicated sender IPs if needed. If you think your organization could benefit from a dedicated sender IP, please [contact Microsoft Support](setup-troubleshooting.md#contact-support) to find out if you qualify. The main goal of this process is to help you achieve as high a delivery rate as possible. Some of the most important factors to consider when making this decision include:
> 
> - How many messages does your organization send each month?
> - Is your content of high quality and in compliance with all relevant regulations?
> - Have there been many spam complaints associated with your messages until now?
> - Does your organization send a consistent volume of messages throughout the month?

Though there can be a few advantages to arranging for a dedicated sender IP, there are also disadvantages, and it is not for everyone. Consider the following:

- **A new sender IP requires time to warm up**  
    When your new sender IP comes online, you must start by sending just a few messages at a time and then slowly ramp up over several weeks until you reach your intended send volume, which you must then continue to maintain. A sudden spike of email coming from a new IP will severely damage your send reputation and might land you on a block list right away. During the warm-up period, it is also important that you only send to valid and engaged recipients. Later, when you have established a reputation, you can begin to add less-engaged recipients.
- **Maintain a regular and consistent send volume**  
    You must spread out your email sends to ensure that you send roughly the same volume every week or so. Don't try to send all your messages at once at the start of each month, for example.
- **You should set up sender authentication for your domain**  
    As mentioned previously, Microsoft sets up the [SPF](http://www.openspf.org/FAQ) and [DKIM](http://dkim.org/info/dkim-faq.html) sender-authentication standards for all of the sender IPs that we use in a standard solution, but when you use your own sender IP, you must do this yourself. You should also [use DKIM to link your sending and email domains](#dkim). These technologies help ensure that spam filters and reputation watchdogs will be able to see that each IP address sending your messages is a legitimate sender and that it matches your envelope sender domain. Doing this is likely to greatly improve your message deliverability.
- **You concentrate risk on yourself and can pay a high price for any mistakes**  
    When you are the only one using your sending IP, any mistakes you make will affect your sender reputation directly, without being diluted by the large volume of compliant messages being sent by a large pool of other users.

### See also

[Create a marketing email and go live](create-marketing-email.md)  
[Prepare marketing email messages](prepare-marketing-emails.md)
