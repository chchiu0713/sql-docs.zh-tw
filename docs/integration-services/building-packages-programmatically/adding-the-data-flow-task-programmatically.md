---
title: "以程式設計方式加入資料流程工作 |Microsoft 文件"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
caps.latest.revision: 48
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 0a7b0c3e51d7df76689f16ed91f60972d171bd9a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/26/2017

---
# <a name="adding-the-data-flow-task-programmatically"></a>以程式設計方式加入資料流程工作
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 包括稱為「資料流程」工作的一項工作，該工作是由物件模型中的 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> 命名空間所表示。 「資料流程」工作是一項特殊且高效能的工作，專門用來在封裝執行期間轉換及移動資料。 就像其他工作一樣，「資料流程」工作是由 <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> 物件所包裝，而且從執行階段引擎的觀點來看，這項工作只是封裝內的另一項工作。 但是，此資料流程包含了其他稱為資料流程元件的物件。 這些元件是讓資料從來源移到目的地的元件，有時是透過轉換。 這些元件會定義移動的方向及轉換資料的方式。 設定「資料流程」工作牽涉到在此工作中加入元件，然後連接這些元件來建立資料流程，並達成所要的轉換。  
  
 有三種資料流程工作中元件類型：**資料流程來源**，**資料流程轉換**，和**資料流程目的地**，依此順序中所示[!INCLUDE[ssIS](../../includes/ssis-md.md)]設計工具 工具箱。 這些類型也可以更簡單地稱為來源、轉換或目的地。 如同名稱所指示，資料會從來源流向轉換，然後再流向目的地。 這是過於簡單的資料流程描述，目的是要說明此概念，但是「資料流程」工作更具彈性而且功能非常強大，足以處理多個來源，並將傳送輸出給多個目的地的許多轉換連接在一起。  
  
 「資料流程」工作會加入到封裝中，其方式就像是加入其他工作一樣。 當加入此工作之後，會進行設定，其方式是將元件加入到資料流程工作中，然後在此工作中設定及連接元件。  
  
## <a name="sample"></a>範例  
 下列程式碼範例示範如何將「資料流程」工作加入到封裝。 此範例需要參考 Microsoft.SqlServer.PipelineHost、Microsoft.SqlServer.DTSPipelineWrap 和 Microsoft.SqlServer.ManagedDTS 組件。  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a>外部資源  
 部落格文章： [EzAPI-已更新 SQL Server 2012](http://go.microsoft.com/fwlink/?LinkId=243223)，blogs.msdn.com 上。  
  
## <a name="see-also"></a>另請參閱  
 [以程式設計方式探索資料流程元件](../../integration-services/building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  