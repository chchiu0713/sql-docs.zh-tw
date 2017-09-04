---
title: "設定 SQL Server 錯誤記錄檔 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: d6815aac3852922ae49a4953abc501a2cf958a4c
ms.contentlocale: zh-tw
ms.lasthandoff: 08/02/2017

---
# <a name="scm-services---configure-sql-server-error-logs"></a>SCM 服務 - 設定 SQL Server 錯誤記錄檔
  此主題描述如何檢視或修改 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 錯誤記錄檔的回收方式。  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a>若要開啟 [設定 SQL Server 錯誤記錄檔] 對話方塊  
  
1.  在 [物件總管] 中展開 SQL Server 執行個體，展開 [管理]，以滑鼠右鍵按一下 [SQL Server 記錄檔]，然後按一下 [設定]。  
  
2.  在 **[設定 SQL Server 錯誤記錄檔]** 對話方塊中，從下列選項中進行選擇。  
  
     **限制回收錯誤記錄檔之前，所允許的檔案數目**  
     核取進行錯誤記錄檔的回收之前，可建立之錯誤記錄檔的數目。 每次啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的執行個體，就會建立一個新的錯誤記錄檔。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 會保留前六個記錄檔備份，除非您核取此選項，並在下面另行指定錯誤記錄檔的最大數目。  
  
     **錯誤記錄檔的最大數目**  
     指定回收之前建立之錯誤記錄檔的最大數目。 預設值是 6，這是回收錯誤記錄檔之前， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 保留的先前備份記錄檔數目。  
  
  