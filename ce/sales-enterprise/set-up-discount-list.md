---
title: "Set up a discount list (Dynamics 365 for Sales) | MicrosoftDocs"
description: "Set up discounts on products in Dynamics 365 for Sales to offer products to your customers on marked down rates."
keywords: Discount, Discounted, Discount list
ms.date: 10/09/2018
ms.service:
  - dynamics-365-sales
ms.custom:
  - dyn365-sales
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement
  - Dynamics 365 for Customer Engagement apps version 9.x
ms.assetid: afdf269e-613e-4949-ab6a-d1e9c02d8370
author: shubhadaj
ms.author: shujoshi
manager: annbe
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
caps.latest.revision: 33
topic-status: Drafting
---

# Set up a discount list (Sales and Sales Hub)

Motivate customers to buy more by offering them discounts on bulk purchases. To offer discounts, you need to set up a discount list.  

## Set up a discount list (Sales Hub)

1. [!INCLUDE[proc_permissions_mgr_vp_ceo_busmgr_sysadmin_syscust](../includes/proc-permissions-mgr-vp-ceo-busmgr-sysadmin-syscust.md)]  
  
2. Select the Site map icon ![Site map icon](media/site-map-icon.png "Site map icon"), then select ellipses ![Ellipses to open more options](media/ellipsis-more-options.png "Ellipses to open more options"), and then select **App Settings**. 
  
3. In the **Product Catalog** area, select **Discount Lists**. 

    ![Discount lists in site map](media/site-map-product-catalog.png "Discount lists in site map")

4.	To create a new discount list, on the command bar, select **New**.

    -OR-
  
    To edit a discount list, open a discount list from the list.

5.	Fill in the information, and select **Save**:

    a.	**Name**. Type a name that provides a good description of the kind of discount this list will include.

    b.	**Type**. To calculate the discount as a percentage of the price of the item, select Percentage or to give discount as a fixed amount, select Amount.

    c.	**Currency**. If you chose to give discount as a fixed amount, select the currency.

    ![Discount list form](media/discount-list-form.png "Discount list form")
 
6.	To add discount details to the list, on select the **Related** tab, and then select **Discounts**.

    ![Discount tab on the Discount List form](media/discount-list-form-related-tab-discounts-option.png "Discount tab on the Discount List form")
 
7.	On the **Discounts** tab, select **Add New Discount**.

8.	In the **New Discount** form, fill in the following information, and select **Save & Close**:

    a.	**Begin quantity**. Enter the minimum quantity that if a customer purchase, they will be eligible for a discount.

    b.	**End quantity**. Enter the maximum quantity that if a customer purchase, they will be eligible for a discount.

    c.	**Percentage**. Enter the percentage of discount the customer will receive.

    For example, this discount list will offer a discount of 5% whenever the customer purchases between 3 – 5 pieces of televisions.

      ![Discount form](media/discount-form.png "Discount form")
 


## Set up a discount list (Sales)
  
1. [!INCLUDE[proc_permissions_mgr_vp_ceo_busmgr_sysadmin_syscust](../includes/proc-permissions-mgr-vp-ceo-busmgr-sysadmin-syscust.md)]  
  
    #### Check your security role  
  
   - [!INCLUDE[proc_follow_steps_in_link](../includes/proc-follow-steps-in-link.md)]  
  
   - [!INCLUDE[proc_dont_have_correct_permissions](../includes/proc-dont-have-correct-permissions.md)]  
  
2. [!INCLUDE[proc_settings_prod_catalog](../includes/proc-settings-prod-catalog.md)]  
  
3. Select **Discount Lists**.  
  
4. To create a new discount list, select **New**.  
  
    -OR-  
  
    To edit a discount list, open it.  
  
5. Fill in the information:  
  
   - **Name**. Type a name that provides a good description of the kind of discount this list will include.  
  
   - **Type**. To calculate the discount as a percentage of the price of the item, select **Percentage** or to give discount as a fixed amount, select **Amount**.  
  
   - **Currency**. If you chose to give discount as a fixed amount, select the currency.  
  
   ![Create a discount list in Dynamics 365 for Sales](../sales-enterprise/media/v7-discount-lit.png "Create a discount list in Dynamics 365 for Sales")  
  
6. Select **OK**.  
  
7. To set volume discounts, in the left pane, under **Common**, select **Discounts**, and then on the **Discounts** tab, in the **Records** group, select **Add New Discount**.  
  
8. Fill in the information:  
  
    Here's how:  
  
   ![Create volume discounts in Dynamics 365 for Sales](../sales-enterprise/media/v7-discounts.png "Create volume discounts in Dynamics 365 for Sales")  
  
    This discount list will offer a discount of 5% whenever the customer purchases between 3 – 5 boxes.  
  
9. Select **Save** or **Save and Close**.  
  
## Typical next steps  
 ![Right arrow button](../sales-enterprise/media/walkthrough-orange-right-arrow.png "Right arrow button") [Create a unit group and add units to that group](create-unit-group-add-units-that-group.md)  
  
 ![Home button](../sales-enterprise/media/walkthrough-home.png "Home button") [Set up a product catalog: Walkthrough](set-up-product-catalog-walkthrough.md)  
  
### See also  
 [System Settings dialog box - Sales tab](../admin/system-settings-dialog-box-sales-tab.md)
