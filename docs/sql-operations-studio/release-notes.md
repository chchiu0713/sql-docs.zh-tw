---
title: Microsoft SQL Operations Studio (preview) 版本資訊 |Microsoft 文件
description: Microsoft SQL Operations Studio (preview) 版本資訊
ms.custom: tools|sos
ms.date: 04/25/2018
ms.prod: sql
ms.reviewer: alayu; erickang; sstein
ms.suite: sql
ms.prod_service: sql-tools
ms.component: sos
ms.tgt_pltfrm: ''
ms.topic: article
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 233572c87f785e10a0cde4ac78a7c8ee75c5a801
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="sql-operations-studio-preview-release-notes"></a>SQL Operations Studio (preview) 版本資訊

**[下載公用年 4 月預覽](download.md)**


## <a name="april-2018-april-public-preview"></a>年 4 月 2018 （年 4 月公用預覽）

發行日期： 2018 年 4 月 25，  
版本： 0.28.6

*年 4 月公用預覽*包含 bug 修正和增強功能。 

- SQL 代理程式預覽擴充功能的增強功能。
- 改善大型和受保護的檔案來儲存受保護的系統管理員的支援和 > 在 SQL 作業 Studio 256 M 檔案。
- 若要同時使用多個開啟的終端機分割整合式的終端機。
- 降低的安裝磁碟上檔案計數呎列印更快的安裝和啟動時間。
- 繼續以修正 GitHub 問題：
   - 修正[發出 37](https://github.com/Microsoft/sqlopsstudio/issues/37)： 當圖表檢視器擲回錯誤時，就會發生未預期的行為。
   - 修正[發出 462](https://github.com/Microsoft/sqlopsstudio/issues/462)： 功能要求： 根據預設展開伺服器群組的選項。
   - 修正[發出 606](https://github.com/Microsoft/sqlopsstudio/issues/606): intellisense-'update' 命令的錯誤提供建議。
   - 修正[發出 967](https://github.com/Microsoft/sqlopsstudio/issues/967)： 預期的查詢計劃當結果方格中選取 XML 顯示計畫。
   - 修正[發出 1023年](https://github.com/Microsoft/sqlopsstudio/issues/1023)： 從 flyfishingdba 新增 ms_foreachdb 呼叫的方括號。
   - 修正[發出 1048年](https://github.com/Microsoft/sqlopsstudio/issues/1048)： 登入前 SSL/TLS 信號交換時發生錯誤。
   - 修正[發出 1050年](https://github.com/Microsoft/sqlopsstudio/issues/1050)： 清除 insights 檢視之前顯示錯誤。
   - 修正[發出 1057年](https://github.com/Microsoft/sqlopsstudio/issues/1057)： 還原和檔案總管 widget 中的新查詢動作已中斷。
   - 修正[發出 1068年](https://github.com/Microsoft/sqlopsstudio/issues/1068)： 儀表板輸出 windows 快顯上使用 Azure SQL Database 的錯誤訊息。
   - 修正[發出 1069年](https://github.com/Microsoft/sqlopsstudio/issues/1069)： 連接對話方塊顯示時最初顯示的所需的伺服器錯誤。
   - 修正[發出 1070年](https://github.com/Microsoft/sqlopsstudio/issues/1070)： 伺服器群組現在需要按兩下以展開。
   - 修正[發出 1072年](https://github.com/Microsoft/sqlopsstudio/issues/1072)： 選取控制項的背景是半透明效果。
   - 修正[發出 1115年](https://github.com/Microsoft/sqlopsstudio/issues/1115)： 修正所有的高對比 SQL 作業 Studio 中的協助工具問題。
   - 修正[發出 1101年](https://github.com/Microsoft/sqlopsstudio/issues/1101)： 擴充功能無法升級 」 下載手動"連結會移至錯誤的位置。
   - 修正[發出 1103年](https://github.com/Microsoft/sqlopsstudio/issues/1103)： 無法在 [首頁] 索引標籤上運作的 V 捲軸。
   - 修正[發出 1104年](https://github.com/Microsoft/sqlopsstudio/issues/1104): SQL 延伸模組索引標籤停止運作。


對於年 4 月公開預覽的重要反白顯示為 Visual Studio 程式碼 1.21 平台來源的程式碼重新整理。 這會帶中的多個更新的核心編輯器和工作臺從先前的 1.19 同步處理點。 一些範例包括下列各項：

- [新的通知 UI](https://code.visualstudio.com/updates/v1_21#_new-notifications-ui) -輕鬆地管理與檢閱 SQL 作業 Studio 通知。
- [整合終端機分割](https://code.visualstudio.com/updates/v1_21#_split-terminals)-一次使用多個開啟的終端機。
- [儲存大型和受保護的檔案](https://code.visualstudio.com/updates/v1_20#_save-files-that-need-admin-privileges)-儲存受保護的系統管理員和 > 在 SQL 作業 Studio 256 M 檔案。
- [改善大型檔案支援](https://code.visualstudio.com/updates/v1_21#_text-buffer-improvements)-大型檔案的文字緩衝區最佳化。
- [改善的設定搜尋](https://code.visualstudio.com/updates/v1_20#_settings-search)-輕鬆地找出使用自然語言搜尋正確的設定。
- [全域程式碼片段](https://code.visualstudio.com/updates/v1_20#_global-snippets)層建立程式碼片段，您可以跨所有檔案類型使用。
- [總管 中複選](https://code.visualstudio.com/updates/v1_20#_multi-select-in-the-explorer)-多個檔案上一次執行的動作。
- [錯誤和警告，在 [總管]](https://code.visualstudio.com/updates/v1_20#_error-indicators-in-the-explorer) -可以快速地瀏覽至您的程式碼基底中的錯誤。
- [拖曳和卸除、 複製和貼上整個 windows](https://code.visualstudio.com/updates/v1_21#_better-drag-and-drop-support) -在開啟的 SQL 作業 Studio 視窗之間移動檔案。
- [Git 子模組支援](https://code.visualstudio.com/updates/v1_20#_git-submodules)-巢狀的 Git 儲存機制上的執行 Git 作業。
- [終端機螢幕讀取器支援](https://code.visualstudio.com/updates/v1_20#_screen-reader-support)-整合式終端機現在有 「 螢幕的讀取器最佳化 」 模式。
- [置中的編輯器配置](https://code.visualstudio.com/updates/v1_21#_centered-editor-layout)-將您的程式碼檢視螢幕面積最大化。
- [水平的搜尋結果 （預覽）](https://code.visualstudio.com/updates/v1_21#_horizontal-search) -您可以在水平台中現在檢視搜尋結果。

如需詳細資訊，簽出[Visual Studio 程式碼年 2 月版本資訊](https://code.visualstudio.com/updates/v1_21)，而[Visual Studio 程式碼年 1 月版本資訊](https://code.visualstudio.com/updates/v1_20)。

如需詳細資訊，請參閱[變更記錄](https://github.com/Microsoft/sqlopsstudio/blob/master/CHANGELOG.md)。

## <a name="march-2018-march-public-preview"></a>年 3 月 2018 （年 3 月公開預覽）

發行日期： 2018 年 3 月 28，  
版本： 0.27.3

*年 3 月公用預覽*繼續處理最上層的 GitHub 問題而重點在於提升擴充性故事。 特別啟用擴充功能管理員，改善儀表板管理，並提供 SQL 代理程式和 insights 擴充功能。 此版本包含下列增強功能：

- 增強的支援索引標籤式的深入資訊和組態窗格的儀表板擴充性模型。
   - 擴充管理員可讓簡單擷取的延伸模組。
   - 儀表板延伸從 sp_whoisactive [whoisactive.com](http://www.whoisactive.com)。
   - 如需詳細資訊，請參閱[擴充功能的 SQL 作業 Studio](extensions.md)。
- 請加入更多[連線和物件總管 中的擴充性 Api](https://github.com/Microsoft/sqlopsstudio/wiki/Extensibility-API)管理。
- 若要修正重要影響的客戶繼續[GitHub 問題](https://github.com/Microsoft/sqlopsstudio/issues)。


## <a name="february-2018-february-public-preview"></a>2018 年 2 月版 （ 2 月公開預覽）

發行日期： 2018 年 2 月 15，  
版本： 0.26.7

*年 2 月公用預覽*含有一些功能建議和高優先順序的 bug 修正。 此版本包含下列增強功能：

- 簡介安裝自動更新，這樣會提供通知可用於下載新版本時 
- 連接對話方塊 'Database' 欄位現在是以動態方式填入的下拉式清單將包含從指定的伺服器填入資料庫清單。
- 修正[發出 6](https://github.com/Microsoft/sqlopsstudio/issues/6)： 使連接與選取的資料庫開啟新查詢索引標籤。
- 修正[發出 22](https://github.com/Microsoft/sqlopsstudio/issues/22): ' Server Name' 和資料庫名稱-可以這些是下拉式清單而不是文字方塊？
- 修正[發出 549](https://github.com/Microsoft/sqlopsstudio/issues/549)： 無訊息/非常無訊息安裝會導致在安裝之後開啟應用程式。
- 修正[發出 481](https://github.com/Microsoft/sqlopsstudio/issues/481)： 加入 「 檢查更新 」 選項。
- SQL 編輯器顏色標示和自動完成修正：
   - 修正[發出 584](https://github.com/Microsoft/sqlopsstudio/issues/584): 「 完整 」 不反白顯示的 intellisense 的關鍵字。
   - 修正[發出 345](https://github.com/Microsoft/sqlopsstudio/issues/345)： 以色彩標示 SQL 函式，在編輯器中的。
   - 修正[發出 300](https://github.com/Microsoft/sqlopsstudio/issues/300): [#tempData] 最新"]"將會顯示綠色。
   - 修正[發出 225](https://github.com/Microsoft/sqlopsstudio/issues/225)： 關鍵字色彩不相符。
   - 修正[發出 60](https://github.com/Microsoft/sqlopsstudio/issues/60)： 無效的 sql 語法色彩反白顯示時使用 from 子句中的暫存資料表。
- 導入連線擴充性 API。
- VS Code 編輯器 1.19 整合。
- 更新拾取幾項查詢計劃檢視器改良 JustinPealing/html-查詢計劃元件。


## <a name="january-2018-january-public-preview"></a>2018 年 1 月 （ 1 月公開預覽）

發行日期： 2018 年 1 月 17 日，  
版本： 0.25.4

*1 月公用預覽*含有一些功能建議和高優先順序的 bug 修正。 此版本包含下列增強功能：

- 在 [連接] 對話方塊中可使用儲存的伺服器連接。
- 啟用熱結束。 根據預設，若要啟用，請參閱熱結束已關閉[熱結束設定](settings.md#hot-exit)。
- 索引標籤著色依據伺服器群組。 根據預設，若要啟用，請參閱已關閉的索引標籤著色[索引標籤的色彩設定](settings.md#tab-color)。
- 變更*伺服器名稱*至*伺服器*連接對話方塊中。
- 修正中斷*執行目前查詢*命令。
- 修正 bug 的指令碼的拖放中斷。
- 修正不正確的 [開始] 功能表釘選的圖示。
- 修正遺失商標圖示的 Azure 帳戶。


## <a name="december-2017-december-public-preview"></a>2017 年 12 月（12 月公開預覽）

發行日期： 2017 年 12 月 19，  
版本： 0.24.1

*年 12 月公用預覽*跨所有功能區域，以及下列增強功能包括數個 bug 修正：

- 建立防火牆規則 對話方塊現在是可以協助您連接到 Azure SQL Database 和 Azure SQL 資料倉儲。
- 加入的 Windows 安裝程式，以及 Linux DEB 和 RPM 安裝封裝。
- 管理儀表板視覺化配置編輯器。
- *指令碼做為 Alter*和*指令碼做為執行*命令。
- *執行目前查詢的實際計畫*命令。
- 整合 VS Code 1.18.1 編輯器平台。
- 啟用側載的 VSIX 擴充功能檔案。
- 支援"GO N"批次反覆運算語法。


## <a name="november-2017"></a>2017 年 11 月

發行日期： 2017 年 11 月 15 日，  
版本： 0.23.6

- 初始版本的[!INCLUDE[name-sos](../includes/name-sos-short.md)]。


## <a name="next-steps"></a>後續步驟

請參閱下列快速入門，若要開始使用其中一項：
- [連接及查詢 SQL Server](quickstart-sql-server.md)
- [連接及查詢 Azure SQL Database](quickstart-sql-database.md)
- [連接及查詢 Azure 資料倉儲](quickstart-sql-dw.md)

參與[!INCLUDE[name-sos](../includes/name-sos-short.md)]:
- [https://github.com/Microsoft/sqlopsstudio](https://github.com/Microsoft/sqlopsstudio)
