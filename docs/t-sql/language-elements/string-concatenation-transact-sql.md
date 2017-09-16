---
title: "+ （字串串連）(TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 12/06/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- concatenation
- +
- string
dev_langs:
- TSQL
helpviewer_keywords:
- concatenation [SQL Server]
- string concatenation operators
- + (string concatenation)
ms.assetid: 35cb3d7a-48f5-4b13-926c-a9d369e20ed7
caps.latest.revision: 51
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 66f482d424c6be56d89e8ec5b99cff30b2ddab0b
ms.contentlocale: zh-tw
ms.lasthandoff: 09/01/2017

---
# <a name="-string-concatenation-transact-sql"></a>+ (字串串連) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  這是字串運算式中的運算子，用來將兩個或更多字元或二進位字串、資料行，或字串和資料行名稱的組合，串連成單一運算式 (字串運算子)。  例如`SELECT 'book'+'case';`傳回`bookcase`。
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
expression + expression  
```  
  
## <a name="arguments"></a>引數  
 *expression*  
 任何有效[運算式](../../t-sql/language-elements/expressions-transact-sql.md)之任何資料類型的字元和二進位資料類型類別目錄，除了**映像**， **ntext**，或**文字**資料型別。 兩個運算式的資料類型必須相同，或者其中一個運算式必須可以用隱含方式轉換為另一個運算式的資料類型。  
  
 當串連二進位字串和二進位字串之間的任何字元時，必須使用指向字元資料的明確轉換。 下列範例示範當`CONVERT`，或`CAST`，必須搭配二進位串連及何時`CONVERT`，或`CAST`，不需要使用。  
  
```  
DECLARE @mybin1 varbinary(5), @mybin2 varbinary(5)  
SET @mybin1 = 0xFF  
SET @mybin2 = 0xA5  
-- No CONVERT or CAST function is required because this example   
-- concatenates two binary strings.  
SELECT @mybin1 + @mybin2  
-- A CONVERT or CAST function is required because this example  
-- concatenates two binary strings plus a space.  
SELECT CONVERT(varchar(5), @mybin1) + ' '   
   + CONVERT(varchar(5), @mybin2)  
-- Here is the same conversion using CAST.  
SELECT CAST(@mybin1 AS varchar(5)) + ' '   
   + CAST(@mybin2 AS varchar(5))  
  
```  
  
## <a name="result-types"></a>結果類型  
 傳回優先順序最高之引數的資料類型。 如需詳細資訊，請參閱[資料類型優先順序 &#40;Transact-SQL&#41;](../../t-sql/data-types/data-type-precedence-transact-sql.md)。  
  
## <a name="remarks"></a>備註  
 + (字串串連) 運算子的行為，在使用空白、長度為零的字串時，與使用 NULL 或未知的值時，各不相同。 長度為零的字元字串可以指定為兩個單引號，引號內不含任何字元。 長度為零的二進位字串可以指定為不含以十六進位常數指定之任何二進位值的 0x。 串連長度為零的字串，一律會串連兩個指定的字串。 當您使用含 Null 值的字串時，串連結果會隨著工作階段設定而不同。 正如同在 Null 值上執行的算術運算，當未知的值加上 Null 值時，結果通常是未知的值，以 Null 值來執行的字串串連作業也應該產生 Null 結果。 不過，您可以變更此行為變更的設定`CONCAT_NULL_YIELDS_NULL`目前工作階段。 如需詳細資訊，請參閱 [SET CONCAT_NULL_YIELDS_NULL &#40;Transact-SQL&#41;](../../t-sql/statements/set-concat-null-yields-null-transact-sql.md)。  
  
 如果字串的串連結果超出 8,000 位元組的限制，就會截斷結果。 不過，如果至少有一個串連的字串是大數值類型時，就不會截斷。  
  
## <a name="examples"></a>範例  
  
### <a name="a-using-string-concatenation"></a>A. 使用字串串連  
 下列範例會根據多個字元資料行，在 `Name` 資料行標題底下建立單一資料行，其中人員姓氏後面接著一個逗號、一個空格，再接著人員的名字。 結果集的排序，按先姓後名的字母順序來遞增。  
  
```  
-- Uses AdventureWorks  
  
SELECT (LastName + ', ' + FirstName) AS Name  
FROM Person.Person  
ORDER BY LastName ASC, FirstName ASC;  
```  
  
### <a name="b-combining-numeric-and-date-data-types"></a>B. 組合數值和日期資料類型  
 下列範例會使用`CONVERT`函數來串連**數值**和**日期**資料型別。  
  
```  
-- Uses AdventureWorks  
  
SELECT 'The order is due on ' + CONVERT(varchar(12), DueDate, 101)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID = 50001;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `------------------------------------------------`  
  
 `The order is due on 04/23/2007`  
  
 `(1 row(s) affected)`  
  
### <a name="c-using-multiple-string-concatenation"></a>C. 使用多重字串串連  
 下列範例串連多個字串來形成一個長字串，以顯示 [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] 副總裁的姓氏和第一個首字母。 在姓氏之後，加上逗號，在第一個首字母之後，加上句點。  
  
```  
-- Uses AdventureWorks  
  
SELECT (LastName + ',' + SPACE(1) + SUBSTRING(FirstName, 1, 1) + '.') AS Name, e.JobTitle  
FROM Person.Person AS p  
    JOIN HumanResources.Employee AS e  
    ON p.BusinessEntityID = e.BusinessEntityID  
WHERE e.JobTitle LIKE 'Vice%'  
ORDER BY LastName ASC;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Name               Title`  
  
 `-------------      ---------------`  
  
 `Duffy, T.          Vice President of Engineering`  
  
 `Hamilton, J.       Vice President of Production`  
  
 `Welcker, B.        Vice President of Sales`  
  
 `(3 row(s) affected)`  
 
### <a name="d-using-large-strings-in-concatenation"></a>D. 在串連中使用大型的字串
下列範例串連多個字串來形成一個長字串，並嘗試計算最終的字串的長度。 結果集的最後一個長度是 16000，因為運算式評估開始，從保留的是， @x + @z + @y = > (@x + @z) + @y。 在此情況下的結果 (@x + @z) 會被截斷為 8000 個位元組，然後@y加入至結果集，使最終的字串長度 16000。 因為@y是字串的大型值型別，就不會截斷。

```
DECLARE @x varchar(8000) = replicate('x', 8000)
DECLARE @y varchar(max) = replicate('y', 8000)
DECLARE @z varchar(8000) = replicate('z',8000)
SET @y = @x + @z + @y
-- The result of following select is 16000
SELECT len(@y) AS y
GO
```
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `y      `  
  
 `-------`  
  
 `16000`  
  
  `(1 row(s) affected)`  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>範例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-using-string-concatenation"></a>E. 使用字串串連  
 下列範例會建立單一資料行的資料行標題底下`Name`從多個字元的資料行、 具有後面逗號、 一個空格，再接著連絡人的名字的連絡人姓氏。 結果集的排序，按先姓後名的字母順序來遞增。  
  
```  
-- Uses AdventureWorks  
  
SELECT (LastName + ', ' + FirstName) AS Name  
FROM DimEmployee  
ORDER BY LastName ASC, FirstName ASC;  
```  
  
### <a name="f-using-multiple-string-concatenation"></a>F. 使用多重字串串連  
 下列範例會串連來形成一個長字串，以顯示姓氏和名字首字母總裁範例資料庫內的多個字串。 在姓氏之後，加上逗號，在第一個首字母之後，加上句點。  
  
```  
-- Uses AdventureWorks  
  
SELECT (LastName + ', ' + SUBSTRING(FirstName, 1, 1) + '.') AS Name, Title  
FROM DimEmployee  
WHERE Title LIKE '%Vice Pres%'  
ORDER BY LastName ASC;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Name               Title                                           
-------------      ---------------  
Duffy, T.          Vice President of Engineering  
Hamilton, J.       Vice President of Production  
Welcker, B.        Vice President of Sales  
```  
  
## <a name="see-also"></a>另請參閱  
 [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [CAST 和 CONVERT &#40;TRANSACT-SQL &#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)   
 [資料類型轉換 &#40; Database Engine &#41;](../../t-sql/data-types/data-type-conversion-database-engine.md)   
 [資料類型 &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [運算式 &#40;TRANSACT-SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [內建函數 &#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)   
 [運算子 &#40;TRANSACT-SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [SET 陳述式 &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)   
 [+ = &#40;字串串連 &#41;&#40;TRANSACT-SQL &#41;](../../t-sql/language-elements/string-concatenation-equal-transact-sql.md)  
  
  



