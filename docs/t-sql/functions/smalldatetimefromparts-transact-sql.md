---
title: SMALLDATETIMEFROMPARTS (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: t-sql|functions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- SMALLDATETIMEFROMPARTS
- SMALLDATETIMEFROMPARTS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- SMALLDATETIMEFROMPARTS function
ms.assetid: 7467fdab-e588-419c-9e29-42caec34a9ea
caps.latest.revision: 14
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: c09655a2335fcad234247c3bc6434a1579ce74d3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="smalldatetimefromparts-transact-sql"></a>SMALLDATETIMEFROMPARTS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all-md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  傳回指定日期和時間的 **smlldatetime** 值。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
SMALLDATETIMEFROMPARTS ( year, month, day, hour, minute )  
```  
  
## <a name="arguments"></a>引數  
 *year*  
 指定年份的整數運算式。  
  
 *month*  
 指定月份的整數運算式。  
  
 *day*  
 指定日期的整數運算式。  
  
 *hour*  
 指定小時的整數運算式。  
  
 *minute*  
 指定分鐘的整數運算式。  
  
## <a name="return-types"></a>傳回類型  
 **smalldatetime**  
  
## <a name="remarks"></a>Remarks  
 此函式的功能與完全初始化之 **smalldatetime** 值的建構函式類似。 如果引數無效，將會引發錯誤。 如果要求的引數為 null，即會傳回 null。  
  
 函數可以在 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 伺服器和更新版伺服器上以遠端方式進行。 它在版本低於 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 的伺服器上無法以遠端方式運作。  
  
## <a name="examples"></a>範例  
  
```  
SELECT SMALLDATETIMEFROMPARTS ( 2010, 12, 31, 23, 59 ) AS Result  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Result  
---------------------------  
2011-01-01 00:00:00  
  
(1 row(s) affected)  
```  
  

