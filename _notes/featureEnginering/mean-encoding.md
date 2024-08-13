---
---

# Mean encoding

Mean encoding(也稱為target encoding)是一種將categorical變數轉換為數值的方法,使用目標變數的平均值來替換類別。

主要特點:
- 用目標變量的平均值替換每個類別
- 可以捕捉類別與目標之間的關係
- 適用於高基數categorical變數

實現方法:
1. 簡單方法:使用整個訓練集計算平均值
2. Expanding window:使用時間序列數據的歷史平均值

使用注意:
- 容易導致過擬合,尤其是對於低頻類別
- 需要小心處理時間序列數據以避免數據洩露

相關筆記:
[[One-hot encoding]]
[[Ordinal encoding]]

代碼示例(簡單方法):
```python
from feature_engine.encoding import MeanEncoder

me = MeanEncoder()
me.fit(X_train, y_train)
X_train_encoded = me.transform(X_train)
X_test_encoded = me.transform(X_test)
```

代碼示例(Expanding window):
```python
encoded = (
    df.groupby(['category'])['target']
    .expanding()
    .mean()
    .shift()
).reset_index()
```
