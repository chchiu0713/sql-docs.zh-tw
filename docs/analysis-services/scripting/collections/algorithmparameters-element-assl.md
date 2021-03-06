---
title: AlgorithmParameters 元素 (ASSL) |Microsoft 文件
ms.custom: ''
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- AlgorithmParameters Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AlgorithmParameters
helpviewer_keywords:
- AlgorithmParameters element
ms.assetid: 240cbb60-7fa3-46ef-b5be-cd14c9ec10de
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 668166459e2002fa14a415af5c5e6216dfafa087
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="algorithmparameters-element-assl"></a>AlgorithmParameters 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含所使用之演算法的參數集合[MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md)項目。  
  
## <a name="syntax"></a>語法  
  
```xml  
  
<MiningModel>  
   ...  
   <AlgorithmParameters>  
      <AlgorithmParameter>...</AlgorithmParameter>  
   </AlgorithmParameters>  
   ...  
</MiningModel>  
```  
  
## <a name="element-characteristics"></a>元素特性  
  
|特性|描述|  
|--------------------|-----------------|  
|資料類型和長度|無 (集合)|  
|預設值|無 (集合)|  
|基數|0-1：只能出現一次的選擇性元素。|  
  
## <a name="element-relationships"></a>元素關聯性  
  
|關聯性|元素|  
|------------------|-------------|  
|父元素|[MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md)|  
|子元素|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|  
  
## <a name="remarks"></a>備註  
 **AlgorithmParameters**集合包含可擴充的參數，表示為採礦模型演算法的名稱/值組集合。 適用的參數集合視演算法而定。 如需有關給定演算法之演算法參數的詳細資訊，請參閱該演算法的適當文件。  
  
 您可以從 DMSCHEMA_MINING_SERVICE_PARAMETERS 結構描述資料列中擷取可用的演算法參數，包括驗證和顯示資訊。  
  
 分析管理物件 (AMO) 物件模型中的對應元素是<xref:Microsoft.AnalysisServices.AlgorithmParameterCollection>。  
  
## <a name="see-also"></a>請參閱  
 [Algorithm 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/algorithm-element-assl.md)   
 [DMSCHEMA_MINING_SERVICE_PARAMETERS 資料列集](../../../analysis-services/schema-rowsets/data-mining/dmschema-mining-service-parameters-rowset.md)   
 [集合 &#40;ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
