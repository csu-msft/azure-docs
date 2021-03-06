---
title: How to add an IoT Hub event source to your Azure Time Series Insights environment | Microsoft Docs
description: This tutorial covers how to add an event source that is connected to an IoT Hub to your Time Series Insights environment
keywords: 
services: time-series-insights
documentationcenter: 
author: sandshadow
manager: almineev
editor: cgronlun

ms.assetid: 
ms.service: time-series-insights
ms.devlang: na
ms.topic: how-to-article
ms.tgt_pltfrm: na
ms.workload: big-data
ms.date: 04/19/2017
ms.author: edett
---
# How to add an IoT Hub event source

This tutorial covers how to use the Azure portal to add an event source that reads from an IoT Hub to your Time Series Insights environment.

## Prerequisites

You have created an IoT Hub and are writing events to it. For more information on IoT Hubs, see <https://azure.microsoft.com/services/iot-hub/>

> [Consumer Groups] Each Time Series Insights event source needs to have its own dedicated consumer group that is not shared with any other consumers. If multiple readers consume events from the same consumer group, all readers are likely to see failures. For details, see the [IoT Hub developer guide](../iot-hub/iot-hub-devguide.md).

## Choose an Import option

The settings for the event source can be entered manually or an IoT hub can be selected from the IoT hubs that are available to you.
In the **Import Option** selector, choose one of the following options:

* Provide IoT Hub settings manually
* Use IoT Hub from available subscriptions

### Select an available IoT Hub

The following table explains each option in the New Event Source tab with its description when selecting an available IoT Hub as an event source:

| PROPERTY NAME | DESCRIPTION |
| --- | --- |
| Event source name | The name of your event source. This name must be unique within your Time Series Insights environment.
| Source | Choose **IoT Hub** to create an IoT Hub event source.
| Subscription Id | Select the subscription in which this IoT hub was created.
| IoT hub name | Select the name of the IoT Hub.
| IoT hub policy name | Select the shared access policy, which can be found on the IoT Hub settings tab. Each shared access policy has a name, permissions that you set, and access keys. The shared access policy for your event source *must* have **service connect** permissions.
| IoT hub consumer group | The Consumer Group to read events from the IoT Hub. It is highly recommended to use a dedicated consumer group for your event source.

### Provide IoT Hub settings manually

The following table explains each property in the New Event Source tab with its description when entering settings manually:

| PROPERTY NAME | DESCRIPTION |
| --- | --- |
| Event source name | The name of your event source. This name must be unique within your Time Series Insights environment.
| Source | Choose **IoT Hub** to create an IoT Hub event source.
| Subscription Id | The subscription in which this IoT hub was created.
| Resource group | The subscription in which this IoT hub was created.
| IoT hub name | The name of your IoT Hub. When you created your IoT hub, you also gave it a specific name
| IoT hub policy name | The shared access policy, which can be created on the IoT Hub settings tab. Each shared access policy has a name, permissions that you set, and access keys. The shared access policy for your event source *must* have **service connect** permissions.
| IoT hub policy key | The Shared Access key used to authenticate access to the Service Bus namespace. Type the primary or secondary key here.
| IoT hub consumer group | The Consumer Group to read events from the IoT Hub. It is highly recommended to use a dedicated consumer group for your event source.

## Next steps

1. Add a data access policy to your environment (time-series-insights-data-access.md)
1. Access your environment in the [Time Series Insights Portal](https://insights.timeseries.azure.com)