# Attentive Group Recommendation
基于注意力机制的群组推荐系统实现
使用注意力机制动态的从数据中去学习聚合策略

## Environment Settings
We use the framework pytorch. 
- pytorch version:  '0.3.0'
- python version: '3.5'

## Example to run the codes.

Run AGREE:

```
python main.py
```

After training process, the value of HR and NDCG in the test dataset will be printed in command window after each optimization iteration.

Output:

```
AGREE at embedding size 32, run Iteration:30, NDCG and HR at 5
...
User Iteration 10 [449.8 s]: HR = 0.6216, NDCG = 0.4133, [1.0 s]
Group Iteration 10 [471.9 s]: HR = 0.5910, NDCG = 0.4005, [23.0 s]

```


## Parameter Tuning

we put all the papameters in the config.py

## Dataset

We provide one processed dataset: CAMRa2011. 

Because we have another paper use the MaFengWo dataset are under reviewing, so we can't release MaFengWo dataset now.

group(user) train.rating:

* Train file.
* Each Line is a training instance: groupID(userID)\t itemID\t rating\t timestamp (if have)

test.rating:

* group(user) Test file (positive instances).
* Each Line is a testing instance: groupID(userID)\t itemID\t rating\t timestamp (if have)

test.negative

* group(user) Test file (negative instances).
* Each line corresponds to the line of test.rating, containing 100 negative samples.
* Each line is in the format: (groupID(userID),itemID)\t negativeItemID1\t negativeItemID2 ...
