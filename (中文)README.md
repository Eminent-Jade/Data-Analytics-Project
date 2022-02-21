# 數據分析項目


## 項目概述

這是對悉尼科技大學 (UTS) 11 號樓的房間02.412（數據競技場）及 12_431（分析室）的室內環境中，房間使用者的熱舒適感覺的探索性數據分析。（請參閱「Images」文件夾），採用的是「EIF」研究項目的數據傳感器接口收集的相應歷史溫度和濕度數據集（2021 年 5 月 1 日至 2021 年 7 月 30 日）。

https://eif-research.feit.uts.edu.au/


Python 工具包 – 「pythermalcomfort」、美國採暖製冷空調工程師協會（ASHRAE）的室內環境熱舒適標準及其理論應用於溫度和濕度數據集的分析和可視化。

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd


須做出以下幾個假設以簡化分析項目的背景：

- 空氣溫度 = 平均輻射溫度（成為「運行溫度」，假設相對空氣速度 = 0.1 m/s，即室內空氣和物件表面（例如牆壁、地板、天花板）之間的熱傳遞可忽略不計。）
- 相對空氣速度 (vr) = 0.1 m/s（用於簡單的熱傳遞計算）
- 衣服熱阻（clo）= 1.0 clo（典型的冬季室內服裝）
- 新陳代謝率(met) = 1.1 met（打字，兩個房間使用者的典型日常工作）


## 項目涵蓋的主題

- 數據收集和操作（NumPy、Pandas DataFrames （數據幀）及（數組）、轉換數據類型、數據合併、重新排序列）
- 數據可視化、單變量（分類特徵和柱狀計數圖）及雙變量分析（線圖、散點圖、回歸線、jointplot）
- 描述性統計（箱形圖、最大值、最小值、平均值、標準差、四分位距（IQR））
- 用數據敘事


## 目錄

1. 提取數據並構建初始數據幀（DataFrame）
2. 對數據進行分類
3. 將所有溫度和濕度數據幀合併（merge）為一
4. 數據類別及趨勢的可視化
5. 採用「pythermalcomfort」工具包運算 pmv & ppd 指數及可視化
6. 在房間02-412最初給人「暖/熱」感覺的時隙中，採用新的衣服熱阻（'clo' ）值
7. 結論


## 數據概述

採用了由分別位於兩個房間內的傳感器所收集的溫度及濕度的線性數字數據集。

研究項目的數據傳感器接口由Australian Government's Education Investment Fund (EIF) （直譯：澳洲政府的教育投資基金）資助。

https://eif-wiki.feit.uts.edu.au/eif_overview

然而，學院的技術服務經理（Technical Services Manager）告知：由於技術/維護問題（請參閱電子郵件對話的「Images」文件夾），所以本項目僅採用溫度和相對濕度數據集進行分析。數據集直接從 url 鏈結複製到 .txt 文件，而不是從搜索引擎下載（請參閱「Data」文件夾）。

## 關於悉尼科技大學（UTS） 11 號樓

憑藉其廣泛的「可持續性」特點（能源、用水量等），悉尼科技大學 11 號樓曾經獲得澳洲綠色建築委員會 （GBCA）授予「綠色之星 - 教育設計 v1」的5 星評級。

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

除了可持續性方面，熱舒適、空氣質量等室內環境因素也對使用者的體驗和建築自身的受歡迎程度起著至關重要的作用。


## 關於熱舒適度、預測平均投票數(pmv) 和不滿意者的百分比 (ppd)

熱舒適度是使用者對環境熱量的感覺的滿意程度，取決於幾個因素，包括但不限於：氣溫、平均輻射溫度、濕度、相對空氣速度、新陳代謝率和衣服熱阻，本項目將採用「pmv/ppd 評價指標」。

根據 「ASHRAE 標準 55」，如建築物內使用者的新陳代謝率在 1.0 met及 1.3 met之間，及衣服提供 0.5 clo 到 1.0 clo 的熱阻性的話，「舒適區」代表「預測平均投票數」（pmv）為 - 0.5 到 + 0.5之間 及「不滿意者的百分比」（ppd）在10%或以下。

如欲深入了解熱舒適理論，請參閱：

https://www.designingbuildings.co.uk/wiki/Predicted_mean_vote

https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

https://www.designingbuildings.co.uk/wiki/Indoor_air_velocity

https://roastsurvey.com/blog-post/understanding-clo-values/

http://www.sensiblehouse.org/nrg_comfort.htm

https://www.designingbuildings.co.uk/wiki/Operative_temperature


## 運算熱舒適度的便利工具

https://comfort.cbe.berkeley.edu/

如須模擬我的項目中的設置：

- 在圖表頂部的選項面板中選擇「相對濕度與空氣溫度」（ 'Relative humidity vs air temperature'）
- 在「Select method」中選擇「PMV method」
- 選中「運行溫度」（Operative temperature）框
- 嘗試不同的「服裝水平」（clothing level）和「代謝率」（Metabolic rate）數值，
- 然後輸入溫度和濕度，例如：

![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)
