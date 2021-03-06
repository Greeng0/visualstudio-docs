---
title: "Packaging and Deploying SharePoint Solutions | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "packaging [SharePoint development in Visual Studio]"
  - "deploying [SharePoint development in Visual Studio]"
  - "SharePoint development in Visual Studio, packaging and deploying"
ms.assetid: 39072fa7-9f94-49c0-9a67-cbcce0147e61
caps.latest.revision: 34
author: "gewarren"
ms.author: "gewarren"
manager: ghogen
ms.workload: 
  - "office"
---
# Packaging and Deploying SharePoint Solutions
  Typically, a SharePoint solution is deployed to a SharePoint server by using a solution package (.wsp) file. You can use Visual Studio to organize your SharePoint Project Items into Features and to create a package to deploy your SharePoint Features.  
  
 This topic provides the following information:  
  
-   [Creating Features and Packages](#Creating)  
  
-   [Feature and Packaging Tool Support](#Tools)  
  
-   [Deploying SharePoint Solutions](#Deploying)  
  
-   [Deploying Files in SharePoint Solutions](#DeployingFiles)  
  
##  <a name="Creating"></a> Creating Features and Packages  
 You can use Visual Studio to group related SharePoint elements into a *Feature*. For example, a Feature for a Contacts list definition may include the list instance and the list definition. You can combine these two elements into a single Feature for deployment purposes. For more information about features, see [Building Block: Features](http://go.microsoft.com/fwlink/?LinkID=169183).  
  
 Next, you can create a SharePoint solution package (.wsp) to bundle multiple features, site definitions, assemblies, and other files into a single package, which stores the files in a format needed by SharePoint to deploy the files to the server. For more information, see [Building Block: Solutions](http://go.microsoft.com/fwlink/?LinkID=169186).  
  
##  <a name="Tools"></a> Feature and Packaging Tool Support  
 You can use the SharePoint development tools in Visual Studio to quickly organize your SharePoint files into Features and solution packages for easier deployment. You can use the following tools to configure the Feature and solution package.  
  
-   Feature Designer and Package Designer.  
  
-   Packaging Explorer, a tool window.  
  
-   Solution Explorer.  
  
### Feature Designer and Package Designer  
 You can create Features, set scopes, and mark other Features as dependencies by using the Feature Designer. The designer also displays the final XML file that describes each feature. For more information, see [Creating SharePoint Features](../sharepoint/creating-sharepoint-features.md).  
  
 Apply the feature to a specific Web site or group of Web sites by setting its *scope* in the Feature Designer. If a feature is activated for an individual Web site, the feature only works in that particular Web site. If a feature is activated for a site collection, the items in the feature apply to the whole site collection. For more information, see [Element Scope](http://go.microsoft.com/fwlink/?LinkID=169189).  
  
 If your feature relies on other features, you can set a *feature activation dependency* to mark the dependent features before making your feature available. A feature activation dependency checks if the dependent features are already activated at that scope. For more information, see [Activation Dependencies and Scope](http://go.microsoft.com/fwlink/?LinkID=169190).  
  
 In the Package Designer, you can group SharePoint elements into a single solution package and configure whether to reset the Web server during deployment. To set the deployment server type, use the **Properties** window. The designer also generates the XML file that describes the package contents. For more information, see [Creating SharePoint Solution Packages](../sharepoint/creating-sharepoint-solution-packages.md).  
  
 During deployment, the Internet Information Services (IIS) service is stopped to copy the solution files to the SharePoint server. By using the Package Designer in Visual Studio, you can select whether the Web server should be restarted. To configure if the solution is deployed to a front-end Web server or an application server, use the **Properties** window. For more information, see [Solution Element (Solution)](http://go.microsoft.com/fwlink/?LinkID=169191).  
  
### Packaging Explorer  
 To complement the Feature Designer and Package Designer, you can use the Packaging Explorer to group your SharePoint files into Features and packages. In addition, you can see the hierarchical view of the package, Features, SharePoint project items, and files. The Packaging Explorer is a tool window that you can use to complete the following tasks:  
  
-   Open SharePoint project items and files.  
  
-   Drag and drop SharePoint project items from one Feature to another.  
  
-   Drag and drop SharePoint project items and Features from one package to another.  
  
-   Add a new Feature to a package.  
  
-   Open a Feature or package designer.  
  
-   Validate Features and packages.  
  
 The SharePoint development tools in Visual Studio have validation rules to help ensure that the solution package is correctly formed. In addition, the rules verify that the .wsp solution file can be successfully deployed and activated on a SharePoint server. For more information about the XML schema for Features, see [Feature Schemas](http://go.microsoft.com/fwlink/?LinkID=169192).  
  
 You can add custom Feature and package validation rules to the SharePoint project system. For more information, see [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).  
  
 For more information about the Packaging Explorer, see [How to: Add and Remove Features and Items to a Package by Using the Packaging Explorer](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
### Solution Explorer  
 You can use Solution Explorer to navigate and open the files of the SharePoint project. Use the context menu in Solution Explorer to add Features, Feature event receivers, and Feature resources. In addition, you can open the Feature Designers and Package Designers to configure the Features and packages for deployment.  
  
##  <a name="Deploying"></a> Deploying SharePoint Solutions  
 After you customize the Features and package in Visual Studio, you can create a .wsp file to deploy to SharePoint servers. You can use Visual Studio to debug and test the .wsp only on the SharePoint server on the development computer. For more information about how to deploy your SharePoint solutions to a remote SharePoint server, see [Deploying a Solution](http://go.microsoft.com/fwlink/?LinkID=169194).  
  
 You can also customize the deployment steps on the development computer. For more information, see [Deploying, Publishing, and Upgrading SharePoint Solution Packages](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).  
  
##  <a name="DeployingFiles"></a> Deploying Files in SharePoint Solutions  
 Typically, when you add a SharePoint project item to your SharePoint solution, all required files are included. Files that can be compiled (code files) are built into the output assembly of the solution. However, you may also have to add non-compilable files, for example, .xml, .txt, or resource files, to a SharePoint project. These files are not automatically packaged in your solution. To ensure that they are packaged, either add the files to a mapped folder or to a SharePoint project item.  
  
 Files added to mapped folders are automatically copied to the SharePoint hive when the solution is deployed. Files added to a SharePoint project item are deployed to the location that is specified in the **Deployment Location** property for each file, which is partially set based on the **Deployment Type** property. By default, the **Deployment Type** property value is **NoDeployment**, which means that the file is not deployed with the solution. You must set another value for the property to include the file in the package.  
  
 For example, to add an .xml file to a SharePoint project, perform one of these actions:  
  
-   Add a SharePoint "Layouts" Mapped Folder to your project. This creates in **Solution Explorer** a folder named **Layouts** that has a subfolder for the project. Add the .xml file to the new subfolder. By default, the file is deployed to the SharePoint file system under ..\TEMPLATE\LAYOUTS\\*Folder Name*\\. For information about how to add mapped folders, see [How to: Add and Remove Mapped Folders](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
-   Add the .xml file to the folder of a SharePoint project item, and then change the **Deployment Type** property of the .xml file from **NoDeployment** to another setting such as **RootFile** or **ElementFile**. The appropriate **Deployment Type** setting depends on the file and the project. For more information about the **Deployment Type** property settings, see [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md).  
  
 If an added file does not apply to any specific project in the solution, you can add an Empty SharePoint Project to your solution and then add the additional files to it. Another alternative for deploying files to SharePoint, especially to the content database, is to add a module to the project and then add the files to the module. For more information, see [Using Modules to Include Files in the Solution](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## See Also  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [Building and Debugging SharePoint Solutions](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  