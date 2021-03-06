---
title: sys.dm_io_cluster_shared_drives (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, pdw
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_io_cluster_shared_drives_TSQL
- sys.dm_io_cluster_shared_drives
- dm_io_cluster_shared_drives_TSQL
- dm_io_cluster_shared_drives
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_io_cluster_shared_drives dynamic management view
ms.assetid: c8fcced8-c780-49dc-99bd-6beb3ca532c4
caps.latest.revision: 30
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 8d42c66b4abe0fb227384cf1db6aa71e37f15000
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmioclustershareddrives-transact-sql"></a>sys.dm_io_cluster_shared_drives (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  如果目前的伺服器執行個體是一個叢集伺服器，這個檢視會傳回每個共用磁碟機的磁碟機名稱。 如果目前的伺服器執行個體不是叢集執行個體，它會傳回空的資料列集。  
  
> [!NOTE]  
>  若要呼叫從[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]，使用名稱**sys.dm_pdw_nodes_io_cluster_shared_drives**。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**DriveName**|**nchar(2)**|代表參與叢集共用磁碟陣列之個別磁碟的磁碟機名稱 (磁碟機代號)。 資料行不可為 Null。|  
|**pdw_node_id**|**int**|**適用於**: ssPDW<br /><br /> 此發行版本上的節點識別碼。|  
  
## <a name="remarks"></a>備註  
 當啟用叢集時，容錯移轉叢集執行個體要求資料和記錄檔必須放在共用磁碟上，以便在執行個體容錯移轉至其他節點時，仍可存取這些檔案。 此檢視表中的每個資料列，都代表這個叢集 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體所用的單一共用磁碟。 只有此檢視表所列出的磁碟可以用來儲存這個 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體的資料或記錄檔。 這份檢視中所列出的磁碟，即為與該執行個體相關聯之叢集資源群組中的磁碟。  
  
> [!NOTE]  
>  這個檢視表在未來的版本將會被取代。 我們建議您改用[sys.dm_io_cluster_valid_path_names &#40;TRANSACT-SQL&#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md)改為。  
  
## <a name="permissions"></a>Permissions  
 使用者必須具有 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體的 VIEW SERVER STATE 權限。  
  
## <a name="examples"></a>範例  
 下列範例會使用 sys.dm_io_cluster_shared_drives 來判斷叢集伺服器執行個體上的共用磁碟機：  
  
```  
SELECT * FROM sys.dm_io_cluster_shared_drives;  
```  
  
 結果集如下：  
  
 DriveName  
  
 --------\-  
  
 m  
  
 n  
  
## <a name="see-also"></a>另請參閱  
 [sys.dm_io_cluster_valid_path_names &#40;Transact SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md)   
 [sys.dm_os_cluster_nodes &#40;Transact SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-cluster-nodes-transact-sql.md)   
 [sys.fn_servershareddrives &#40;Transact SQL&#41;](../../relational-databases/system-functions/sys-fn-servershareddrives-transact-sql.md)   
 [動態管理檢視與函數 &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  
