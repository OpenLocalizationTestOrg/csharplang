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
no-loc: [advisor , Test]
---

![Test1noicon](./image/Test1noicon.png)

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

:::image type="complex"  alt-text="this is a complex image testing feature for image SxS behavior" source="./image/feedback-tool.png"::: 
this is a log description for complex image testing feature for SxS
This is SxS multiline testing1
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

::: image source= "./image/Test1noicon.png" alt-text="space teating":::

:::image type="complex" source="./image/feedback-tool.png" alt-text="this is a complex image testing feature for loc-scope2" loc-scope="Azure"::: 
this is a log description for complex image testing feature for loc-scope2
This is multiline testing2
:::image-end:::
<a name="section_C_5_map_values_fields"></a>

### C.5 *sys.dm_xe_map_values* and event fields


The following SELECT includes a JOIN to the tricky view named *sys.dm_xe_map_values*.

The purpose of the SELECT display the numerous fields that you can choose from for your event session. The event fields can be used in two ways:

- To choose which field values will be written to your target for each event occurrence..
- To filter which event occurrences will be sent to versus kept from your target.


```sql
SELECT  --C.5
		dp.name         AS [Package],
		do.name         AS [Object],
		do.object_type  AS [Object-Type],
		'o--c'     AS [O--C],
		dc.name         AS [Column],
		dc.type_name    AS [Column-Type-Name],
		dc.column_type  AS [Column-Type],
		dc.column_value AS [Column-Value],
		'c--m'     AS [C--M],
		dm.map_value    AS [Map-Value],
		dm.map_key      AS [Map-Key]
	FROM
		      sys.dm_xe_objects         AS do
		JOIN  sys.dm_xe_object_columns  AS dc

			ON  dc.object_name = do.name

		JOIN  sys.dm_xe_map_values      AS dm

			ON  dm.name = dc.type_name

		JOIN  sys.dm_xe_packages        AS dp

			ON  dp.guid = do.package_guid
	WHERE
		do.object_type = 'event'
		AND
		do.name        = '\<YOUR-EVENT-NAME-HERE!>'  --'lock_deadlock'
	ORDER BY
		[Package],
		[Object],
		[Column],
		[Map-Value];
```


#### Output

<a name="resource_type_dmv_actual_row"></a>

Next is a sampling of the actual 153 rows of output from the preceding T-SQL SELECT. The row for **resource_type** is [relevant](#resource_type_PAGE_cat_view) to the predicate filtering used in the **event_session_test3** example elsewhere in this article.


```
/***  5 sampled rows from the actual 153 rows returned.
	NOTE:  'resource_type' under 'Column'.

Package     Object          Object-Type   O--C   Column          Column-Type-Name     Column-Type   Column-Value   C--M   Map-Value        Map-Key
-------     ------          -----------   ----   ------          ----------------     -----------   ------------   ----   ---------        -------
sqlserver   lock_deadlock   event         o--c   CHANNEL         etw_channel          readonly      2              c--m   Operational      4
sqlserver   lock_deadlock   event         o--c   KEYWORD         keyword_map          readonly      16             c--m   access_methods   1024
sqlserver   lock_deadlock   event         o--c   mode            lock_mode            data          NULL           c--m   IX               8
sqlserver   lock_deadlock   event         o--c   owner_type      lock_owner_type      data          NULL           c--m   Cursor           2
sqlserver   lock_deadlock   event         o--c   resource_type   lock_resource_type   data          NULL           c--m   PAGE             6

Therefore, on your CREATE EVENT SESSION statement, in its ADD EVENT WHERE clause,
you could put:
	WHERE( ... resource_type = 6 ...)  -- Meaning:  6 = PAGE.
***/
```

## Next steps

To learn more about Advisor recommendations, see:
* [Introduction to Advisor](advisor-overview.md)
* [Get Started](advisor-get-started.md)
* [Advisor Performance recommendations](advisor-cost-recommendations.md)
* [Advisor High Availability recommendations](advisor-cost-recommendations.md)
* [Advisor Security recommendations](advisor-cost-recommendations.md)
