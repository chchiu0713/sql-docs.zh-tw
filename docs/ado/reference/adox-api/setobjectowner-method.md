---
title: SetObjectOwner 方法 |Microsoft 文件
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Catalog::SetObjectOwner
- _Catalog::raw_SetObjectOwner
helpviewer_keywords:
- SetObjectOwner method [ADOX]
ms.assetid: e5170a37-9d6e-43db-bfb6-9b6631fa3048
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a3d3642d0641a55bdb476998b722a04dc81edf10
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="setobjectowner-method"></a>SetObjectOwner 方法
指定物件的擁有者[目錄](../../../ado/reference/adox-api/catalog-object-adox.md)。  
  
## <a name="syntax"></a>語法  
  
```  
  
Catalog.SetObjectOwner ObjectName, ObjectType, OwnerName [,ObjectTypeId]  
```  
  
#### <a name="parameters"></a>參數  
 *ObjectName*  
 A**字串**值，指定要為其指定的擁有者物件的名稱。  
  
 *ObjectType*  
 A**長**值可以是下列其中之一的[ObjectTypeEnum](../../../ado/reference/adox-api/objecttypeenum.md)指定擁有者類型的常數。  
  
 *OwnerName*  
 A**字串**值，指定[名稱](../../../ado/reference/adox-api/name-property-adox.md)的[使用者](../../../ado/reference/adox-api/user-object-adox.md)或[群組](../../../ado/reference/adox-api/group-object-adox.md)擁有物件。  
  
 *ObjectTypeId*  
 選擇性。 A **Variant**值，指定不由 OLE DB 規格定義的提供者物件類型的 GUID。 這個參數是必要項，如果*ObjectType*設**adPermObjProviderSpecific**，否則不會使用它。  
  
## <a name="remarks"></a>備註  
 如果提供者不支援指定的物件擁有者，就會發生錯誤。  
  
## <a name="applies-to"></a>適用於  
 [Catalog 物件 (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)  
  
## <a name="see-also"></a>另請參閱  
 [GetObjectOwner 和 SetObjectOwner 方法範例 (VB)](../../../ado/reference/adox-api/getobjectowner-and-setobjectowner-methods-example-vb.md)   
 [GetObjectOwner 方法 (ADOX)](../../../ado/reference/adox-api/getobjectowner-method-adox.md)
