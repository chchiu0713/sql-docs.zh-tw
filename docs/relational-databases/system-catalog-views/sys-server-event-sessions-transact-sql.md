---
title: "sys.server_event_sessions (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- server_event_sessions
- server_event_sessions_TSQL
- sys.server_event_sessions_TSQL
- sys.server_event_sessions
dev_langs: TSQL
helpviewer_keywords:
- sys.server_event_sessions catalog view
- xe
ms.assetid: 796f3093-6a3e-4d67-8da6-b9810ae9ef5b
caps.latest.revision: "15"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 041fe01f163a29df7f070d3c16650dcd32646676
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="sysservereventsessions-transact-sql"></a>sys.server_event_sessions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  列出 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中所存在的所有事件工作階段定義。  
  
||  
|-|  
|**適用於**： [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 至 [目前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658))。|  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|事件工作階段的唯一識別碼。 不可為 Null。|  
|name|**sysname**|用來識別事件工作階段的使用者定義名稱。 名稱是唯一的。 不可為 Null。|  
|event_retention_mode|**nchar(1)**|判斷如何處理事件遺失。 預設值為 S。不可設為 Null。 為下列其中一項：<br /><br /> S. 對應至 event_retention_mode_desc = ALLOW_SINGLE_EVENT_LOSS<br /><br /> M. 對應至 event_retention_mode_desc = ALLOW_MULTIPLE_EVENT_LOSS<br /><br /> N. 對應至 event_retention_mode_desc = NO_EVENT_LOSS|  
|event_retention_mode_desc|**sysname**|描述如何處理事件遺失。 預設值為 ALLOW_SINGLE_EVENT_LOSS。 不可為 Null。 為下列其中一項：<br /><br /> ALLOW_SINGLE_EVENT_LOSS。 事件可能會從工作階段遺失。 只有當所有事件緩衝區已滿時，才會卸除單一事件。 當緩衝區已滿時遺失單一事件會允許可接受的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 效能特性，同時也可讓處理之事件資料流中的遺失情形降至最低。<br /><br /> ALLOW_MULTIPLE_EVENT_LOSS。 完整事件緩衝區可能會從工作階段遺失。 遺失的事件數目取決於配置給工作階段的記憶體大小、記憶體的分割及緩衝區中的事件大小。 當事件緩衝區被快速填滿時，這個選項可對伺服器的效能影響降至最低。 但是，可能會從工作階段中遺失大量的事件數目。<br /><br /> NO_EVENT_LOSS。 不允許事件遺失。 這個選項可確保將會保留所有引發的事件。 使用這個選項可強制引發事件的所有工作等候到事件緩衝區中有可用的空間為止。 這樣可以在事件工作階段為使用中時偵測效能降低的問題。|  
|max_dispatch_latency|**int**|指定事件在對工作階段目標提供服務之前，將於記憶體內緩衝處理的時間量 (以毫秒為單位)。 有效的值是從 1 到 2147483648 及 -1。 -1 的值表示分派延遲為無限大。 可為 Null。|  
|max_memory|**int**|為了事件緩衝處理而配置給工作階段的記憶體數量。 預設值為 4 MB。 可為 Null。|  
|max_event_size|**int**|保留給不適合事件工作階段緩衝區之事件的記憶體數量。 如果 max_event_size 超出計算而來的緩衝區大小，會將 max_event_size 的兩個額外緩衝區配置給事件工作階段。 可為 Null。|  
|memory_partition_mode|**nchar(1)**|在記憶體中建立事件緩衝區的位置。 預設的分割模式為 G。不可設為 Null。 memory_partition_mode 是下列之一：<br /><br /> G - NONE<br /><br /> C - PER_CPU<br /><br /> N - PER_NODE|  
|memory_partition_mode_desc|**sysname**|預設值是 NONE。 不可為 Null。 為下列其中一項：<br /><br /> NONE。 SQL Server 執行個體內會建立單一組緩衝區。<br /><br /> PER_CPU。 為每個 CPU 建立一組緩衝區。<br /><br /> PER_NODE。 會針對每一個非統一記憶體存取 (NUMA) 節點建立一組緩衝區。|  
|track_causality|**bit**|啟用或停用因果追蹤。 如果設定為 1 (ON)，會啟用追蹤，而且不同伺服器連接上的相關事件會彼此相互關聯。 預設值是 0 (OFF)。 不可為 Null。|  
|startup_state|**bit**|可決定當伺服器啟動時，是否要自動啟動工作階段的值。 預設值是 0。 不可為 Null。 是下列其中一項：<br /><br /> 0 (OFF)。 當伺服器啟動時，此工作階段不會啟動。<br /><br /> 1 (ON)。 當伺服器啟動時，會啟動此事件工作階段。|  
  
## <a name="permissions"></a>Permissions  
 需要伺服器的 VIEW SERVER STATE 權限。  
  
## <a name="see-also"></a>請參閱＜  
 [目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [擴充的事件目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [擴充事件](../../relational-databases/extended-events/extended-events.md)  
  
  