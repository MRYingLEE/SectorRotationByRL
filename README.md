# The original repo is to use reinforcement learning in portfolio management

# This repo uses in a special situation of portfolio management, sector allocation.

## Why sector allocation?
Different from a general portfolio management, sector allocation decides weights on different sectors.

Sector allocation is based on sector rotation (https://www.investopedia.com/articles/trading/05/020305.asp). sector rotation has academic evidence. Also, when we decide weights on sectors instead of names, we don't need to take company specific information into consideration. So that sector allocation is much more suitable for reinforcement learning.

## What's the data?

I use the popular Chinese sector indice of SWS http://www.swsindex.com/idx0130.aspx?columnid=8838. Actually there are 31 sectors. 



config.json- the configuration file for training or testing settings:

```javascript
{
"train_start_date": "2014-02-21", "train_end_date": "2018-04-27",
"test_start_date": "2018-05-02", "test_end_date": "2019-04-30", 

"codes": ["801010.XSHE",    "801020.XSHE",    "801030.XSHE",    "801040.XSHE",    "801050.XSHE",    "801080.XSHE",    "801110.XSHE",    "801120.XSHE",    "801130.XSHE",    "801140.XSHE",    "801150.XSHE",    "801160.XSHE",    "801170.XSHE",    "801180.XSHE",    "801200.XSHE",    "801210.XSHE",    "801230.XSHE",    "801710.XSHE",    "801720.XSHE",    "801730.XSHE",    "801740.XSHE",    "801750.XSHE",    "801760.XSHE",    "801770.XSHE",    "801780.XSHE",    "801790.XSHE",    "801880.XSHE",    "801890.XSHE"]}
```

## What's the results?

![Sector Rotation](https://github.com/MRYingLEE/SectorRotationByRL/blob/master/report/sector%20rotation.png "Sector Rotation")

The results is not too bad. Actually, it is better than the one in the original repo.

But, it is not as good as tradtional technical analysis. Years ago I have used RRG in Bloomberg terminal (https://www.relativerotationgraphs.com/partners/bloomberg) to do backtesting. The results was much better.


# In future?

1. (STATE) Different sector data. This time, the sectors are too many to deal with. Next time maybe I should try a market index with a few sub-sector indice.

2. (STATE) Different time scale. This time, daily data was used. Pratically monthly data should be used. But if so, only hundreds of  train data is available.

3. (STATE) Indirect Data. Maybe we should use some technical indicators (such as RRG indicators) instead of price/return data.

4. (ACTION) Instead of weights, we may let the agent to choose 1 sector to overweight and 1 to underweight.

5. (REWARD) This time, an immediate return was used to as reward. Maybe we should try other ways, such as a reward to punish overtrading.

6. (ALGO) The algo should reflect the characterics of investment. Maybe we need investment specific algo.

If I have some progress, I will update here.
