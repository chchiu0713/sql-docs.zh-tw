---
title: "JDBC 驅動程式的系統需求 |Microsoft 文件"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 447792bb-f39b-49b4-9fd0-1ef4154c74ab
caps.latest.revision: 73
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: eed93fab6f0ceec655b7b9f6b392abc390b5f0ff
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="system-requirements-for-the-jdbc-driver"></a>JDBC 驅動程式的系統需求
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  從存取資料[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或[!INCLUDE[ssAzure](../../includes/ssazure_md.md)]使用[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]，您必須擁有您電腦上安裝下列元件：  
  
-   [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]  
  
     您可以從 Microsoft 下載中心取得下列連結，下載 Microsoft JDBC 驅動程式： 
     * [Microsoft JDBC Driver for SQL Server 6.2](http://go.microsoft.com/fwlink/?linkid=852460)
     * [Microsoft JDBC Driver 6.0 for SQL Server](http://go.microsoft.com/fwlink/?linkid=841535)
     * [Microsoft JDBC Driver 4.2 for SQL Server](http://go.microsoft.com/fwlink/?linkid=841534) 
     * [Microsoft JDBC Driver 4.1 for SQL Server](http://go.microsoft.com/fwlink/?linkid=841533) 
     * [Microsoft JDBC Driver 4.0 for SQL Server](http://go.microsoft.com/fwlink/?linkid=841532)
  
-   Java Runtime Environment  
  
## <a name="java-runtime-environment-requirements"></a>Java Runtime Environment 需求  
 從 Microsoft JDBC Driver 4.2 for SQL Server 開始支援 Sun Java SE 開發套件 (JDK) 8.0 與 Java Runtime Environment (JRE) 8.0。 Java 資料庫連線 (JDBC) Spec API 支援已經過擴充，可包含 JDBC 4.1 和 4.2 API。  
  
 從 Microsoft JDBC Driver 4.1 for SQL Server 開始支援 Sun Java SE 開發套件 (JDK) 7.0 與 Java Runtime Environment (JRE) 7.0。  
  
 從開始[!INCLUDE[jdbc_40](../../includes/jdbc_40_md.md)]，JDBC 驅動程式的 Java Database Connectivity (JDBC) Spec API 支援已經已擴充，可包含 JDBC 4.0 API。 JDBC 4.0 API 導入成 Sun Java SE Development Kit (JDK) 6.0 和 Java Runtime Environment (JRE) 6.0 的一部分。 JDBC 4.0 是 JDBC 3.0 API 的超集。  
  
 當您部署[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]Windows 與 UNIX 作業系統上，您必須使用安裝封裝，封裝*sqljdbc_\<版本 > _enu.exe*和*sqljdbc_\<版本 > _enu.tar.gz*分別。 如需如何部署 JDBC 驅動程式的詳細資訊，請參閱[部署 JDBC 驅動程式](../../connect/jdbc/deploying-the-jdbc-driver.md)主題。  
  
**Microsoft JDBC Driver 6.2 for SQL Server:**  
  
  JDBC 驅動程式 6.2 包含兩個 JAR 類別庫中每個安裝套件： **mssql-jdbc-6.2.1.jre7.jar**，和**mssql-jdbc-6.2.1.jre8.jar**。 
  
 JDBC 驅動程式 6.2 設計來使用，且支援所有主要 Sun 對等 Java 虛擬機器，但僅在 Sun JRE 5.0、 6.0、 7.0 和 8.0 上測試。 
  
 以下摘要說明隨附於 Microsoft JDBC Drivers 6.0 與 4.2 for SQL Server 的兩個 JAR 檔案所提供的支援：  
  
|JAR|JDBC 版本相容性|建議的 Java 版本|Description|  
|---------|-----------------------------|----------------------|-----------------|   
|mssql-jdbc-6.2.1.jre7.jar|4.1|7|需要 Java Runtime Environment (JRE) 7.0。 使用 JRE 6.0 或更舊版本將會擲回例外狀況。<br /><br /> 6.2 中的新功能包括： Azure AD 驗證適用於 Linux，主體/密碼方法 kerberos 領域中的 SPN 進行跨網域驗證，Kerberos 限制委派，查詢逾時，通訊端逾時，自動偵測和準備陳述式控制代碼重複使用。 |  
|mssql-jdbc-6.2.1.jre8.jar|4.2|8|需要 Java Runtime Environment (JRE) 8.0。 使用 JRE 7.0 或更舊版本將會擲回例外狀況。<br /><br /> 6.2 中的新功能包括： Azure AD 驗證適用於 Linux，主體/密碼方法 kerberos 領域中的 SPN 進行跨網域驗證，Kerberos 限制委派，查詢逾時，通訊端逾時，自動偵測和準備陳述式控制代碼重複使用|    

  JDBC 驅動程式 6.2 也會提供 Maven 中央儲存機制以及可以在 POM 中加入下列程式碼加入至 Maven 專案中。XML 
  
 ```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>6.2.1.jre8</version>
</dependency>
```    

 **Microsoft JDBC Driver 6.0 與 4.2 for SQL Server:**  
  
  JDBC 驅動程式 6.0 與 4.2 包含兩個 JAR 類別庫中每個安裝套件： **sqljdbc41.jar**，和**sqljdbc42.jar**。 
  
 JDBC 驅動程式 6.0 與 4.2 設計處理，並在所有主要 Sun 對等 Java 虛擬機器，都必須支援，但僅在 Sun JRE 5.0、 6.0、 7.0 和 8.0 上測試。 
  
 以下摘要說明隨附於 Microsoft JDBC Drivers 6.0 與 4.2 for SQL Server 的兩個 JAR 檔案所提供的支援：  
  
|JAR|JDBC 版本相容性|建議的 Java 版本|Description|  
|---------|-----------------------------|----------------------|-----------------|   
|sqljdbc41.jar|4.1|7|需要 Java Runtime Environment (JRE) 7.0。 使用 JRE 6.0 或更舊版本將會擲回例外狀況。<br /><br /> 6.0 與 4.2 套件中的新功能包括：JDBC 4.1 相容性與大量複製<br /><br /> 此外，只有 6.0 套件中的新功能包含： 備妥的永遠加密，資料表值參數，Azure Active Directory 驗證，透明連接 Alwayson 可用性群組，針對擷取參數中繼資料中的改進查詢和國際化網域名稱 (IDN)|  
|sqljdbc42.jar|4.2|8|需要 Java Runtime Environment (JRE) 8.0。 使用 JRE 7.0 或更舊版本將會擲回例外狀況。<br /><br /> 6.0 與 4.2 套件中的新功能包括：JDBC 4.1 相容性、JDBC 4.2 相容性以及大量複製<br /><br /> 此外，只有 6.0 套件中的新功能包含： 備妥的永遠加密，資料表值參數，Azure Active Directory 驗證，透明連接 Alwayson 可用性群組，針對擷取參數中繼資料中的改進查詢和國際化網域名稱 (IDN)|  
  
 **Microsoft JDBC Driver 4.1 for SQL Server:**  
  
 JDBC Driver 4.1 包含一個 JAR 類別庫中每個安裝套件： **sqljdbc41.jar**。  
    
|JAR|Description|  
|---------|-----------------|  
|sqljdbc41.jar|**sqljdbc41.jar**類別庫會提供 JDBC 4.0 API 的支援。 它包括所有的 JDBC 4.0 驅動程式，以及 JDBC 4.0 API 方法的功能。 不支援 JDBC 4.1 (將會擲回例外狀況"SQLFeatureNotSupportedException")。<br /><br /> **sqljdbc41.jar**類別庫需要 Java Runtime Environment (JRE) 7.0。 使用**sqljdbc41.jar** JRE 6.0 與 5.0 上將會擲回例外狀況。<br /><br /> 
  
 請注意，雖然 JDBC 驅動程式是設計用於與所有主要 Sun 對等 Java 虛擬機器使用並且受該虛擬機器支援，不過它已經在 Sun JRE 5.0、6.0 和 7.0 上測試過。  
  
 以下摘要說明隨附於 Microsoft JDBC Driver 4.1 for SQL Server 的 JAR 檔案所提供的支援。  
  
|JAR|JDBC 版本|JRE (可以執行)|JDK (可以編譯)|  
|---------|------------------|---------------------|-------------------------|   
|sqljdbc41.jar|4|7|7 6 5|  
  
 **Microsoft JDBC Driver 4.0 for SQL Server:**  
  
 為了支援回溯相容性和可能的升級狀況，JDBC 驅動程式會包含兩個 JAR 類別庫中每個安裝套件： **sqljdbc.jar**和**sqljdbc4.jar**。  
  
|JAR|Description|  
|---------|-----------------|  
|sqljdbc.jar|**sqljdbc.jar**類別庫會提供 JDBC 3.0 的支援。<br /><br /> **sqljdbc.jar**類別庫需要 5.0 版的 Java Runtime Environment (JRE)。 使用**sqljdbc.jar**在 JRE 6.0 或 JRE 7.0 將會擲回例外狀況時連接至資料庫。<br /><br /> **注意：** JDBC 驅動程式不支援 JRE 1.4。 使用 JDBC 驅動程式時，您必須將 JRE 1.4 升級為 JRE 5.0、JRE 6.0 或 JRE 7.0。 在某些情況下，您可能必須重新編譯應用程式，因為它可能與 JDK 5.0 API 或 JDK 6.0 API 不相容。 如需詳細資訊，請參閱 Sun Microsystems 網站上的文件。<br /><br /> [!INCLUDE[jdbc_40](../../includes/jdbc_40_md.md)]不支援 JDK 7。|  
|sqljdbc4.jar|**sqljdbc4.jar**類別庫會提供 JDBC 4.0 API 的支援。 它包含的所有功能**sqljdbc.jar**以及新的 JDBC 4.0 API 方法。<br /><br /> **sqljdbc4.jar**類別庫需要 6.0 或 7.0 版的 Java Runtime Environment (JRE)。 使用**sqljdbc4.jar**在 JRE 5.0 上將會擲回例外狀況。<br /><br /> **注意：**使用**sqljdbc4.jar**當您的應用程式必須執行在 JRE 6.0 或 7.0，即使您的應用程式並未使用 JDBC 4.0 API 功能。|  
  
 請注意，雖然 JDBC 驅動程式是設計用於與所有主要 Sun 對等 Java 虛擬機器使用並且受該虛擬機器支援，不過它已經在 Sun JRE 5.0、6.0 和 7.0 上測試過。  
  
## <a name="sql-server-requirements"></a>SQL Server 需求  
 JDBC 驅動程式支援連接至 Azure SQL database 和 SQL Server。 從 SQL Server 2008 開始支援 Microsoft JDBC Driver 4.2 與 4.1 for SQL Server。 從 SQL Server 2005 開始支援 Microsoft JDBC Driver 4.0 for SQL Server。  
  
## <a name="operating-system-requirements"></a>作業系統需求  
 JDBC Driver 設計為可以在支援使用 JAVA 虛擬機器 (JVM) 的任何作業系統上運作。 不過，僅在 Sun Solaris、SUSE Linux 及 Windows 作業系統上正式測試過。  
  
## <a name="supported-languages"></a>支援的語言  
 JDBC 驅動程式支援所有[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]資料行定序。 如需有關 JDBC 驅動程式支援的定序的詳細資訊，請參閱[JDBC driver 的國際功能](../../connect/jdbc/international-features-of-the-jdbc-driver.md)。  
  
 如需有關定序的詳細資訊，請參閱 < 使用定序 」 中的[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]線上叢書 》。  
  
## <a name="see-also"></a>另請參閱  
 [JDBC 驅動程式概觀](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  
