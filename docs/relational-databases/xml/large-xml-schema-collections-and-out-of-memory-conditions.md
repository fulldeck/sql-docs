---
title: "Out-of-memory with large XML schema collections | Microsoft Docs"
description: Learn about solutions for handling out-of-memory conditions when loading or dropping a large XML schema collection.
ms.date: "03/01/2017"
ms.prod: sql
ms.prod_service: "database-engine"
ms.reviewer: ""
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords: 
  - "out-of-memory conditions"
  - "XML schema collections [SQL Server], large"
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: MikeRayMSFT
ms.author: mikeray
ms.custom: "seo-lt-2019"
---
# Large XML Schema Collections and Out-of-Memory Conditions
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur. The following are solutions you can use to handle this:  
  
-   When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command. If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again. If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.  
  
-   When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.  
  
## See Also  
 [Requirements and Limitations for XML Schema Collections on the Server](../../relational-databases/xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
