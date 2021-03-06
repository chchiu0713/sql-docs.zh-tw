---
title: 索引鍵集資料指標 |Microsoft 文件
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Keyset cursors [ADO]
- cursors [ADO], Keyset
ms.assetid: 14b51b17-6fd9-4146-af45-ca4b0fe6d48a
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 88772fa9ede31acdf5b719cec7cb9311b15cb864
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="keyset-cursors"></a>索引鍵集資料指標
索引鍵集資料指標偵測變更的能力提供靜態和動態資料指標之間的功能。 類似靜態資料指標，它不一定偵測的變更的成員資格和順序的結果集。 動態資料指標，例如它沒有在結果集中偵測變更的資料列的值。  
  
 索引鍵集驅動資料指標是由一組稱為索引鍵集的唯一識別碼 （索引鍵） 的控制。 索引鍵是從結果集中唯一識別資料列的一組資料行建立的。 索引鍵集是從查詢陳述式所傳回的所有資料列的索引鍵值組。  
  
 與索引鍵集驅動資料指標索引鍵是建立、 儲存的資料指標中每個資料列和儲存在用戶端工作站或伺服器上。 當您存取每個資料列時，預存的金鑰用來從資料來源擷取目前的資料值。 在索引鍵集驅動資料指標時，會完全擴展索引鍵集時，已凍結結果集的成員資格。 此後，新增或更新影響成員資格不屬於結果集之前重新開啟。  
  
 變更資料值 （由依索引鍵集擁有者或其他處理序） 都是可見的使用者捲動的結果集。 只有當資料指標已關閉並重新開啟，會顯示插入資料指標外部製作 （藉由其他處理序）。 從資料指標內進行的插入會顯示在結果集的結尾。  
  
 索引鍵集驅動資料指標的嘗試擷取已刪除的資料列，資料列會顯示為 「 孔 」 結果集內。 資料列的索引鍵存在於索引鍵集，但是該資料列不再存在於結果集。 如果已更新的索引鍵值的資料列中，資料列會被視為已刪除，然後插入，因此這類資料列也會顯示為結果集中的漏洞。 雖然索引鍵集驅動資料指標一律可以偵測其他程序所刪除的資料列，它可以選擇性地移除它本身進行刪除的資料列的索引鍵。 執行此動作的索引鍵集驅動資料指標無法偵測自己刪除，因為已移除的辨識項。  
  
 更新索引鍵資料行的運作方式與刪除舊的金鑰後面插入新的金鑰。 如果更新尚未成為透過資料指標時才看不到 新索引鍵值。 已透過資料指標進行更新，新的索引鍵值可見的結果集的結尾。  
  
 沒有索引鍵集驅動資料指標稱為索引鍵集導向的標準資料指標的變化型。 在索引鍵集導向的標準資料指標，結果集中的資料列的成員資格和資料列的順序固定的資料指標開啟時，但值由資料指標擁有者所做的變更，就可以看到其他處理程序所做的認可的變更。 如果變更 disqualifies 成員資格的資料列，或影響資料列的順序，資料列不會消失或移除非資料指標已關閉並重新開啟。 插入的資料不會顯示，但是會在提取資料列，並會顯示現有資料的變更。  
  
 索引鍵集驅動資料指標很難使用正確的資料變更的敏感程度取決於許多不同情況下，因為上面所述。 不過，如果您的應用程式不關心並行更新，以程式設計的方式可以處理不正確的索引鍵，而且必須直接存取特定索引鍵的資料列，索引鍵集驅動資料指標的動作就可能適用於您。 使用**adOpenKeyset CursorTypeEnum**來指出您想要使用在 ADO 中索引鍵集資料指標。  
  
## <a name="see-also"></a>另請參閱  
 [順向資料指標](../../../ado/guide/data/forward-only-cursors.md)   
 [靜態資料指標](../../../ado/guide/data/static-cursors.md)   
 [動態資料指標](../../../ado/guide/data/dynamic-cursors.md)
