# 數據分析項目


## 項目概述

這是以分析及可視化悉尼科技大學 (UTS) 11 號樓的房間02.412（數據競技場）及 12_431（分析室）的室內環境歷史溫度和濕度數據集，及運算相應的熱舒適指數結果，找出房間使用者的熱舒適程度所做的探索性數據分析項目。

項目涵蓋的主題：

- 數據收集和操作（NumPy、Pandas DataFrames （數據幀）及（數組）、轉換數據類型、數據合併、重新排序列）
- 數據可視化、單變量（分類特徵和柱狀計數圖）及雙變量分析（線圖、散點圖、回歸線、jointplot）
- 描述性統計（箱形圖、最大值、最小值、平均值、標準差、四分位距（IQR））
- 對外部python工具包的運用
- 用數據敘事


## 數據概述

採用了由2021 年 5 月 1 日至 2021 年 7 月 30 日，由分別位於兩個房間內的傳感器所收集的溫度及濕度的線性數字數據集（請參閱「Images」文件夾）。

「EIF」研究項目的數據傳感器接口由Australian Government's Education Investment Fund (EIF) （直譯：澳洲政府的教育投資基金）資助，用以監控大廈的可再生能源系統、以及各種外在及內在環境因素。

https://eif-research.feit.uts.edu.au/

https://eif-wiki.feit.uts.edu.au/eif_overview

然而，學院的技術服務經理（Technical Services Manager）告知：由於技術/維護問題（請參閱「Images」文件夾的電子郵件對話），故本項目僅採用溫度和相對濕度數據集進行分析。數據集直接從 url 鏈結複製到 .txt 文件，而非從搜索引擎下載（請參閱「Data」文件夾）。


## 關於熱舒適度、預測平均投票數(pmv) 和不滿意者的百分比 (ppd)

熱舒適度是使用者對環境熱量的感覺的滿意程度，取決於幾個因素，包括但不限於：氣溫、平均輻射溫度、濕度、相對空氣速度、新陳代謝率和衣服熱阻，本項目將採用由丹麥教授 Povl Ole Fanger 所研發的「pmv/ppd 評價指標」。

簡單來說，PMV 是一個用來預測一組使用者的投票平均值的7分制熱感覺指數；「PPD」是一個與「PMV」相關的指數，用於預測對熱舒適度不滿意的使用者百分比。

根據 「ASHRAE 標準 55」，如建築物內使用者的新陳代謝率在 1.0 met及 1.3 met之間，及衣服提供 0.5 clo 到 1.0 clo 的熱阻性的話，「舒適區」代表「預測平均投票數」（pmv）為 - 0.5 到 + 0.5之間 及「不滿意者的百分比」（ppd）在10%或以下。

如欲深入了解熱舒適理論，請參閱：

https://www.designingbuildings.co.uk/wiki/Predicted_mean_vote

https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

https://www.designingbuildings.co.uk/wiki/Indoor_air_velocity

https://roastsurvey.com/blog-post/understanding-clo-values/

http://www.sensiblehouse.org/nrg_comfort.htm

https://www.designingbuildings.co.uk/wiki/Operative_temperature


## 假設

須做出以下幾個假設以模擬分析項目的背景：

- 空氣溫度 = 平均輻射溫度（成為「運行溫度」，假設相對空氣速度 = 0.1 m/s，即室內空氣和物件表面（例如牆壁、地板、天花板）之間的熱傳遞可忽略不計。）
- 相對空氣速度 (vr) = 0.1 m/s（用於簡單的熱傳遞計算）
- 衣服熱阻（clo）= 1.0 clo（典型的冬季室內服裝）
- 新陳代謝率(met) = 1.1 met（打字，兩個房間使用者的典型日常工作）


## 方法

首先，對溫度及濕度進行操作、分析及可視化，以找出其趨勢、它們之間的關係及類別分佈。

之後，採用 Python 工具包 – 「pythermalcomfort」、「美國採暖製冷空調工程師協會（ASHRAE）的室內環境熱舒適標準」及其理論，運算熱舒適指數「pmv & ppd」，並以相似的方式分析和可視化。

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd

然後，比較「溫度和濕度」及「pmv和ppd」指數對使用者的室內熱舒適感的代表性。

最後，在一部分給使用者帶來「暖/熱」時隙時間段內，改變衣服熱阻數值，並重新計算「pmv & ppd」指數以查看改善%。


## 目錄

1. 提取數據並構建初始數據幀（DataFrame）
2. 對數據進行分類
3. 將所有溫度和濕度數據幀合併（merge）為一
4. 數據類別及趨勢的可視化
5. 採用「pythermalcomfort」工具包運算 「pmv & ppd」指數及可視化
6. 在房間02-412最初給人「暖/熱」感覺的時隙中，採用新的衣服熱阻（'clo' ）值
7. 結論


## 關於悉尼科技大學（UTS） 11 號樓

憑藉其廣泛的「可持續性」特點（能源、用水量等），悉尼科技大學 11 號樓曾經獲得澳洲綠色建築委員會 （GBCA）授予「綠色之星 - 教育設計 v1」的5 星評級。

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

除了可持續性方面，熱舒適、空氣質量等室內環境因素也對使用者的體驗和建築自身的受歡迎程度起著至關重要的作用。


## 運算熱舒適度的便利工具

https://comfort.cbe.berkeley.edu/

如須模擬我的項目中的設置：

- 在圖表頂部的選項面板中選擇「相對濕度與空氣溫度」（ 'Relative humidity vs air temperature'）
- 在「Select method」中選擇「PMV method」
- 選中「運行溫度」（Operative temperature）框
- 嘗試不同的「服裝水平」（clothing level）和「代謝率」（Metabolic rate）數值，
- 然後輸入溫度和濕度，例如：

![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)
