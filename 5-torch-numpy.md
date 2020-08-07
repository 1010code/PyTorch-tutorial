## Numpy 與 Torch 轉換
torch 和 numpy 能很好的兼容，可以自由地轉換 numpy array 和 torch tensor。

```py
import torch
import numpy as np

np_data = np.arange(6).reshape((2, 3)) # numpy array
torch_data = torch.from_numpy(np_data) # 轉換成 32bit tensor
tensor2array = torch_data.numpy() # tensor to numpy array
print(
    '\nnumpy array:', np_data,          # [[0 1 2], [3 4 5]]
    '\ntorch tensor:', torch_data,      #  tensor([[0, 1, 2],[3, 4, 5]]) 
    '\ntensor to array:', tensor2array, # [[0 1 2], [3 4 5]]
)
```


## Torch 中的數學運算
torch 中 tensor 的運算和 numpy array 的數學運算其實大同小異。如果想了解更多 torch 運算符可[參考](https://pytorch.org/docs/stable/torch.html)。
```py
# abs 絕對值計算
data = [-1, -2, 3, 4]
tensor = torch.FloatTensor(data)  # 轉換成 32bit tensor
print(
    '\nabs',
    '\nnumpy: ', np.abs(data),          # [1 2 3 4] 
    '\ntorch: ', torch.abs(tensor)      # tensor([1., 2., 3., 4.])

)

# sin   三角函數 sin
print(
    '\nsin',
    '\nnumpy: ', np.sin(data),      # [-0.84147098 -0.90929743  0.14112001 -0.7568025]
    '\ntorch: ', torch.sin(tensor)  # tensor([-0.8415, -0.9093,  0.1411, -0.7568])
)

# mean  均值
print(
    '\nmean',
    '\nnumpy: ', np.mean(data),         # 1.0
    '\ntorch: ', torch.mean(tensor)     # tensor(1.)
)
```



## 矩陣運算
矩陣運算是神經網絡中最重要的部分，所以我們展示下矩陣的乘法
- `numpy.matmul()` 和 `torch.mm()` 是矩陣乘法（叉乘），
- `numpy.multiply()` 和 `torch.mul()` 是矩陣點乘（對應元素相乘）
```py
# matrix multiplication 矩陣乘點
data = [[1,2], [3,4]]
tensor = torch.FloatTensor(data)  # 轉換成 32bit tensor
# correct method
print(
    '\nmatrix multiplication (matmul)',
    '\nnumpy: ', np.matmul(data, data),     # [[7, 10], [15, 22]]
    '\ntorch: ', torch.mm(tensor, tensor)   # tensor([[ 7., 10.],[15., 22.]])
)
```