# BUAA_Pattern-recognition_Final
北航模式识别大作业，这里使用的是Pytorch神经网络进行花朵的识别（这个分类器的效果并不是很好，Test文件夹中有很多污染，但是可以尝试将这个程序移植到其他数据集上）<br />
<br />
<br />
**数据从老师给的文件里找花朵的那个数据集**<br />
**记得修改对应的文件地址**<br />
<br />
希望能帮到大家<br />

Final_CM.ipynb是用来画图的程序，提供了绘制混淆矩阵的方法<br />
Test1.0_py提供了单独调用模型对数据进行分类的方法，可以用于训练结束后的评估<br />
<br />
main.py是主程序，模型的定义和训练都在里面，（最初代的模型，效果比最终结果相差很多，且效率较低，但至少它已经能跑起来了（雾<br />
<br />
__**UpDate25.6.16**__:  
Main.0.5程序对于加载数据的部分进行了修改，这样数据会在开始训练前全部保存在RAM中，在训练过程中会显著加快训练速度（前提是GPU跟得上）可以充分你运用到GPU性能，<br />
需要注意的是，这一操作需要占用约5G的内存空间（如果不加载test文件夹则需要3.5G），用的时候注意自己的内存分配。<br />
这一程序在实验中主要用于遍历不同的卷积核与隐藏层尺寸对于模型最终的预测结果的影响，为后续选择合适的模型参数做准备。<br />
<br />
__**UpDate25.6.17**__:<br />
Main.1.0中加入了transformer机制，在test文件夹中的正确率得到了有效地提升，同时对于GPU性能运用也相对充分，然而，在尝试将Conv1层也进行transfer时模型数据量过大，显存直接被爆破！！！！<bar/>
更新了Lr的选择方式，现在的learningrate会跟随loss的优化而不断改进<br />
__**UpDate25.6.18**__:<br />
Main.1.2对于数据集的划分问题进行了进一步优化，严格划分了训练集、验证集、测试集，方便最终进行结果评价。<br />
![1_loss_accuracy](https://github.com/user-attachments/assets/ed5cce22-ee8e-4553-a806-c06440144d45)
![test_result](https://github.com/user-attachments/assets/3a08e351-8f3b-4f37-97e0-be440176b3da)



<br />
环境需要用到pytorch、opencv、numpy，可以用conda管理


  对于Main.1.2的训练结果在RESULT文件夹中的RESULT_6.4
