---
title: 擷取結果集資料範例 |Microsoft 文件
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
ms.assetid: 1b190c36-3d38-49a2-8599-612329675851
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 20603e6fc1f0e4728782fce9b79a4a1589651e88
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="retrieving-result-set-data-sample"></a>擷取結果集資料範例
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  這[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]範例應用程式示範如何擷取一組資料從[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]資料庫，然後再顯示該資料。  
  
 此範例的程式碼檔案名稱為 retrieveRS.java，可以在下列位置找到它：  
  
 \<*安裝目錄*> \sqljdbc_\<*版本*>\\<*語言*> \samples\resultsets  
  
## <a name="requirements"></a>需求  
 若要執行此範例應用程式，您必須將 Classpath 設定為包含 sqljdbc.jar 檔案或 sqljdbc4.jar 檔案。 如果 Classpath 遺漏 sqljdbc.jar 或 sqljdbc4.jar 的項目，範例應用程式將會擲回「找不到類別」的一般例外狀況。 您也會需要存取[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]範例資料庫。 如需如何設定 classpath 的詳細資訊，請參閱[使用 JDBC 驅動程式](../../connect/jdbc/using-the-jdbc-driver.md)。  
  
> [!NOTE]  
>  [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]提供 sqljdbc.jar 和 sqljdbc4.jar 類別庫檔案，可根據您慣用的 Java Runtime Environment (JRE) 設定。 如需選擇哪個 JAR 檔案的詳細資訊，請參閱[JDBC 驅動程式的系統需求](../../connect/jdbc/system-requirements-for-the-jdbc-driver.md)。  
  
## <a name="example"></a>範例  
 在下列範例中，範例程式碼會連接到[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]範例資料庫。 然後，使用 SQL 陳述式與[SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md)物件，然後執行 SQL 陳述式，並將它傳回的資料放[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)物件。  
  
 接下來，範例程式碼呼叫自訂 displayRow 方法來逐一查看的結果集中包含的資料列，並使用[getString](../../connect/jdbc/reference/getstring-method-sqlserverresultset.md)方法以顯示一些它所包含的資料。  
  
```java
import java.sql.*;  
  
public class retrieveRS {  
  
   public static void main(String[] args) {  
  
      // Create a variable for the connection string.  
      String connectionUrl = "jdbc:sqlserver://localhost:1433;" +  
            "databaseName=AdventureWorks;integratedSecurity=true;";  
  
      // Declare the JDBC objects.  
      Connection con = null;  
      Statement stmt = null;  
      ResultSet rs = null;  
  
      try {  
  
         // Establish the connection.  
         Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver");  
         con = DriverManager.getConnection(connectionUrl);  
  
         // Create and execute an SQL statement that returns a  
         // set of data and then display it.  
         String SQL = "SELECT * FROM Production.Product;";  
         stmt = con.createStatement();  
         rs = stmt.executeQuery(SQL);  
         displayRow("PRODUCTS", rs);  
      }  
  
      // Handle any errors that may have occurred.  
      catch (Exception e) {  
         e.printStackTrace();  
      }  
  
      finally {  
         if (rs != null) try { rs.close(); } catch(Exception e) {}  
         if (stmt != null) try { stmt.close(); } catch(Exception e) {}  
         if (con != null) try { con.close(); } catch(Exception e) {}  
      }  
   }  
  
   private static void displayRow(String title, ResultSet rs) {  
      try {  
         System.out.println(title);  
         while (rs.next()) {  
            System.out.println(rs.getString("ProductNumber") + " : " + rs.getString("Name"));  
         }  
      } catch (Exception e) {  
         e.printStackTrace();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [使用結果集](../../connect/jdbc/working-with-result-sets.md)  
  
  
