---
title: getImportedKeys 方法 (SQLServerDatabaseMetaData) |Microsoft 文件
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
apiname:
- SQLServerDatabaseMetaData.getImportedKeys
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: dc8c1a5e-700e-4059-a5ed-5013bbb87fb6
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5ed1492914aa1f149a641eead6605704daba6c10
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="getimportedkeys-method-sqlserverdatabasemetadata"></a>getImportedKeys 方法 (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  擷取主索引鍵資料行的描述，這些資料行會由資料表中的外部索引鍵資料行所參考。  
  
## <a name="syntax"></a>語法  
  
```  
  
public java.sql.ResultSet getImportedKeys(java.lang.String cat,  
                                          java.lang.String schema,  
                                          java.lang.String table)  
```  
  
#### <a name="parameters"></a>參數  
 *cat*  
  
 A**字串**，其中包含目錄名稱。  
  
 *schema*  
  
 A**字串**，其中包含結構描述名稱。  
  
 *table*  
  
 A**字串**，其中包含資料表名稱。  
  
## <a name="return-value"></a>傳回值  
 A [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)物件。  
  
## <a name="exceptions"></a>例外狀況  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>備註  
 這個 getImportedKeys 方法是由 java.sql.DatabaseMetaData 介面中 getImportedKeys 方法指定。  
  
 GetImportedKeys 方法所傳回的結果集將包含下列資訊：  
  
|名稱|型別|Description|  
|----------|----------|-----------------|  
|PKTABLE_CAT|**字串**|包含主索引鍵資料表的目錄名稱。|  
|PKTABLE_SCHEM|**字串**|主索引鍵資料表的結構描述名稱。|  
|PKTABLE_NAME|**字串**|主索引鍵資料表的名稱。|  
|PKCOLUMN_NAME|**字串**|主索引鍵的資料行名稱。|  
|FKTABLE_CAT|**字串**|包含外部索引鍵資料表的目錄名稱。|  
|FKTABLE_SCHEM|**字串**|外部索引鍵資料表的結構描述名稱。|  
|FKTABLE_NAME|**字串**|外部索引鍵資料表的名稱。|  
|FKCOLUMN_NAME|**字串**|外部索引鍵的資料行名稱。|  
|KEY_SEQ|**short**|資料行在多重資料行主索引鍵中的序號。|  
|UPDATE_RULE|**short**|當 SQL 作業為更新時套用到外部索引鍵的動作。 它可能是下列其中一個值：<br /><br /> importedKeyNoAction (3)<br /><br /> importedKeyCascade (0)<br /><br /> importedKeySetNull (2)<br /><br /> importedKeySetDefault (4)<br /><br /> importedKeyRestrict (1)|  
|DELETE_RULE|**short**|當 SQL 作業為刪除時套用到外部索引鍵的動作。 它可能是下列其中一個值：<br /><br /> importedKeyNoAction (3)<br /><br /> importedKeyCascade (0)<br /><br /> importedKeySetNull (2)<br /><br /> importedKeySetDefault (4)<br /><br /> importedKeyRestrict (1)|  
|FK_NAME|**字串**|外部索引鍵的名稱。|  
|PK_NAME|**字串**|主索引鍵的名稱。|  
|DEFERRABILITY|**short**|指出外部索引鍵條件約束的評估是否可以延遲到認可之前。 它可能是下列其中一個值：<br /><br /> importedKeyInitiallyDeferred (5)<br /><br /> importedKeyInitiallyImmediate (6)<br /><br /> importedKeyNotDeferrable (7)|  
  
> [!NOTE]  
>  多個 getImportedKeys 方法所傳回的資料的詳細資訊，請參閱 「 sp_fkeys (TRANSACT-SQL) 」，在[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]線上叢書 》。  
  
## <a name="example"></a>範例  
 下列範例示範如何傳回有關所有參考的外部索引鍵中的 Person.Address 資料表的主索引鍵使用 getImportedKeys 方法[!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)]範例資料庫。  
  
```  
public static void executeGetImportedKeys(Connection con) {  
   try {  
      DatabaseMetaData dbmd = con.getMetaData();  
      ResultSet rs = dbmd.getImportedKeys("AdventureWorks", "Person", "Address");  
      ResultSetMetaData rsmd = rs.getMetaData();  
  
      // Display the result set data.  
      int cols = rsmd.getColumnCount();  
      while(rs.next()) {  
         for (int i = 1; i <= cols; i++) {  
            System.out.println(rs.getString(i));  
         }  
      }  
      rs.close();  
   }   
  
   catch (Exception e) {  
      e.printStackTrace();  
   }  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [SQLServerDatabaseMetaData 方法](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 成員](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 類別](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
