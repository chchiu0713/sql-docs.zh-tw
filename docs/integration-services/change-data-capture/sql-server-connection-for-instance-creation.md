---
title: "SQL Server Connection for Instance Creation |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 65f20b235b6a3c4bd22ce754467f36a9b03fdaab
ms.contentlocale: zh-tw
ms.lasthandoff: 08/03/2017

---
# <a name="sql-server-connection-for-instance-creation"></a>用來建立執行個體的 SQL Server 連接
  建立 Oracle CDC 執行個體時的其中一個首要步驟就是在目標 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體上建立 CDC 資料庫。 這個 CDC 資料庫會啟用 SQL Server CDC，而這樣的啟用需要屬於 `sysadmin` 固定伺服器角色成員的登入。  
  
 如果啟動 [建立 Oracle CDC 執行個體精靈] 的使用者不是 `sysadmin` 固定伺服器角色的成員，便會開啟 [連接到 SQL Server] 對話方塊，並要求 `sysadmin` 角色成員的認證，才能執行「為 SQL Server CDC 啟用資料庫」工作。 當建立 CDC 資料庫時，將會捨棄 `sysadmin` 登入，而且會使用之前進入 Oracle 設計工具主控台時所使用的原始 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登入繼續工作。  
  
## <a name="task-list"></a>工作清單  
 在 [連接到 SQL Server] 對話方塊中輸入以下資訊。  
  
 **伺服器名稱**  
 輸入 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 所在的伺服器名稱。  
  
 **驗證**  
 選取下列其中一項：  
  
-   **Windows 驗證**  
  
-   **SQL Server 驗證**：如果您選取這個選項，您必須針對您所連接之 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中的使用者輸入 [登入] 和 [密碼]。  
  
 此登入擁有的資料庫角色必須允許存取 MSXCDCDB 資料庫。 建議最好讓此登入也能存取正在使用的其他任何資料庫，否則使用者將無法檢視這些資料庫中的資料。  
  
 **選項。**  
 按一下箭頭即可檢視要設定的可用選項。 您可以選擇保留這些選項的預設值。 可用的選項如下：  
  
-   **連接逾時**：輸入 Oracle CDC 服務在逾時之前，等候連接 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的時間 (以秒數為單位)。 預設值為 **15**。  
  
-   **執行逾時**：輸入 Oracle CDC Windows 服務在逾時之前，等候執行命令的時間 (以秒數為單位)。 預設值是 **30**。  
  
-   **加密連接**：針對 Oracle CDC 服務與使用加密連接之目標 **執行個體之間的通訊選取** [加密連接] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 。  
  
-   **進階**：按一下 [進階]，並在必要時，於 [進階連接屬性] 對話方塊中輸入其他任何連接屬性。  
  
     如需有關 [進階連接屬性] 對話方塊的相關資訊，請參閱[進階連接屬性](../../integration-services/change-data-capture/advanced-connection-properties.md)。  
  
## <a name="see-also"></a>請參閱＜  
 [建立 SQL Server 變更資料庫](../../integration-services/change-data-capture/create-the-sql-server-change-database.md)   
 [CDC 設計工具 SQL Server 連接所需權限](../../integration-services/change-data-capture/sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  