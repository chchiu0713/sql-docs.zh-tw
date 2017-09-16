---
title: "Azure Blob 來源 |Microsoft 文件"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/25/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.afpblobsrc.f1
- sql14.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 752f199d4555163fee9bbc7b1cbcda9e69b638aa
ms.contentlocale: zh-tw
ms.lasthandoff: 08/03/2017

---
# <a name="azure-blob-source"></a>Azure Blob 來源
  **Azure Blob 來源** 元件可讓 SSIS 封裝從 Azure Blob 讀取資料。 支援的檔案格式：CSV 與 AVRO。
  
  若要查看 Azure Blob 來源的編輯器，可在資料流程設計師上拖放 **Azure Blob 來源** ，並連按兩下以開啟編輯器。  
  
 **Azure Blob 來源**是一種元件的[Azure 的 SQL Server Integration Services (SSIS) Feature Pack](../../integration-services/azure-feature-pack-for-integration-services-ssis.md)。  
  
1.  針對 [Azure 儲存體連線管理員] 欄位，請指定現有的 Azure 儲存體連線管理員，或建立參考 Azure 儲存體帳戶的新連線管理員。  
  
2.  針對 [Blob 容器名稱] 欄位，請指定包含原始程式檔的 Blob 容器名稱。  
  
3.  針對 [Blob 名稱] 欄位，請指定 Blob 的路徑。  
  
4.  針對 [Blob 檔案格式] 欄位，請指定要使用的 Blob 格式。  
  
5.  若檔案格式為 CSV，則您必須指定 [資料行分隔符號字元] 值。 若檔案中第一個資料列包含資料行名稱，請選取 [第一個資料列的資料行名稱]。  
  
6.  指定連接資訊後，請切換至 [資料行]  頁面，將來源資料行對應至 SSIS 資料流程的目的地資料行。  
  
  
