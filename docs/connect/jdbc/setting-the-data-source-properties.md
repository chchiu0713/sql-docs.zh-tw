---
title: 設定資料來源屬性 |Microsoft 文件
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
ms.assetid: f3363d05-07fc-4bf8-ae5e-2a7a968808ad
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0d7c237bd3f8cbdc8ec25330b20f2b4d3bfb1cf8
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="setting-the-data-source-properties"></a>設定資料來源屬性
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  資料來源為在 Java Platform Enterprise Edition (Java EE) 環境中建立 JDBC 連接所慣用的機制。 資料來源提供連接、共用連接及分散式連接，而未在 Java 程式碼內將連接屬性寫入程式碼。 所有[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]可以設定資料來源，或分別使用適當的 setter 與 getter 方法，取得任何屬性的值。  
  
 Java EE 產品 (例如應用程式伺服器及 servlet/JSP 引擎) 通常會讓您設定資料庫存取的資料來源。 中所列的任何屬性[設定連接屬性](../../connect/jdbc/setting-the-connection-properties.md)主題可以指定只要組態能讓您屬性輸入成 property = value 組。  
  
 如需有關[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]資料來源，請參閱[SQLServerDataSource](../../connect/jdbc/reference/sqlserverdatasource-class.md)類別。 如需如何使用 SQLServerDataSource 類別建立連接的範例[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]資料庫，請參閱[資料來源範例](../../connect/jdbc/data-source-sample.md)。  
  
## <a name="see-also"></a>另請參閱  
 [使用 JDBC Driver 連接到 SQL Server](../../connect/jdbc/connecting-to-sql-server-with-the-jdbc-driver.md)  
  
  
