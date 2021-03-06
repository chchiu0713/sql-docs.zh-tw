---
title: setLockTimeout 方法 (SQLServerDataSource) |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: jdbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- SQLServerDataSource.setLockTimeout
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 10dca5aa-1851-4326-9ae9-7a8430d12d11
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 93c6502ea87623c39c7a013e694378b4e967f4ce
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="setlocktimeout-method-sqlserverdatasource"></a>setLockTimeout 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  設定**int**值，指出資料庫報告鎖定逾時之前要等候的毫秒數。  
  
## <a name="syntax"></a>語法  
  
```  
  
public void setLockTimeout(int lockTimeout)  
```  
  
#### <a name="parameters"></a>參數  
 *lockTimeout*  
  
 **Int**值，包含要等候的毫秒數。  
  
## <a name="remarks"></a>備註  
 鎖定逾時是等候資料庫報告鎖定逾時的毫秒數。預設值為 -1，表示將會無限期地等候。 如果已指定，則此值為連接上所有陳述式的預設值。  
  
> [!NOTE]  
>  0 值表示不會等候。 如果未設定 lockTimeout 屬性， [getLockTimeout](../../../connect/jdbc/reference/getlocktimeout-method-sqlserverdatasource.md)方法會傳回預設值為-1。  
  
## <a name="see-also"></a>另請參閱  
 [SQLServerDataSource 成員](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 類別](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
