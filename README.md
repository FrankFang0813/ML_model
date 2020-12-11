# ML_model
Just Note


* 多元迴歸分析(線性)
```js
- 常見的迴歸係數估計方法:
  
  普通最小平方法(OLS):未知殘差的分配，使所有觀察值與估計值的殘差平方和最小。
  最大概似法(MLE):以知殘差的分配，使觀察樣本出現的機率最大(意即找出一組與觀察值最接近的參考值)。
  
  最常見的是普通最小平方法(Ordinary Least Squares, OLS)。
  
- 當為多元迴歸分析時(多個X)，需挑選適合的自變數X，分為三種方法:

  前向式(foreward):將X自變數一一加入模型，從最顯著的開始加(只加顯著的X)。
  後向式(backward):將自變數全部丟入模型，從最不顯著的自變數開始剔除(只踢不顯著的X)。
  逐步挑選(stepwise):＃較常使用＃綜合前向及後向，直至模型顯著後不剔除。(A變數顯著
                    ，加入B變數後，A變成不顯著而B顯著，則剔除A變數，後加入C變數，以此類推)。
                    
- 四大假設

  線性(Linearity):x與y是線性關係。
  常態性(Normality):若母體為常態分佈，則殘差項也要符合常態分佈。
  同質性(Heteroscedasticity):殘差項之間有相同的變異。
  獨立性(Independency):殘差項之間相互獨立。

優點:
    1.直觀，線性容易理解。
    2.限制多，樣本需求較少。
缺點:
    1.無法處理非線性問題。
    2.會有共線性問題，但無法解決線性組合高度相關的問題。
```
*正規化回歸 (Regularized Regression)

```js

＃＃確認線性迴歸有over-fitting問題，再試試看「正規化迴歸」。＃＃
L1和L2的參考學習影片:https://www.youtube.com/watch?v=TmzzQoO8mr4
https://medium.com/ai%E5%8F%8D%E6%96%97%E5%9F%8E/learning-model-l1-l2-regularization%E5%B7%AE%E7%95%B0-8d7fc089b35c

*LASSO Regression
  迴歸+L1 penalty(一階懲罰項,絕對值)
  LASSO不僅能正規化優化模型，還能自動執行變數篩選(Feature selection)。
  Lasso幫你識別並挑選出有最強訊號的一個變數。

* 嶺回歸(Ridge Regression)

  迴歸誤差平方和+L2 penalty(二階懲罰項,平方項)。
  將迴歸係數值平均地分散在各個變數之間。
  
＊彈性網罩模型(elastic nets)

  迴歸模型中，讓L1懲罰項與L2懲罰項都加入模型(權重相加=1)。
  LASSO為L2權重=0的型態，Ridge為L1權重=0的型態。
  
  
  
  參考資料:
  https://ithelp.ithome.com.tw/articles/10227654
  https://www.zhihu.com/question/38121173
  https://www.itread01.com/content/1542591853.html
  ```
  
  
  *羅吉斯迴歸(logistic regression)
  
  ```js
  
  為線性分類模型
  
  ＃不需要常態分配的假設＃
  
  使用的估計方法為最大概似估計法。
  
  建立二元類別機率值之成功勝率對數值的線性分類模型，
  羅吉斯迴歸的依變項(Y)主要為二元的類別變項(亦即是或否，0或1)，
  羅吉斯迴歸的自變項(X)，可以是類別變數，也可以是連續變數。
  
  羅吉斯迴歸使用的是sigmoid激活函數
  
  
  參考資料:
  https://medium.com/%E5%B1%95%E9%96%8B%E6%95%B8%E6%93%9A%E4%BA%BA%E7%94%9F/python%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-111-%E7%BE%85%E5%90%89%E6%96%AF%E5%9B%9E%E6%AD%B8%E5%88%86%E9%A1%9E%E5%99%A8%E4%BB%8B%E7%B4%B9%E5%8F%8A%E6%87%89%E7%94%A8-caa1cebcf831
  
  ```
  
  
  *樸素貝葉斯模型(Naïve Bayesian classifier)
  ```js
  
  為非線性分類模型
  
  基本假設為:
    1.每個變數之間相互獨立關係。
    2.每個變數同等重要(權重相等)。
    
  優點:
    1.速度快，簡單，有效。
    2.可用於多類別預測，並可獲得Y的各類別機率。
    3.只需少量樣本進行訓練。
    4.可以處理帶雜訊或遺缺值的資料(相對的，遺缺值會造成'零頻率'，導致某些特徵無法一起運算，須以平滑技術處理)。
  
  缺點:
    1.特徵同等重要且互相獨立的假設通常不符合現實狀況。
    2.不適合有大量數值屬性的資料集
    3.刪除重複出現的高度相關的特徵，可能會丟失頻率信息，影響效果

  參考網址：https://kknews.cc/code/ax2xkox.html
  
  ```
  
  *
