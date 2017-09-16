---
title: MSSQLSERVER_21892 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
caps.latest.revision: 6
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 3ce5f5c4d88232aee27695aae35bfcf55734497d
ms.contentlocale: zh-tw
ms.lasthandoff: 06/22/2017

---
# <a name="mssqlserver21892"></a>MSSQLSERVER_21892
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|SQL Server|  
|事件識別碼|21892|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱|SQLErrorNum21892|  
|訊息文字|無法在與虛擬網路名稱 '%s' 相關聯的可用性群組主要複本中，針對成員複本的伺服器名稱查詢 sys.availability_replicas：錯誤 = %d，錯誤訊息 = %s。|  
  
## <a name="explanation"></a>說明  
**sp_validate_replica_hosts_as_publishers** 會查詢與重新導向發行者相關聯之可用性群組的目前主要複本，以便判斷裝載成員複本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體。  當此查詢失敗時，就會傳回錯誤 21892。  
  
**sp_validate_replica_hosts_as_publishers** 通常是在第一次使用暫時連結的伺服器時進行，因此如果發生連線問題，這些問題可能會先與 **sp_validate_replica_hosts_as_publishers** 一起顯示。 **sp_validate_replica_hosts_as_publishers** 與 **sp_validate_redirected_publisher** 不同之處在於，前者所使用的連結伺服器一定會在連接到任何可用性群組複本主機時使用呼叫端的認證。  
  
## <a name="user-action"></a>使用者動作  
執行此預存程序時，請確定您從所有複本上有效的登入執行。 此登入需要足夠的授權，才能查詢可用性群組中繼資料資料表，以及查詢發行者資料庫複本中的訂閱中繼資料資料表。  
  
請檢查原始的參考錯誤，以便判斷失敗的原因以及適當的更正動作。  
  
