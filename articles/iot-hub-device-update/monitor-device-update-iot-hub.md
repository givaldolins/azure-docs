---
title: Monitoring Device Update for IoT Hub
description: Start here to learn how to monitor Device Update for IoT Hub 
author: eshashah-msft
ms.author: eshashah
ms.topic: conceptual 
ms.service: iot-hub
ms.custom: subject-monitoring
ms.date: 9/08/2022

---

# Monitoring Device Update for IoT Hub

When you have critical applications and business processes relying on Azure resources, you want to monitor those resources for their availability, performance, and operation.

This article describes the monitoring data generated by Device Update for IoT Hub (DU). Device Update uses [Azure Monitor](../azure-monitor/overview.md). If you are unfamiliar with the features of Azure Monitor common to all Azure services that use it, read [Monitoring Azure resources with Azure Monitor](../azure-monitor/essentials/monitor-azure-resource.md).

## Activity log Collection and Routing

The Activity log displays recent administrative activity for the device update account, instances, including any creation, updates, deletion and change in access permissions. Activity logs are collected and stored automatically, but can be routed to other locations by using a diagnostic setting.  

In Azure portal, you can select **Activity Logs** in the Device Update account menu, and the **Time range** for which you want to see activity logs

To create a diagnostic setting to send it to a destination of your choice (Log Analytics workspace, storage account, Event Hub, etc.), select **Export Activity Logs** followed by **Add diagnostic setting** and scope it to the logs and platform metrics emitted by your account.

See [Create diagnostic setting to collect platform logs and metrics in Azure](../azure-monitor/essentials/diagnostic-settings.md) for the detailed process for creating a diagnostic setting using the Azure portal, CLI, or PowerShell. When you create a diagnostic setting, you specify which categories of logs to collect.

## Analyzing logs

Data in Azure Monitor Logs is stored in tables where each table has its own set of unique properties.  

To route data to Azure Monitor Logs, you must create a diagnostic setting to send resource logs or platform metrics to a Log Analytics workspace. 

In Azure portal, you can select **Logs** under **Monitoring** on the left-pane of your Device Update account to perform Log Analytics queries scoped, by default, to the logs and metrics collected in Azure Monitor Logs for your account.

All resource logs in Azure Monitor have the same fields followed by service-specific fields. The common schema is outlined in [Azure Monitor resource log schema](../azure-monitor/essentials/resource-logs-schema.md).

The [Activity log](../azure-monitor/essentials/activity-log.md) is a type of platform log in Azure that provides insight into subscription-level events. You can view it independently or route it to Azure Monitor Logs, where you can do much more complex queries using Log Analytics.  

## Alerts

Azure Monitor alerts proactively notify you when important conditions are found in your monitoring data. They allow you to identify and address issues in your system before your customers notice them. You can set alerts on [logs](../azure-monitor/alerts/alerts-unified-log.md) and the [activity log](../azure-monitor/alerts/activity-log-alerts.md). Different types of alerts have benefits and drawbacks.

## Next steps

- See [Monitoring Azure resources with Azure Monitor](../azure-monitor/essentials/monitor-azure-resource.md) for details on monitoring Azure resources.
