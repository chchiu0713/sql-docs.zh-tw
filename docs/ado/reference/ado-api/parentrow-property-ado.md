---
title: ParentRow 屬性 (ADO) |Microsoft 文件
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
- ADORecordConstruction::put_ParentRow
- ADORecordConstruction::ParentRow
- ADORecordConstruction::putParentRow
helpviewer_keywords:
- ParentRow property [ADO]
ms.assetid: 5ea8029b-eda4-490b-ae84-2ad036fb582f
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 76a0a89b6cbdbcfd6a474a830c7ffb9a61603ae7
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="parentrow-property-ado"></a>ParentRow 屬性 (ADO)
設定 OLE DB 的容器**列**物件上**ADORecordConstruction**物件，使資料列的父代會轉換成 ADO**記錄**物件。  
  
 唯寫。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT put_ParentRow([in] IUnknown* pParent);  
```  
  
## <a name="parameters"></a>參數  
 *pParent*  
 資料列的容器。  
  
## <a name="return-values"></a>傳回值  
 這個屬性的方法會傳回標準的 HRESULT 值，包括 S_OK 和 E_FAIL。  
  
## <a name="applies-to"></a>適用於  
 [ADORecordConstruction 介面](../../../ado/reference/ado-api/adorecordconstruction-interface.md)
