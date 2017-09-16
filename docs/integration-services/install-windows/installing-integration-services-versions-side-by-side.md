---
title: "安裝 Integration Services 版本並存 |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability and coexistence [Integration Services]
- Integration Services, interoperability and coexistence
ms.assetid: edfbcd56-012f-462e-a542-95491394fda9
caps.latest.revision: 41
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d642d8d9d732a51c210e5d83cecf2b090ac2f426
ms.contentlocale: zh-tw
ms.lasthandoff: 08/03/2017

---
# <a name="installing-integration-services-versions-side-by-side"></a>並存安裝 Integration Services 版本
  您可以並存安裝   
      [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]Integration Services (SSIS)-並存與舊版 SSIS。 本主題說明並存安裝的一些限制。  
  
## <a name="designing-and-maintaining-packages"></a>設計和維護封裝  
 若要設計和維護目標為 SQL Server 2016、SQL Server 2014 或 SQL Server 2012 的封裝，請使用適用於 Visual Studio 2015 的 SQL Server Data Tools (SSDT)。 若要取得 SSDT，請參閱 [下載最新的 SQL Server Data Tools](https://msdn.microsoft.com/library/mt204009.aspx)。  
  
 在 Integration Services 專案屬性頁面 [組態屬性] 的 [一般] 索引標籤中，選取 [TargetServerVersion] 屬性，然後選擇 SQL Server 2016、SQL Server 2014 或 SQL Server 2012。  
  
|SQL Server 的目標版本|SSIS 封裝的開發環境|  
|----------------------------------|-----------------------------------------------|  
|2016|Visual Studio 2015 的 SQL Server Data Tools|  
|2014|Visual Studio 2015 的 SQL Server Data Tools<br /><br /> 或<br /><br /> SQL Server Data Tools - Business Intelligence for Visual Studio 2013|  
|2012|Visual Studio 2015 的 SQL Server Data Tools<br /><br /> 或<br /><br /> SQL Server Data Tools - Business Intelligence for Visual Studio 2012|  
|2008|SQL Server 2008 的 Business Intelligence Development Studio|  
  
 當您將現有封裝加入現有專案時，封裝會轉換成專案所設目標的格式。  
  
## <a name="running-packages"></a>執行封裝  
 您可以使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dtexec **公用程式或是** 代理程式的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本，執行較早版本開發工具所建立的 Integration Services 封裝。 當這些 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 工具載入舊版開發工具中所開發的封裝時，工具會暫時將記憶體中的封裝轉換成 [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] 所使用的封裝格式。 如果封裝發生無法成功轉換的問題，在解決這些問題之前， [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 工具將無法執行此封裝。 如需詳細資訊，請參閱 [升級 Integration Services 封裝](../../integration-services/install-windows/upgrade-integration-services-packages.md)。  
  
  