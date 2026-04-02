Task 1
--------------------------------------------------------------------------------------------------------------
Identify which column in the dataset is the label, and which column,
if included as a feature, would introduce data leakage. For each, write one sentence justifying your choice.

-> repeat_purchase_flag column in the dataset is the lable. Because it is our target variable.
-> discount_used_on_repeat_order is a leaky feature which can affect our dataset. So we should remove it.

Task 2
--------------------------------------------------------------------------------------------------------------
Your manager skips straight to training a gradient boosting model. 
Suggest two steps from the complete ML workflow that should have been completed first, 
and briefly explain why each step matters before jumping to a complex model.

-> Data Splitting:
  Using the same data for both training and testing can give us 100% accuracy but it will always fail in the real-life datas.
  So before training we should split our data into training, testing and validating data we will give us a good ML-model.

-> Features 
  Identifying the good feature and bad feature will always be good thing for our model.
  Because bad features can lead to data leakage, which will affect the accuracy of our model.
  SO its always best to identify bad feature and if nesscary drop the bad features to get a better output.
