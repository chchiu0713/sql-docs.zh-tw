---
title: 重新命名資料表 (Database Engine) | Microsoft Docs
ms.custom: ''
ms.date: 02/23/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-tables
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Active
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 7c96ad974288ec9c8bbaf09ae9405c40b47cb5e4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="rename-tables-database-engine"></a>重新命名資料表 (Database Engine)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

將 SQL Server 或 Azure SQL Database 中的資料表重新命名。

若要重新命名 Azure SQL 資料倉儲或平行處理資料倉儲中的資料表，請使用 t-sql [RENAME OBJECT](../../t-sql/statements/rename-transact-sql.md) 陳述式。 
  
> [!CAUTION]  
>  在重新命名資料表之前請仔細考慮。 如果現有的查詢、檢視表、使用者定義函數、預存程序或程式參考此資料表，則名稱修改將會使這些物件失效。  
  
 **本主題內容**  
  
-   **開始之前：**  
  
     [限制事項](#Restrictions)  
  
     [Security](#Security)  
  
-   **若要使用下列項目來重新命名資料表：**  
  
     [Transact-SQL](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 開始之前  
  
###  <a name="Restrictions"></a> 限制事項  
 重新命名資料表不會自動重新命名該資料表的參考。 您必須手動修改任何參考重新命名之資料表的物件。 例如，如果您重新命名了資料表，而且觸發程序參考該資料表，您就必須修改觸發程序來反映新的資料表名稱。 在重新命名資料表之前，請使用 [sys.sql_expression_dependencies](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md) 列出其相依性。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 權限  
 需要資料表的 ALTER 權限。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### <a name="to-rename-a-table"></a>重新命名資料表  
  
1.  在物件總管中，以滑鼠右鍵按一下想要重新命名的資料表，然後從快速鍵功能表選擇 [設計]。  
  
2.  從 **[檢視]** 功能表中選擇 **[屬性]**。  
  
3.  在 **[屬性]** 視窗中的 **[名稱]** 值欄位中，輸入資料表的新名稱。  
  
4.  若要取消這個動作，請在離開這個欄位之前按 ESC 鍵。  
  
5.  從 [檔案]  功能表中，選擇 [儲存 <資料表名稱>] 。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### <a name="to-rename-a-table"></a>重新命名資料表  
  
1.  在 **[物件總管]**中，連接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的執行個體。  
  
2.  在標準列上，按一下 **[新增查詢]**。  
  
3.  下列範例會將 `SalesTerritory` 資料表重新命名為 `SalesTerr` 結構描述中的 `Sales` 。 複製下列範例並將其貼到查詢視窗中，然後按一下 **[執行]**。  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 如需其他範例，請參閱 [sp_rename &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-rename-transact-sql.md)。  
  
  
