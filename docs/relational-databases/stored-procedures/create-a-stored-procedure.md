---
title: "建立預存程序 | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-stored-Procs
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
caps.latest.revision: 37
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: bc2034ac69dee1a72429e94841aec1763703de7c
ms.openlocfilehash: 85b2194d4535c4edb2d4a27039fde6ca87911871
ms.contentlocale: zh-tw
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-stored-procedure"></a>建立預存程序

 > 如需舊版 SQL Server 的相關內容，請參閱[建立預存程序](https://msdn.microsoft.com/en-US/library/ms345415(SQL.120).aspx)。

  此主題描述如何使用 [!INCLUDE[tsql](../../includes/tsql-md.md)] 及 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] CREATE PROCEDURE 陳述式來建立 [!INCLUDE[tsql](../../includes/tsql-md.md)] 預存程序。  
  
##  <a name="Top"></a>   
-   **開始之前：**  [Permissions](#Permissions)  
  
-   **若要建立程序，請使用：**[SQL Server Management Studio](#SSMSProcedure)、[Transact-SQL](#TsqlProcedure)  
  
##  <a name="Permissions"></a> Permissions  
 需要在資料庫中的 CREATE PROCEDURE 權限，以及在建立程序時所在的結構描述上的 ALTER 權限。  
  
##  <a name="Procedures"></a> 如何建立預存程序  
 您可以使用下列其中一項：  
  
-   [SQL Server Management Studio](#SSMSProcedure)  
  
-   [Transact-SQL](#TsqlProcedure)  
  
###  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
 **在 [物件總管] 中建立程序**  
  
1.  在 **[物件總管]**中，連接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的執行個體，然後展開該執行個體。  
  
2.  依序展開 **[資料庫]**、 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 資料庫，以及 **[Programmability]**。  
  
3.  以滑鼠右鍵按一下 [預存程序]，然後按一下 [新增預存程序]。  
  
4.  在 **[查詢]** 功能表上，按一下 **[指定範本參數的值]**。  
  
5.  在 **[指定範本參數的值]** 對話方塊中，為顯示的參數輸入下列值。  
  
    |參數|值|  
    |---------------|-----------|  
    |作者|*您的名字*|  
    |建立日期|*今天的日期*|  
    |描述|傳回員工資料。|  
    |Procedure_name|HumanResources.uspGetEmployeesTest|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|**nvarchar**(50)|  
    |Default_Value_For_Param1|NULL|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|**nvarchar**(50)|  
    |Default_Value_For_Param2|NULL|  
  
6.  按一下 **[確定]**。  
  
7.  在 **[查詢編輯器]**中，以下列陳述式取代 SELECT 陳述式：  
  
    ```tsql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  若要測試語法，請在 **[查詢]** 功能表上按一下 **[剖析]**。 如果傳回錯誤訊息，請比較陳述式與上列資訊，並視需要進行更正。  
  
9. 若要建立程序，請在 **[查詢]** 功能表中，按一下 **[執行]**。 程序也可建立為資料庫中的物件。  
  
10. 若要查看物件總管中所列的程序，請以滑鼠右鍵按一下 [預存程序]，然後選取 [重新整理]。  
  
11. 若要執行程序，請在物件總管中，以滑鼠右鍵按一下預存程序名稱 **HumanResources.uspGetEmployeesTest**，然後選取 [執行預存程序]。  
  
12. 在 [執行程序] 視窗中，輸入 Margheim 以作為 @LastName 參數值，然後輸入 Diane 值以作為 @FirstName 參數值。  
  
> [!WARNING]  
>  驗證所有使用者輸入。 在使用者輸入完成驗證前，請勿加以串連。 請勿執行由未經驗證之使用者輸入所建構的命令。  
  
###  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
 **若要在查詢編輯器中建立程序**  
  
1.  在 **[物件總管]**中，連接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的執行個體。  
  
2.  在 **[檔案]** 功能表中，按一下 **[新增查詢]**。  
  
3.  將下列範例複製並貼入查詢視窗中，然後按一下 **[執行]**。 此範例會使用不同的程序名稱建立與上述相同的預存程序。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS   
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO  
  
    ```  
  
4.  若要執行程序，請將下列範例複製並貼到新的查詢視窗中，然後按一下 **[執行]**。 請注意，此處顯示指定參數值的不同方法。  
  
    ```  
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO  
  
    ```  
  
##  <a name="PowerShellProcedure"></a>   
## <a name="see-also"></a>另請參閱  
 [CREATE PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)  
  
  