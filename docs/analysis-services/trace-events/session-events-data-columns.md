---
title: 工作階段事件資料行 |Microsoft 文件
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Session Events event category
ms.assetid: 35853451-6768-4a02-8b8f-81a8ae37a333
caps.latest.revision: 21
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 2a11895ad8a966a95b9ea4b78fa78236bc3d88d9
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="session-events-data-columns"></a>工作階段事件資料行
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]工作階段事件的事件類別目錄具有下列事件類別：  
  
|**事件識別碼**|**事件名稱**|**事件描述**|  
|------------------|--------------------|---------------------------|  
|41|Existing Connection|現有的使用者連接。|  
|42|現有的工作階段|現有的工作階段。|  
|43|工作階段初始化|工作階段初始化。|  
  
 下表列出此事件類別的資料行。  
  
## <a name="existing-connection"></a>Existing Connection  
  
|**資料行名稱**|**資料行識別碼**|**資料行類型**|**資料行描述**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|StartTime|3|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|ConnectionID|25|@shouldalert|唯一的連接識別碼。|  
|NTUserName|32|8|Windows 使用者名稱。|  
|NTDomainName|33|8|使用者所隸屬的 Windows 網域。|  
|ClientHostName|35|8|執行用戶端的電腦名稱。 這個資料行會在用戶端提供主機名稱時填入。|  
|ClientProcessID|36|@shouldalert|用戶端應用程式的處理序識別碼。|  
|ApplicationName|37|8|建立伺服器連接的用戶端應用程式名稱。 這個資料行會填入應用程式所傳送的值，而非程式的顯示名稱。|  
|SPID|41|@shouldalert|伺服器處理序識別碼。 這可唯一識別出使用者工作階段， 直接對應到 XML/A 所使用的工作階段 GUID。|  
|ServerName|43|8|產生事件的伺服器名稱。|  
  
## <a name="existing-session"></a>現有的工作階段  
  
|**資料行名稱**|**資料行識別碼**|**資料行類型**|**資料行描述**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|StartTime|3|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|Duration|5|2|事件所花費的時間量 (以毫秒為單位)。|  
|CPUTime|6|2|事件所用的 CPU 時間 (以毫秒為單位)。|  
|ConnectionID|25|@shouldalert|唯一的連接識別碼。|  
|DatabaseName|28|8|正在執行使用者之陳述式的資料庫名稱。|  
|NTUserName|32|8|Windows 使用者名稱。|  
|NTDomainName|33|8|使用者所隸屬的 Windows 網域。|  
|ClientHostName|35|8|執行用戶端的電腦名稱。 這個資料行會在用戶端提供主機名稱時填入。|  
|ClientProcessID|36|@shouldalert|用戶端應用程式的處理序識別碼。|  
|ApplicationName|37|8|建立伺服器連接的用戶端應用程式名稱。 這個資料行會填入應用程式所傳送的值，而非程式的顯示名稱。|  
|NTCanonicalUserName|40|8|標準格式的使用者名稱。 例如，engineering.microsoft.com/software/someone。|  
|SPID|41|@shouldalert|伺服器處理序識別碼。 這可唯一識別出使用者工作階段， 直接對應到 XML/A 所使用的工作階段 GUID。|  
|TextData|42|9|與事件相關的文字資料。|  
|ServerName|43|8|產生事件的伺服器名稱。|  
|RequestProperties|45|9|XMLA 要求屬性。|  
  
## <a name="session-initialize"></a>工作階段初始化  
  
|||||  
|-|-|-|-|  
|**資料行名稱**|**資料行識別碼**|**資料行類型**|**資料行描述**|  
|CurrentTime|2|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|StartTime|3|5|事件的開始時間 (如果可以取得的話)。 篩選所需的格式為 'YYYY-MM-DD' 與 'YYYY-MM-DD HH:MM:SS'。|  
|ConnectionID|25|@shouldalert|唯一的連接識別碼。|  
|DatabaseName|28|8|正在執行使用者之陳述式的資料庫名稱。|  
|NTUserName|32|8|Windows 使用者名稱。|  
|NTDomainName|33|8|使用者所隸屬的 Windows 網域。|  
|ClientHostName|35|8|執行用戶端的電腦名稱。 這個資料行會在用戶端提供主機名稱時填入。|  
|ClientProcessID|36|@shouldalert|用戶端應用程式的處理序識別碼。|  
|ApplicationName|37|8|建立伺服器連接的用戶端應用程式名稱。 這個資料行會填入應用程式所傳送的值，而非程式的顯示名稱。|  
|NTCanonicalUserName|40|8|標準格式的使用者名稱。 例如，engineering.microsoft.com/software/someone。|  
|SPID|41|@shouldalert|伺服器處理序識別碼。 這可唯一識別出使用者工作階段， 直接對應到 XML/A 所使用的工作階段 GUID。|  
|TextData|42|9|與事件相關的文字資料。|  
|ServerName|43|8|產生事件的伺服器名稱。|  
|RequestProperties|45|9|XMLA 要求屬性。|  
  
## <a name="see-also"></a>請參閱  
 [安全性稽核事件類別目錄](../../analysis-services/trace-events/security-audit-event-category.md)  
  
  
