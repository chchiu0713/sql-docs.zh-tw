---
title: "UPDATE() (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- UPDATE()_TSQL
- UPDATE()
dev_langs:
- TSQL
helpviewer_keywords:
- INSERT statement [SQL Server], UPDATE function
- testing column updates
- UPDATE function
- UPDATE() function
- detecting changes
- columns [SQL Server], change detection
- UPDATE statement [SQL Server], UPDATE function
- verifying column updates
- checking column updates
ms.assetid: 8e3be25b-2e3b-4d1f-a610-dcbbd8d72084
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 6d5b93a4f98e382ccb6504e1d20d6e974a031f86
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="update---trigger-functions-transact-sql"></a>UPDATE-觸發程序函數 (TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  傳回一個布林值，用來指出是否在資料表或檢視的指定資料行上嘗試了 INSERT 或 UPDATE。 [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT 或 UPDATE 觸發程序主體內的任何位置，都可以利用 UPDATE() 來測試觸發程序是否應該執行特定動作。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
UPDATE ( column )   
```  
  
## <a name="arguments"></a>引數  
 *資料行*  
 這是進行 INSERT 或 UPDATE 動作測試的資料行名稱。 由於資料表名稱指定在觸發程序的 ON 子句中，因此，請勿在資料行名稱前面併入資料表名稱。 資料行可以是任何[資料型別](../../t-sql/data-types/data-types-transact-sql.md)支援[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 不過，在這個內容中，不能使用計算資料行。  
  
## <a name="return-types"></a>傳回類型  
 布林  
  
## <a name="remarks"></a>備註  
 不論 INSERT 或 UPDATE 嘗試成功與否，UPDATE() 都會傳回 TRUE。  
  
 若要測試多個資料行的 INSERT 或 UPDATE 動作，指定個別的更新 (*資料行*) 之後的第一個子句。 您可以利用 COLUMNS_UPDATED 來測試多個資料行的 INSERT 或 UPDATE 動作。 這會傳回一個位元模式來指出插入或更新了哪些資料行。  
  
 IF UPDATE 會在 INSERT 動作中傳回 TRUE 值，因為資料行插入了明確的值或隱含的 (NULL) 值。  
  
> [!NOTE]  
>  IF UPDATE (*資料行*n) 子句相同的函數與 IF、 如果...否則，或子句時，可以使用開始...結束區塊。 如需詳細資訊，請參閱[流程控制語言 &#40;TRANSACT-SQL &#41;](~/t-sql/language-elements/control-of-flow.md).  
  
 更新 (*資料行*) 可以在的主體內的任何地方使用[!INCLUDE[tsql](../../includes/tsql-md.md)]觸發程序。  
  
## <a name="examples"></a>範例  
 下列範例會建立一個當任何人試圖升級 `StateProvinceID` 資料表的 `PostalCode` 或 `Address` 資料行時，將訊息列印到用戶端的觸發程序。  
  
```  
USE AdventureWorks2012;  
GO  
IF EXISTS (SELECT name FROM sys.objects  
      WHERE name = 'reminder' AND type = 'TR')  
   DROP TRIGGER Person.reminder;  
GO  
CREATE TRIGGER reminder  
ON Person.Address  
AFTER UPDATE   
AS   
IF ( UPDATE (StateProvinceID) OR UPDATE (PostalCode) )  
BEGIN  
RAISERROR (50009, 16, 10)  
END;  
GO  
-- Test the trigger.  
UPDATE Person.Address  
SET PostalCode = 99999  
WHERE PostalCode = '12345';  
GO  
```  
  
## <a name="see-also"></a>請參閱＜  
 [COLUMNS_UPDATED &#40;TRANSACT-SQL &#41;](../../t-sql/functions/columns-updated-transact-sql.md)   
 [CREATE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)  
  
  
