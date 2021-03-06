---
title: sys.database_recovery_status (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 08/12/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- database_recovery_status_TSQL
- database_recovery_status
- sys.database_recovery_status
- sys.database_recovery_status_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_recovery_status catalog view
ms.assetid: 46fab234-1542-49be-8edf-aa101e728acf
caps.latest.revision: 31
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ddf36b834adb7fd3addb6df9cc6cc4dd9c96dcc4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sysdatabaserecoverystatus-transact-sql"></a>sys.database_recovery_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  針對每個資料庫，各包含一個資料列。 如果資料庫尚未開啟，[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 會嘗試啟動它。  
  
 若要查看資料庫的資料列以外**主要**或**tempdb**，下列其中之一必須套用：  
  
-   您是資料庫的擁有者。  
  
-   您有 ALTER ANY DATABASE 或 VIEW ANY DATABASE 伺服器層級權限。  
  
-   在 CREATE DATABASE 權限**主要**資料庫。    
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|資料庫的識別碼，在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的執行個體內是唯一的。|  
|**database_guid**|**uniqueidentifier**|用來將資料庫的所有資料庫檔案關聯起來。 所有檔案的標頭頁都必須有這個 GUID，資料庫才能依照預期來啟動。 應該只有一個資料庫有這個 GUID，但您可以複製和附加資料庫來建立複本。 當您還原不存在的資料庫時，RESTORE 一律會產生新的 GUID。<br /><br /> NULL= 資料庫離線，或不啟動資料庫。|  
|**family_guid**|**uniqueidentifier**|偵測相符還原狀態的資料庫「備份系列」的識別碼。<br /><br /> NULL= 資料庫離線，或不啟動資料庫。|  
|**last_log_backup_lsn**|**numeric(25,0)**|起始記錄序號的下一個記錄備份。<br /><br /> 如果是 NULL，交易記錄備份最多無法執行因為資料庫處於簡單復原，或沒有目前的資料庫備份。|  
|**recovery_fork_guid**|**uniqueidentifier**|識別目前在使用資料庫的目前復原分岔。<br /><br /> NULL= 資料庫離線，或不啟動資料庫。|  
|**first_recovery_fork_guid**|**uniqueidentifier**|起始復原分岔的識別碼。<br /><br /> NULL= 資料庫離線，或不啟動資料庫。|  
|**fork_point_lsn**|**numeric(25,0)**|如果**first_recovery_fork_guid**不等於 (！ =) 來**recovery_fork_guid**， **fork_point_lsn**是目前分岔點的記錄序號。 否則，這個值是 NULL。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 如需相關資訊，請參閱 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另請參閱  
 [目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [資料庫和檔案目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql.md)   
 [RESTORE HEADERONLY &#40;Transact-SQL&#41;](../../t-sql/statements/restore-statements-headeronly-transact-sql.md)   
 [查詢 SQL Server 系統目錄常見問題集](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
