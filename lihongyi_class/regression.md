
* gradient descent
* overfitting & regularization

为啥梯度下降的时候，用到所有的，开始我简单的想象成一条线，然后一个w，直线方程求导，而事实是，我们在求w的时候，这个时候w是自变量，x是参数，而且不是对直线求导，直线只是我们的model，我们的function，梯度下降是针对loss_function的，而我们的loss_function用到了所有的样本，我们希望每个output和label的loss加起来最小，所有梯度下降和model不是关联的，和loss_funciotn才是，我们是求解loss最小。是求解loss最小的那组对应的medol。

### 何为机器学习：

```    实际上  机器学习  就是一堆function  我们去选出最好的function  当然这里的function是说具体的系数已经确定好了，ax+b这里的a和b都已经确定好了。我们将这个 function set 叫做model，机器学习的过程就是 去找出一个合适的，令我们满意的 function set，这里有点像参数空间，hough变换，我们不知道哪些参数是合适的，我们需要去找出来，所以说这是机器学习，让机器去找出合适的function。我们给定的是loss或者说好坏，一个评判标准，机器按着这个标准知道自己是否达到了要求。```

![avatar](/home/later/Pictures/exampleofml.png)

```从上图我们可以知道，一个神经网络大体结构，虽然没有展示隐藏层，但是input和output都有了，中间的隐藏层也是机器该学习的。Goodness of funciotn就是lossfunction，我们去告诉机器这组function怎么样。```

#### 大体步骤
![avatar](/home/later/Pictures/stepsofml.png)
首先我们定义model也就是function_set，或者说网络框架，然后我们定义lossfunction，一个评价指标，最后我们就是要去迭代的找出那个最好的function_set

- 确定Model：Model就是a set of function（函数的集合），一个Model有很多个函数，通过函数我们得到想要的output。

- 评价函数（Goodness of function）:因为有许多的函数，我们要通过一个确定的方式去挑选出最好的函数，通常我们用loss function 去评价一个函数的好坏。

- 挑选并使用函数。

#### ml learning map
![avatar](/home/later/Pictures/mllearingmap.png)
我们能轻松的得到数据的时候，我们就可以用supervised learning，否则我们可以选用reinforcement learning，在alphago里面使用了reinforcement learning。

> 这里都已经提到了regression，那我就顺便说说。何为线性，线性就可以理解为一条直线，y=ax+b，就可以这样理解，想到了我当时研一上工程数学的时>候，有一些样本点，我们去拟合这些样本点，如果是直线的话，可能得不到很好的结果，用曲线比较好。何为回归，很简单，指的就是说这>个function_set得到一个具体的值。想对于分类来说。 为什么线性的model没有local_minma，因为直线都是一个方向上升或者下降的。不存在起伏。所以在李宏毅老师的例子中，加入了x的高次项，也就是加入了非线性，这样的话呢，在train_data上面当然是越来越好，但是在tseting_data上面却不一定，这就是过拟合。overfitting
![avatar](/home/later/Pictures/goodnessofcomplexmodel.png)
- 越复杂的model会包含简单的model。

</br>
</br>
</br>

### 李宏毅老师是如何引出正则化的？regularization
> 我们为了能降低loss，使用了更复杂的model，更多的参数，我们不知道哪些是有用的，但加到了少量的样本中，这样有过拟合的风险，所以引入正则化。当时在唐宇迪的课程中，解释的是一些不同的权重参数可能会得到一样的output，我们要将这些不同的权重参数区分开来，我觉得也是合理的。
![avatar](/home/later/Pictures/regularization.png)

从这个公式来看，我们为啥期待w越小呢，这样就会越平滑，平滑是指，我们的output不会有太大的波动，肯定啊，这比w大的时候output的曲线要平滑很多。 同时呢，我们为了让我们的function考虑少噪声，这同时就会在train_data上面表现得没有那么好，但是在testing_data上面是可能会更好的。

##### why we need smooth functions?
![avatar](/home/later/Pictures/why_we_need_smooth_functions.png)
如果我们数据中有很多误差，这样我们的网络会更加健壮。但是我们自然而然的想到，太平滑的function什么都干不了。

- 超参数调参，这个正则化的lamuda，我们应该给到多少合适呢，需要我们实验看看。
![avatar](/home/later/Pictures/regularization_lamuda.png)
- 在做正则化的时候，是不需要考虑bias这项的。因为调整bias跟function的平滑程度是没有关系的。
我们来看看调整regularization的结果。
![avatar](/home/later/Pictures/regularization_infacts.png)
