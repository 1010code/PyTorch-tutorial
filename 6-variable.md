# 變數(Variable)

新版本中，torch.autograd.Variable 和torch.Tensor 將同屬一類。更確切地說，torch.Tensor 能夠追踪日誌並像舊版本的Variable 那樣運行; Variable 封裝仍舊可以像以前一樣工作，但返回的對像類型是torch.Tensor。這意味著你的代碼不再需要變量封裝器。