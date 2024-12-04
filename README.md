# Fashion Mnist
## 專案說明
Fashion-Mnist資料集包含了7萬張不同類別的圖片(10個類別)，每張都為28x28的灰階圖片。

| 類別 | 商品 |
|:---:|------|
| 0 |	T-shirt/top |
| 1	| Trouser |
| 2	| Pullover |
| 3	| Dress |
| 4	| Coat |
| 5	| Sandal |
| 6	| Shirt |
| 7	| Sneaker |
| 8	| Bag |
| 9	| Ankle boot |

## 建立模型
* np.eye(10)建立一個10x10的矩陣，並根據類別(0~9)做索引，生成對應的編碼。

![image](https://github.com/user-attachments/assets/e7068b76-ea81-416d-8be4-1c10715c4af3)

* 利用 Keras 建立一個 卷積神經網絡（CNN）模型
  - Sequential: 依順序堆疊層。
  - Conv2D: 卷積層，提取圖片特徵。比如第一層使用32個3x3大小的卷積核生成feature maps，激活函數ReLU引入非線性，
      input_shape=(28, 28, 1)定義輸入的形狀 (28x28, 一個通道)。
  - MaxPooling2D: 池化層，用來壓縮圖片大小。以(2, 2)大小分割區域，並對每個區域取最大值。
  - Dropout: 0.25 表示以 25% 的概率隨機丟棄神經元，避免過擬合。
  - Flatten: 將多維特徵圖轉換為一維向量，來做Dense layer的輸入。
  - Dense: 全連接層，連結輸入神經元與輸出神經元。softmax將輸出的神經元映射成機率的數值。

![image](https://github.com/user-attachments/assets/6bc56690-9e22-4362-a47f-0e53a64b0860)


## 資料集來源
<https://github.com/zalandoresearch/fashion-mnist>
 


