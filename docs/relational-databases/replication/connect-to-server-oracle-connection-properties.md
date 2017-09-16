---
title: "連接到伺服器 (Oracle)，連接屬性 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f65a185a723debd6ff1e8d2d240409521fe4c50f
ms.contentlocale: zh-tw
ms.lasthandoff: 06/22/2017

---
# <a name="connect-to-server-oracle-connection-properties"></a>連接到伺服器 (Oracle)，連接屬性
  使用 **[連接到伺服器]** 對話方塊的 **[連接屬性]** 索引標籤，即可指定 **[閘道]** 或 **[完整]**發行選項。 識別發行者之後，除非卸除並重新設定發行者，否則無法變更此選項。 如需詳細資訊，請參閱[設定 Oracle 發行者](../../relational-databases/replication/non-sql/configure-an-oracle-publisher.md)。  
  
## <a name="options"></a>選項。  
 **發行者類型**  
 選取 **[閘道]** 或 **[完整]**。 **[完整]** 選項可以為 Oracle 發行提供具有完整支援功能的快照式和交易式發行集。 [閘道]  選項可以在複寫作為系統之間的閘道時，提供特定的設計最佳化以提升效能。 如果您計畫在多個交易式發行集內發行相同的資料表，就無法使用 [閘道]  選項。 如果您選取 **[閘道]**，則資料表最多只能在一個交易式發行集裡出現，但可以在任意數目的快照式發行集裡出現。  
  
 **逾時**  
 指定 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 散發者要嘗試連接 Oracle 發行者多久之後，才發生逾時的錯誤。  
  
## <a name="see-also"></a>另請參閱  
 [Oracle 發行相關術語字彙](../../relational-databases/replication/non-sql/glossary-of-terms-for-oracle-publishing.md)   
 [Performance Tuning for Oracle Publishers](../../relational-databases/replication/non-sql/performance-tuning-for-oracle-publishers.md)  
  
  