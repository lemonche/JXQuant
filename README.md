# JXQuant
该库主要分享“匠芯量化”公众号内的策略源码，更多策略细节请关注微信公众号：“匠芯量化”（微信搜索公众号“jxquant”）。

目录：

Init_StockALL_Sp.py  —— 【数据采集】利用tushare接口将日线行情存储到本地数据库。  
DC.py   ——  【数据预处理】将本地存储的日基础行情整合成一份训练集。  
SVM.py   ——  【SVM建模】对个股用SVM进行建模，训练和预测。  
Model_Evaluate.py   ——   【模型评估】通过回测+推进式建模的方式对模型进行评估，主要计算查准率Precision，查全率Recall，F1分值，并存入结果表。  
Portfolio.py   ——   【仓位管理】基于马科维茨投资组合理论，计算一段时间序列内投资组合的风险、仓位配比和夏普率，有市场方向和最佳收益方向两种结果。  
Deal.py.py   ——   【模拟交易】封装类，用于模拟交易过程中获取最新的资产账户相关数据。  
Operator.py   ——   【模拟交易】封装函数，用于模拟交易过程中执行买和卖操作。  
Cap_Update_daily.py   ——   【模拟交易】封装函数，用于在回测过程中，每日更新资产表中相关数据。  
Filter.py   ——   【策略回测】封装函数，用于在回测过程中，处理一些简单的逻辑（更新持仓天数，买卖顺序等）。  
main.py   ——   【策略回测】策略的框架，回测的主函数。  

stock_my_capital.sql   ——   【策略回测】回测主函数里用到的数据库表，可直接导入。资产账单表，表结构在文章内有介绍，该表内含一条初始数据，用于定义初始资金，可根据回测场景自行修改。  
stock_stock_index.sql   ——   【策略回测】回测主函数里用到的数据库表，可直接导入。大盘行情表，内含部分大盘行情。  
stock_model_ev_mid.sql   ——   【模型评估】模型评估过程中用到的中间表，用于暂存回测时间序列内的部分数据，并用于最终计算F1分值。  
stock_model_ev_resu.sql   ——   【模型评估】模型评估的结果表，用于存储股票在某个时间点上的F1分值。  
stock_my_stock_pool.sql   ——   【策略回测】当前股票资产详情表，主要字段为:持仓股票代码，成交均价，持仓量，持仓天数。  
stock_stock_all.sql   ——   【策略回测】股票每日行情数据表，包含所有股票的日线行情。  
stock_stock_info.sql   ——   【策略回测】<stock_all>表的瘦身版，表结构相同，但删除了冗余数据，用于提高回测运行速度。  
