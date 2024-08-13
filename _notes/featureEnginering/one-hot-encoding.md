---
---

# One-hot encoding

One-hot encoding是一種將categorical變數轉換為numerical格式的方法。

主要特點:
- 為每個類別創建一個新的二進制列
- 原始類別列被替換為這些新的binary列
- 通常會刪除一個類別(k-1 encoding)以避免多重共線性

常用庫:
- Scikit-learn
- Feature-engine  
- Category Encoders

使用注意:
- 需要在訓練集和測試集上分別fit和transform
- 可能會產生大量的新特徵,尤其是對高基數變數

相關筆記:
[[Ordinal encoding]]
[[Mean encoding]]

代碼示例:
```python
from sklearn.preprocessing import OneHotEncoder

ohe = OneHotEncoder(drop="first", sparse_output=False)
ohe.fit(X_train)
X_train_encoded = ohe.transform(X_train)
X_test_encoded = ohe.transform(X_test)
```
