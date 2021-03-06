---
title: "XML 資料類型 (XMLA) |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- XML data types [XMLA]
- data types [XML for Analysis]
- XMLA, data types
- XML for Analysis, data types
ms.assetid: 979b5384-90d9-4e09-9286-1d1eafdc4864
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 57e14656a089736a8b7ce9566362c9d7c8888a5d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="xml-data-types-xmla"></a>XML 資料類型 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]除了標準基本和衍生所定義之類型的 XML 1.0 版建議事項，XML for Analysis (XMLA) 1.1 規格會定義其他資料類型，以支援多維度和表格式資料的表示法。  
  
 XMLA 會使用下表所列的資料類型。  
  
|資料類型|描述|  
|----------------|-----------------|  
|布林|標準的 XML**布林**資料型別。|  
|Decimal|標準的 XML**十進位**資料型別。|  
|[EmptyResult](../../../analysis-services/xmla/xml-data-types/emptyresult-data-type-xmla.md)|命名空間上的**根**項目。 XMLA 命令不會傳回結果，因為 XMLA 命令通常也不會傳回結果，或是因為發生錯誤時，會傳回此命名空間[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]執行 XMLA 命令時的執行個體。|  
|[EnumString](../../../analysis-services/xmla/xml-data-types/enumstring-data-type-xmla.md)|給定列舉值的具名字串常數集合。|  
|Integer|標準的 XML **int**資料型別。|  
|[MDDataSet](../../../analysis-services/xmla/xml-data-types/mddataset-data-type-xmla.md)|所傳回的多維度資料*結果*參數[Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md)方法。|  
|[結果集](../../../analysis-services/xmla/xml-data-types/resultset-data-type-xmla.md)|自我描述 XML 結果集所傳回**Execute**方法。|  
|[資料列集](../../../analysis-services/xmla/xml-data-types/rowset-data-type-xmla.md)|傳回資料列從資料來源，內嵌 XML 結構描述，結構化[探索](../../../analysis-services/xmla/xml-elements-methods-discover.md)方法。|  
|String|XML**字串**資料型別。|  
|UnsignedInt|XML **unsignedInt**結構描述型別。|  
  
 如需標準 XML 資料類型的完整描述，請參閱全球資訊網協會 (WC3) 的候選建議。  
  
## <a name="see-also"></a>請參閱  
 [XML 項目 &#40;XMLA &#41;](http://msdn.microsoft.com/library/40ab2360-efb6-4ba6-bf23-e84964e51008)   
 [XML for Analysis &#40;XMLA &#41;參考](../../../analysis-services/xmla/xml-for-analysis-xmla-reference.md)  
  
  
