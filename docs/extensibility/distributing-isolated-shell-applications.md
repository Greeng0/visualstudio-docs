---
redirect_url: shell/distributing-isolated-shell-applications
title: "Distributing Isolated Shell Applications | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: 9
author: "gregvanl"
ms.author: "gregvanl"
manager: ghogen
ms.workload: 
  - "vssdk"
---
# Distributing Isolated Shell Applications
You must install Visual Studio and the Visual Studio SDK in order to create an isolated shell application. To distribute the application to the machines of other users or customers, you must include a special redistributable package for the isolated shell.  
  
## Prerequisites for Distributing Isolated Shell Applications  
  
|Name|Description|  
|----------|-----------------|  
|Visual Studio SDK|The SDK you must have to develop and test extensions of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. You can also use the SDK to create your own instance of the Visual Studio isolated shell.<br /><br /> Visual Studio is a prerequisite for the SDK.|  
|Microsoft Visual Studio Isolated Shell Redistributable|The redistributable that you include in your Setup program when you build a tools environment on the Visual Studio isolated shell. The isolated Shell redistributable package includes the .NET Framework 4.5.|  
  
## Creating an Installation Program for the Application  
 You must create a special installation program for your integrated or isolated shell application. For more information, see [Installing an Isolated Shell Application](../extensibility/installing-an-isolated-shell-application.md).  
  
## Allowing for Updates to your Application  
 Your installation program must allow for the possibility that your application will be updated, either by Microsoft updates or by your company's updates. For more information about updates, see [Servicing Guidelines for Isolated Shell Applications](../extensibility/servicing-guidelines-for-isolated-shell-applications.md).