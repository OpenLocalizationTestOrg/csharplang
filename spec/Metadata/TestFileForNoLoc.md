---
title: Reduce service costs using Azure Advisor | Microsoft Docs
description: Use Azure Advisor to optimize the cost of your Azure deployments.
services: advisor
documentationcenter: NA
author: kasparks
ms.service: advisor
ms.topic: article
ms.date: 01/29/2019
ms.author: kasparks
---

# Reduce service costs using Azure Advisor

Advisor helps you optimize and reduce your overall Azure spend by identifying idle and underutilized resources. You can get cost recommendations from the **Cost** tab on the Advisor dashboard. This is TEST 123.

## Optimize virtual machine spend by resizing or shutting down underutilized instances 

Although certain application scenarios can result in low utilization by design, you can often save money by managing the size and number of your virtual machines. Advisor monitors your virtual machine usage for 7 days and then identifies low-utilization virtual machines. Virtual machines are considered low-utilization if their CPU utilization is 5% or less and their network utilization is less than 2% or if the current workload can be accommodated by a smaller virtual machine size.This is no-loc test.

Advisor shows you the estimated cost of continuing to run your virtual machine, so that you can choose to shut it down or resize it.

If you want to be more aggressive at identifying underutilized virtual machines, you can adjust the average CPU utilization rule on a per subscription basis.

## Reduce costs by eliminating unprovisioned ExpressRoute circuits

Advisor identifies ExpressRoute circuits that have been in the provider status of *Not Provisioned* for more than one month, and recommends deleting the circuit if you aren't planning to provision the circuit with your connectivity provider.

## Reduce costs by deleting or reconfiguring idle virtual network gateways

Advisor identifies virtual network gates that have been idle for over 90 days. Since these gateways are billed hourly, you should consider reconfiguring or deleting them if you don't intend to use them anymore. 

## Buy reserved virtual machine instances to save money over pay-as-you-go costs

Advisor will review your virtual machine usage over the last 30 days and determine if you could save money by purchasing an Azure reservation. Advisor will show you the regions and sizes where you potentially have the most savings and will show you the estimated savings from purchasing reservations. With Azure reservations, you can pre-purchase the base costs for your virtual machines. Discounts will automatically apply to new or existing VMs that have the same size and region as your reservations. [Learn more about Azure Reserved VM Instances.](https://azure.microsoft.com/pricing/reserved-vm-instances/)

Advisor will also notify you of reserved instances that you have that will expire in the next 30 days. It will recommend that you purchase new reserved instances to avoid paying pay-as-you-go pricing.

## Delete unassociated public IP addresses to save money

Advisor identifies public IP addresses that are not currently associated to Azure resources such as Load Balancers or VMs. These public IP addresses come with a nominal charge. If you do not plan to use them, deleting them can result in cost savings.

## How to access Cost recommendations in Azure Advisor

:::image type="complex"  alt-text="this is a complex image testing feature for loc-scope1" loc-scope="Azure" source="./Test.png"::: 
this is a log description for complex image testing feature for loc-scope1
This is multiline testing1
:::image-end:::

1. Sign in to the [Azure portal](https://portal.azure.com), and then open [Advisor](https://aka.ms/azureadvisordashboard).
:::icon source="image\Test123.png":::This is icon source test
This is test of next line

2.	On the Advisor dashboard, click the **Cost** tab.
This is a :::no-loc text="TEST for inline lock"::: to see if the "TEST for inline loc" will be removed or put as a tag.

:::image source="https://portal.azure.com" alt-text="This is image source Test":::
TLong Description start.Advisor identifies public IP addresses that are not currently associated to Azure resources such as Load Balancers or VMs. These public IP addresses come with a nominal charge. If you do not plan to use them, deleting them can result in cost savings.
Long description end
:::image-end:::This is image end

::: image source= "image\Test1noicon.png" alt-text="space teating":::

:::image type="complex" source="image\Test1noicon.png" alt-text="this is a complex image testing feature for loc-scope2" loc-scope="Azure"::: 
this is a log description for complex image testing feature for loc-scope2
This is multiline testing2
:::image-end:::

## Next steps

To learn more about Advisor recommendations, see:
* [Introduction to Advisor](advisor-overview.md)
* [Get Started](advisor-get-started.md)
* [Advisor Performance recommendations](advisor-cost-recommendations.md)
* [Advisor High Availability recommendations](advisor-cost-recommendations.md)
* [Advisor Security recommendations](advisor-cost-recommendations.md)
