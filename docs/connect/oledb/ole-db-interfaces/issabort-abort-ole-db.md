---
title: 'Issabort:: Abort (OLE DB) |Microsoft 文件'
description: ISSAbort::Abort (OLE DB)
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db-interfaces
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISSAbort::Abort (OLE DB)
apitype: COM
helpviewer_keywords:
- Abort method
author: pmasl
ms.author: Pedro.Lopes
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 93ecb24c160642804a76591e17745f1e558373a7
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="issabortabort-ole-db"></a>ISSAbort::Abort (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  取消目前的資料列集加上與目前命令相關聯之任何批次處理的命令。  
  
**ISSAbort**介面，會在 OLE DB 驅動程式中公開適用於 SQL Server，提供**issabort:: Abort**方法用來取消目前的資料列集加上任何命令批次命令一開始會產生資料列集，並可對尚未完成執行。  
  
 **ISSAbort**是 SQL Server 特定介面 OLE DB 驅動程式可使用**QueryInterface**上**IMultipleResults**所傳回物件**icommand:: Execute**或**iopenrowset:: Openrowset**。  
  
## <a name="syntax"></a>語法  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a>備註  
 如果要中止的命令位於預存程序，將會終止執行預存程序 （以及任何程序，必須呼叫該程序），以及包含預存程序呼叫的命令批次。 如果伺服器正在傳送結果集，用戶端，將會停止傳送。 如果用戶端不想使用結果集，則呼叫**issabort:: Abort**釋放資料列集將會加速資料列集的版本中，但如果沒有開啟的交易，而且 XACT_ABORT 為 ON，將會回復交易之前時**issabort:: Abort**稱為  
  
 之後**issabort:: Abort**傳回 S_OK 時，相關聯**IMultipleResults**介面進入無法使用的狀態並將 db_e_canceled 傳回到所有方法呼叫 (除了所定義的方法**IUnknown**介面) 直到釋放它為止。 如果**IRowset**有取自**IMultipleResults**之前呼叫**中止**，它也會進入無法使用的狀態並將 db_e_canceled 傳回到所有方法呼叫 (除了所定義的方法**IUnknown**介面和**irowset:: Releaserows**) 直到成功呼叫之後釋放它為止**issabort:: Abort**。  
  
> [!NOTE]  
>  開頭為[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]，如果伺服器 XACT_ABORT 狀態上，執行**issabort:: Abort**會終止並回復任何目前隱含或明確的交易時連接到[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。 舊版 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 將不會中止目前的交易。  
  
## <a name="arguments"></a>引數  
 無。  
  
## <a name="return-code-values"></a>傳回碼值  
 S_OK  
 **Issabort:: Abort**方法會傳回 S_OK，如果已取消批次和 DB_E_CANTCANCEL 否則。 如果批次已經遭到取消，就會傳回 DB_E_CANCELED。  
  
 DB_E_CANCELED  
 批次已經遭到取消。  
  
 DB_E_CANTCANCEL  
 批次未取消。  
  
 E_FAIL  
 發生提供者特定的錯誤。詳細資訊，請使用[ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1)介面。  
  
 E_UNEXPECTED  
 此方法的呼叫是非預期的。 比方說，物件處於廢止狀態因為**issabort:: Abort**已經呼叫過。  
  
 E_OUTOFMEMORY  
 記憶體不足的錯誤。  
  
  
