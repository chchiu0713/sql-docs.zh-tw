---
title: 取得 DDL 觸發程序的資訊 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: triggers
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-ddl
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
caps.latest.revision: 31
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: cdd7d700e4e95a057f86e5c37ee3c730c17feb9e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="get-information-about-ddl-triggers"></a>取得 DDL 觸發程序的詳細資訊
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]
  本章節所列的目錄檢視可用來取得 DDL 觸發程序的相關資訊。  
  
 **取得 DDL 觸發程序引發所在之事件或事件群組的相關資訊**  
  
-   [sys.trigger_event_types &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql.md)  
  
 **檢視觸發程序的相依性**  
  
-   [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md)  
  
-   [sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql.md)  
  
-   [sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql.md)  
  
## <a name="database-scoped-ddl-triggers"></a>資料庫範圍的 DDL 觸發程序  
 **若要取得資料庫範圍觸發程序的相關資訊**  
  
-   [sys.triggers &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-triggers-transact-sql.md)  
  
 **若要取得引發觸發程序之資料庫事件的相關資訊**  
  
-   [sys.trigger_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trigger-events-transact-sql.md)  
  
 **若要檢視資料庫範圍觸發程序的定義**  
  
-   [sys.sql_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md)  
  
 **若要取得 CLR 資料庫範圍觸發程序的相關資訊**  
  
-   [sys.assembly_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-assembly-modules-transact-sql.md)  
  
## <a name="server-scoped-ddl-triggers"></a>伺服器範圍的 DDL 觸發程序  
 **若要取得伺服器範圍觸發程序的相關資訊**  
  
-   [sys.server_triggers &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-triggers-transact-sql.md)  
  
 **若要取得引發觸發程序之伺服器事件的相關資訊**  
  
-   [sys.server_trigger_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql.md)  
  
 **若要檢視伺服器範圍觸發程序的定義**  
  
-   [sys.server_sql_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql.md)  
  
 **若要取得 CLR 伺服器範圍觸發程序的相關資訊**  
  
-   [sys.server_assembly_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql.md)  
  
## <a name="see-also"></a>另請參閱  
 [DDL 觸發程序](../../relational-databases/triggers/ddl-triggers.md)  
  
  
