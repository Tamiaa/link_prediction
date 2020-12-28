# link_prediction
## Introduction
  目前，用户可以在论文搜索网站（如Google Scholar和Baidu academical）中输入自己喜欢的关键词搜索自己感兴趣的论文，然后这些网站会向他们推荐合适的论文。  
  用户通常通过在研究任务中加入以下关键词来实现自己的目标：（1）链路预测解决了被引网络的稀疏性；（2）在链路预测中采用了加权准则，（3） 数据挖掘是指从网络中挖掘出的论文信息，并将其应用到加权方法中；（4）引文网络用于研究论文之间的被引关系。  
  用户获得一组关键字，包括链接预测、加权准则、数据挖掘和引文网络。然后，论文搜索网站通常会根据上述关键词向用户推荐一些论文。  
  在本文中，我们从论文的基本信息中提取特征，训练网络来对两篇论文是否具有引用关系进行预测。  
## File Description
  link_prediction.ipynb   
  training_set.txt 训练样本对，两个论文的编号，最后一列为标签，0：没有引用，1：有引用。  
  Testing_set.txt测试数据集，两篇论文的编号，输入给训练好的模型，用于预测论文间是否有引用。  
  node_information.csv 训练数据集中论文的详细信息，包括编号、年份、标题、作者名、类型、和概括内容。从这个文件中提取出训练所需要的特征（年份的关系，标题的相似度，作者的相似度），输入模型进行训练。
## Method
  问题定义：根据paper之间的相似度进行训练，对paper pair 是否具有引用关系进行预测。  
  算法：梯度提升分类器。
## Processes and Result
  首先要从训练数据中提取训练分类器所需要的各种特征（年份的关系，标题的相似度，作者的相似度）。之后调用上一节的梯度提升分类器对训练数据的各种特征进行拟合，得到训练好的模型。
然后对测试数据集进行预测，将预测结果与实际标签进行比较。
最后检查分类器的精度，使用了f1 score作为评估的指标。
  F1 score是准确率和召回率的调和平均数，本实验中，测试的F1 score达到了0.8047。
## Bibliography
[1] L.M. Aiello et al., Friendship prediction and homophily in social media. ACM Trans. Web (TWEB) 6(2), 9 (2012)   
[2] C. Lee et al., How to assess patent infringement risks: A semantic patent claim analysis using dependency relationships. Tech. Anal. Strat. Manag. 25, 23–38 (2013)   
[3] L. Lü et al., Link prediction in complex networks: A survey. Phys. A 390(6), 1150–1170 (2011)   
[4] A. Clauset et al., Hierarchical structure and the prediction of missing links in networks. Nat. Publ. Group 453, 98–101 (2008)   
[5] R.H. Li et al., in Proceedings of the 20th ACM International Conference on Information and Knowledge Management. CIKM’11. Link prediction: The power of maximal entropy random walk (2011), pp. 1147–1156  
