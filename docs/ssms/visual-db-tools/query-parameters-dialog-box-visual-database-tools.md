---
title: 查詢參數對話方塊 (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4fa58a5ed7831a596787875f28d9d156aa1167a3
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a>查詢參數對話方塊 (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
這對話方塊可以讓您輸入查詢中定義的參數值。 執行查詢時，如果查詢中包含在執行階段期間需要使用者輸入的參數，此對話方塊就會出現。  
  
## <a name="options"></a>選項。  
**名稱**  
列出針對正在執行之查詢所定義的參數。 如果查詢包含具名參數，名稱會出現在清單中。 如果查詢包含未命名的參數，則查詢中會針對每個參數列出系統定義的參數名稱。  
  
**ReplTest1**  
請輸入 [Name] 下方列出的每個參數值。 最近使用的值將顯示為預設參數值。  
  
## <a name="example"></a>範例  
在 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject_md.md)] 資料庫中執行下列 [SQL 窗格] 中的查詢時，會開啟 [查詢參數] 對話方塊。  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a>另請參閱  
[使用參數查詢 &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-parameters-visual-database-tools.md)  
  
