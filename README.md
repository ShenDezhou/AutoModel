# AutoModel
DNN made simple: a practical approach to build a State of The Art model for your data

#定义#
：采用商业技术快速建立预测性模型，并将其应用于商业活动，从而改进决策过程

#Methodology#：
输入包含字段头的csv格式的数据，指定预测字段，指定模型算法（"AFM", "DCN", "MLR",  "DeepFM", "MLR", "NFM", "DIN", "FNN", "PNN", "WDL", "xDeepFM", "AutoInt“）  
建模工具自动进行稀疏字段、稠密字段识别  
输出使用Keras训练数据的过程，按照80/20的划分对模型进行训练，并用测试数据对模型进行log_loss, roc_auc_score计算  
优点：快速比较各个模型对于目标数据集的差异，自动选择最优模型  

#API#  
命令行接口   
启动建模工具后，输入数据文件名，预测字段，算法名称  

#Input#：
filename:  
target:  
choose a model: afm,autoint,dcn,deepfm,din,fnn,mlr,nfm,pnn,wdl,xdeepfm  

#Output：#
Train on 128 samples, validate on 32 samples  
Epoch 1/100  
- 4s - loss: 0.6552 - binary_crossentropy: 0.6551 - auc: 0.6212 - val_loss: 0.6223 - val_binary_crossentropy: 0.6223 - val_auc: 0.6823  
…  
Epoch 100/100  
 - 0s - loss: 1.1989e-04 - binary_crossentropy: 8.0650e-06 - auc: 1.0000 - val_loss: 0.0011 - val_binary_crossentropy: 9.7462e-04 - val_auc: 1.0000  
test LogLoss 0.0009  
test AUC 1.0  

#结论#  
AUC值为1，说明了xDeepFM模型在该数据集上是一个SOTA的算法

