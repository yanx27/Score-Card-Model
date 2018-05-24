﻿# 评分卡模型

#
##数据导入和建立<br> 
1，读入数据<br> 
2，选择合适的建模样本<br> 
3，数据集划分成训练集和测试集<br> 

##第一步：数据预处理，包括<br> 
（1）数据清洗<br> 
（2）格式转换<br> 
（3）确实值填补<br> 

##第二步：变量衍生

##第三步：分箱，采用ChiMerge,要求分箱完之后：<br> 
（1）不超过5箱<br> 
（2）Bad Rate单调
（3）每箱同时包含好坏样本<br> 
（4）特殊值如－1，单独成一箱

###连续型变量可直接分箱<br> 
类别型变量：<br> 
（a）当取值较多时，先用bad rate编码，再用连续型分箱的方式进行分箱<br> 
（b）当取值较少时：<br> 
  （b1）如果每种类别同时包含好坏样本，无需分箱<br> 
  （b2）如果有类别只包含好坏样本的一种，需要合并<br> 

##第四步：WOE编码、计算IV

##第五步：单变量分析和多变量分析，均基于WOE编码后的值<br> 
（1）选择IV高于0.02的变量<br> 
（2）比较两两线性相关性。如果相关系数的绝对值高于阈值，剔除IV较低的一个
 
##第六步：逻辑回归模型。<br> 
要求：<br> 
1，变量显著<br> 
2，符号为负<br> 