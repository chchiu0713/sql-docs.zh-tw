---
title: get_OLEDBCommand 方法 |Microsoft 文件
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
helpviewer_keywords:
- get_OLEDBCommand method [ADO]
ms.assetid: 23d551f5-3d5b-434b-ade6-fef15f1710e7
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 01e6082d17932dfc85e7ce7ca1ecd3f09d69bc5a
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="getoledbcommand-method"></a>get_OLEDBCommand 方法
傳回基礎 OLE DB 命令，先傳播至 OLE DB 命令 ADO 命令上設定任何參數資訊。  
  
## <a name="syntax"></a>語法  
  
```  
  
HRESULT get_OLEDBCommand(  
      IUnknown **ppOLEDBCommand  
);  
```  
  
#### <a name="parameters"></a>參數  
 *ppOLEDBCommand*  
 [out]寫入基礎 OLE DB 命令的 IUnknown 指標的指標位置指標。  
  
## <a name="applies-to"></a>適用於  
 [IADOCommandConstruction](http://msdn.microsoft.com/en-us/d8e54333-00eb-4b72-bf4a-ca92c7ca5f86)
