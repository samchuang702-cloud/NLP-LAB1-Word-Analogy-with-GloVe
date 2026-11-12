# NLP LAB1 — 使用 GloVe 進行詞彙類比與語意評估

## 專案簡介

本專案探討預訓練詞向量是否能捕捉英文單字之間的**語意關係**與**句法關係**。實作以 Google Analogy Test Set 為評估資料，使用 GloVe 預訓練詞向量進行向量運算，檢驗模型能否完成如「man : woman = king : ?」這類詞彙類比任務。

## 想解決的問題

- 詞向量能否以數學運算表達單字之間的關係？
- GloVe 在語意與句法類比任務上的表現如何？
- 哪些詞彙關係較容易或較難被模型辨識？
- 高維詞向量降維後，語意相關詞彙是否形成群聚？

## 技術方法

1. 下載並解析 Google Analogy Test Set。
2. 將題目區分為 semantic 與 syntactic 類別。
3. 載入 Gensim 的 `glove-wiki-gigaword-100` 預訓練模型。
4. 以 `word_b + word_c - word_a` 進行類比預測。
5. 計算各類別及子類別準確率。
6. 使用 t-SNE 將詞向量投影至二維空間。

## 實驗結果

| 評估類別 | 準確率 |
|---|---:|
| Semantic | 65.34% |
| Syntactic | 61.26% |
| Capital–Common Countries | 93.87% |
| Capital–World | 88.95% |
| Family | 81.62% |
| Currency | 14.20% |

GloVe 能有效捕捉部分地理、家庭與文法關係，但對貨幣及其他知識密集的關係仍有限制。

## 使用技術

Python、Pandas、NumPy、Gensim、GloVe、scikit-learn、t-SNE、Matplotlib、Google Colab。

## 專案亮點

- 完成資料解析、模型推論與分層評估流程。
- 分析語意、句法及多個細分類別，而非只呈現單一分數。
- 以視覺化方式解釋分散式語意表示。
- 展現 NLP、詞向量、實驗設計與結果解讀能力。

## 執行方式

1. 使用 Google Colab 或 Jupyter Notebook 開啟 `NLP_LAB1_Word_Analogy_GloVe.ipynb`。
2. 依序執行所有儲存格。
3. 首次執行會下載評估資料及 GloVe 模型，需保持網路連線。

## 未來改進

- 比較 Word2Vec、FastText 與不同維度的 GloVe。
- 加入 BERT 等 contextual embedding 作為對照。
- 深入分析 OOV 詞彙與錯誤案例。
