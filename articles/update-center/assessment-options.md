---
title: Assessment options in update management center (preview).
description: The article describes the assessment options available in Update management center (preview).
ms.service: update-management-center
ms.date: 04/21/2022
ms.topic: conceptual
author: snehasudhirG
ms.author: sudhirsneha
---

# Assessment options in update management center (preview)

**Applies to:** :heavy_check_mark: Windows VMs :heavy_check_mark: Linux VMs :heavy_check_mark: On-premises environment :heavy_check_mark: Azure Arc-enabled servers.

This article provides an overview of the assessment options available by update management center (preview). 

Update management center (preview) provides you the flexibility to assess the status of available updates and manage the process of installing required updates for your machines.

## Periodic assessment
 
 Periodic assessment is an update setting on a machine that allows you to enable automatic periodic checking of updates by update management center (preview). We recommend that you enable this property on your machines as it allows update management center (preview) to fetch latest updates for your machines every 24 hours and enables you to view the latest compliance status of your machines. You must register this [feature in your Azure subscription](enable-machines.md#periodic-assessment). You can enable this setting using update settings flow as detailed [here](manage-update-settings.md#configure-settings-on-single-vm) or enable it at scale by using [Policy](periodic-assessment-at-scale.md). 

:::image type="content" source="media/updates-maintenance/periodic-assessment-inline.png" alt-text="Screenshot showing periodic assessment option." lightbox="media/updates-maintenance/periodic-assessment-expanded.png":::

## Check for updates now/On-demand assessment

Update management center (preview) allows you to check for latest updates on your machines at any time, on-demand. You can view the latest update status and act accordingly. Go to **Updates** blade on any VM and select **Check for updates** or select multiple machines from update management center (preview) and check for updates for all machines at once. For more information, see [check and install on-demand updates](view-updates.md).

## Update assessment scan
 You can initiate a software updates compliance scan on a machine to get a current list of operating system updates available. 

 - **On Windows** - the software update scan is actually performed by the Windows Update Agent. 
 - **On Linux** -  the software update scan is performed using OVAL-compatible tools to test for the presence of vulnerabilities based on the OVAL Definitions for that platform, which is retrieved from a local or remote repository.

 In the **Updates (preview)** page, after you initiate an assessment, a notification is generated to inform you the activity has started and another is displayed when it is finished.

 :::image type="content" source="media/assessment-options/updates-preview-page.png" alt-text="Screenshot of the Updates (preview) page.":::


The **Recommended updates** section is updated to reflect the OS updates applicable. You can also select **Refresh** to update the information on the page and review the assessment details of the selected machine.

In the **History** section, you can view:
- **Total deployments**—the total number of deployments.
- **Failed deployments**—the number out of the total deployments that failed.
- **Successful deployments**—the number out of the total deployments that were successful.

A list of the deployments created are shown in the update deployment grid and include relevant information about the deployment. Every update deployment has a unique GUID, represented as **Activity ID**, which is listed along with **Status**, **Updates Installed**, and **Time details**. You can filter the results listed in the grid in the following ways:

- Select one of the tile visualizations
- Select a specific time period. Options are: **Last 30 Days**, **Last 15 Days**, **Last 7 Days**, and **Last 24 hrs**. By default, deployments from the last 30 days are shown.
- Select a specific deployment status. Options are: **Succeeded**, **Failed**, **CompletedWithWarnings**, **InProgress**, and **NotStarted**. By default, all status types are selected.
Selecting any one of the update deployments from the list will open the **Assessment run** page. Here, it shows a detailed breakdown of the updates and the installation results for the Azure VM or Arc-enabled server.

In the **Scheduling** section, you can either **create a maintenance configuration** or **attach existing maintenance configuration**. See the section for more information on [how to create a maintenance configuration](scheduled-patching.md#create-a-new-maintenance-configuration) and [how to attach existing maintenance configuration](scheduled-patching.md#attach-a-maintenance-configuration).


## Next steps

* To view update assessment and deployment logs generated by update management center (preview), see [query logs](query-logs.md).
* To troubleshoot issues, see the [Troubleshoot](troubleshoot.md) update management center (preview).