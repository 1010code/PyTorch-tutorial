# 神經網絡梯度下降 (Gradient Descent)
神經網路是當今最為流行的深度學習框架，它的原理主要是梯度下降的機制。優化能力是人類歷史上的重大突破，他解決了很多實際生活中的問題。比如說牛頓法(Newton's method)，最小二乘法(Least Squares method)，梯度下降法(Gradient Descent) 等等。而我們的神經網絡就是屬於梯度下降法這個分支中的一個提到梯度下降，我們不得不說說大學裡面學習過的求導求微分。

![](https://i.imgur.com/BNsuChF.png)

初學神經網絡的時候，我們通常會遇到這樣一個函式他叫loss function損失函數。損失函數是用來計算預測出來的和我們實際中的值有多大差別。在預測數值的問題中，我們常用均方差(Mean Squared Error)來代替。

神經網路的梯度下降可沒那麼簡單，神經網路中的W權重可不只有一個。如果有一個W就如下圖所示，如果有兩個W就以3D圖所示。超過三個就難以可視化出來了。

![](https://morvanzhou.github.io/static/results/ML-intro/gd3.png)

在簡化版的誤差曲線中，我們只要找到梯度線躺平的地方，就能能迅速找到誤差最小時的W。可是很多情況是這樣的，誤差曲線並不只有一個溝，而且梯度躺平的點也不止一個。不同的W初始化的位置，將會帶來不同的下降區域。不同的下降區域，又會帶來不同的W 解

![](https://morvanzhou.github.io/static/results/ML-intro/gd5.png)