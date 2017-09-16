---
title: "STArea (geography 資料類型) |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STArea (geography Data Type)
- STArea_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STArea method
ms.assetid: cfc0b0e0-7fde-431a-863f-d13f3b1b1bef
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e96ee94983746e162990b8eadad4f6affb4f92fd
ms.contentlocale: zh-tw
ms.lasthandoff: 09/01/2017

---
# <a name="starea-geography-data-type"></a>STArea (geography 資料類型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  傳回總介面區**geography**執行個體。 中的空間參考識別碼所使用的測量單位平方傳回結果為 STArea() **geography**執行個體; 例如，如果執行個體的 SRID 為 4326，STArea() 傳回結果中平方公尺來測量。  
  
## <a name="syntax"></a>語法  
  
```  
  
.STArea ( )  
```  
  
## <a name="return-types"></a>傳回類型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]傳回型別： **float**  
  
 CLR 傳回類型： **SqlDouble**  
  
## <a name="remarks"></a>備註  
 STArea() 傳回 0，如果**geography**執行個體包含 0 和 1 維度的圖形或者它是空白。  
  
> [!NOTE]  
>  上的方法**geography**資料型別的產生度量傳回值將會有不同的結果，根據此方法中使用的執行個體的 SRID。 如需有關 Srid 的詳細資訊，請參閱[空間參考識別碼 &#40;Srid &#41;](../../relational-databases/spatial/spatial-reference-identifiers-srids.md).  
  
## <a name="examples"></a>範例  
 下列範例會使用`STArea()`建立`Polygon``geography`執行個體，並計算此多邊形的區域。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326);  
SELECT @g.STArea();  
```  
  
## <a name="see-also"></a>另請參閱  
 [Geography 執行個體上的 OGC 方法](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  