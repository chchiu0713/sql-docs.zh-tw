---
title: 查詢用於建立採礦模型的參數 |Microsoft 文件
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a35dc0d2279b73086af5c16d9d827a12221f63dd
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a>查詢用於建立採礦模型的參數
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]受影響採礦模型的構成不僅受到定型案例的而且建立模型時所設定的參數。 因此，擷取現有模型的參數設定以更加了解模型行為，可能會很有用。 擷取參數在記錄該模型的特定版本時也很有用。  
  
 若要尋找建立模型時所用的參數，您可針對其中一個採礦模型結構描述資料列集建立查詢。 這些結構描述資料列會公開為一組系統檢視表，您可以輕鬆地使用查詢的 TRANSACT-SQL 語法。 這項程序描述如何建立查詢，以傳回用來建立指定採礦模型的參數。  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a>開啟結構描述資料列集查詢的查詢視窗  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，開啟包含所要查詢之 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 的執行個體。  
  
2.  以滑鼠右鍵按一下執行個體名稱，選取 [新增查詢]，然後選取 [DMX]。  
  
    > [!NOTE]  
    >  您也可以使用 [MDX] 範本針對資料採礦模型建立查詢。  
  
3.  如果執行個體包含多個資料庫，請從工具列中的 **[可用的資料庫]** 清單選取包含您要查詢之模型的資料庫。  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a>傳回現有採礦模型的模型參數  
  
1.  在 DMX 查詢窗格中，輸入或貼上下列文字：  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  在 [物件總管] 中，選取所要的採礦模型，然後將它拖曳到 [DMX 查詢] 窗格內的單引號中。  
  
3.  按 F5, 或按一下 **[執行]**。  
  
## <a name="example"></a>範例  
 下列程式碼會傳回用來建立您在 [Basic Data Mining Tutorial](http://msdn.microsoft.com/library/6602edb6-d160-43fb-83c8-9df5dddfeb9c)中所建立之採礦模型的參數清單。 這些參數所包含的明確值，會用於伺服器的提供者所提供之採礦服務使用的任何預設值。  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 程式碼範例會針對群集模型傳回下列參數：  
  
 範例結果：  
  
 MINING_PARAMETERS  
  
 CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10  
  
## <a name="see-also"></a>請參閱  
 [資料採礦查詢工作和使用說明](../../analysis-services/data-mining/data-mining-query-tasks-and-how-tos.md)   
 [資料採礦查詢](../../analysis-services/data-mining/data-mining-queries.md)  
  
  
