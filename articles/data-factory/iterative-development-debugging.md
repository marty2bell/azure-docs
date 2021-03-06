---
title: Iterative development and debugging in Azure Data Factory | Microsoft Docs
description: Learn how to develop and debug Data Factory pipelines iteratively in the Azure portal.
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.date: 04/16/2018
ms.topic: article
ms.service: data-factory

services: data-factory
documentationcenter: ''
ms.workload: data-services
ms.tgt_pltfrm: na
ms.devlang: na
---
# Iterative development and debugging with Azure Data Factory

Azure Data Factory lets you iteratively develop and debug Data Factory pipelines.

## Iterative debugging features
Create pipelines and do test runs using the **Debug** capability in the pipeline canvas without writing a single line of code.

![Debug capability on the pipeline canvas](media/iterative-development-debugging/iterative-development-image1.png)

View the results of your test runs in the **Output** window of the pipeline canvas.

![Output window of the pipeline canvas](media/iterative-development-debugging/iterative-development-image2.png)

After a test run succeeds, add more activities to your pipeline and continue debugging in an iterative manner. You can also **Cancel** a test run while it is in progress.

![Cancel a test run](media/iterative-development-debugging/iterative-development-image3.png)

When you do test runs, you don't have to publish your changes to the data factory before you select **Debug**. This is helpful in scenarios where you want to make sure that the changes work as expected before you update the data factory workflow.

## More info about debugging

1. The test runs initiated with the **Debug** capability are not available in the list on the **Monitor** tab. You can only see runs triggered with **Trigger Now**, **Schedule**, or **Tumbling Window** triggers in the **Monitor** tab. You can see the last test run initiated with the **Debug** capability in the **Output** window of the pipeline canvas.

2. Selecting **Debug** actually runs the pipeline. So, for example, if the pipeline contains copy activity, the test run copies data from source to destination. As a result, we recommend that you use test folders in your copy activities and other activities when debugging. After you've debugged the pipeline, switch to the actual folders that you want to use in normal operations.

## Setting breakpoints for debugging

Data Factory also lets you debug until you reach a particular activity on the pipeline canvas. Just put a breakpoint on the activity until which you want to test, and select **Debug**. Data Factory ensures that the test runs only until the breakpoint activity on the pipeline canvas. This *Debug Until* feature is useful when you don't want to test the entire pipeline, but only a subset of activities inside the pipeline.

![Breakpoints on the pipeline canvas](media/iterative-development-debugging/iterative-development-image4.png)

To set a breakpoint, select an element on the pipeline canvas. A *Debug Until* option appears as an empty red circle at the upper right corner of the element.

![Before setting a breakpoint on the selected element](media/iterative-development-debugging/iterative-development-image5.png)

After you select the *Debug Until* option, it changes to a filled red circle to indicate the the breakpoint is enabled.

![After setting a breakpoint on the selected element](media/iterative-development-debugging/iterative-development-image6.png)

## Next steps
[Continuous integration and deployment in Azure Data Factory](continuous-integration-deployment.md)
