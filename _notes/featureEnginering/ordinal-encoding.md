---
---

# Ordinal encoding

Ordinal encoding將categorical變數轉換為整數值。

主要特點:
- 為每個類別分配一個唯一的整數
- 保留了單一列,不會增加特徵數量
- 假設類別之間有順序關係

常用庫:
- Scikit-learn
- Feature-engine
- Category Encoders

使用注意:
- 需要在訓練集和測試集上分別fit和transform
- 對於無序類別變數,分配的整數可能會引入錯誤的順序關係

相關筆記:
[[One-hot encoding]]
[[Mean encoding]]

代碼示例:
```python
from sklearn.preprocessing import OrdinalEncoder

oe = OrdinalEncoder()
oe.fit(X_train)
X_train_encoded = oe.transform(X_train)
X_test_encoded = oe.transform(X_test)
```
