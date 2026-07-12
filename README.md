# quant_strate
sandbox on crypto trading
```
大类	        核心逻辑	                  典型策略
套利	        利用短暂价格偏差	          统计套利、配对交易、ETF套利、指数套利、跨市场套利
趋势	        顺应价格惯性	              CTA、趋势跟踪、动量
均值回归	    偏离最终会回归	              日内反转、价差回归、部分统计套利
风险溢价	    承担某种风险获取长期收益	      因子投资、波动率策略、信用策略等
```

1. 统计套利（Statistical Arbitrage）

2. 配对交易（Pairs Trading）

3. 做市（Market Making）

4. 趋势跟踪（Trend Following / CTA）

5. 动量策略（Momentum）

6. 均值回归（Mean Reversion）

7. 指数套利（Index Arbitrage）

8. ETF套利

9. 跨市场套利

10. 波动率套利（Volatility Arbitrage）

11. 事件驱动（Event Driven）

12. 因子投资（Factor Investing）

13. 机器学习策略

从机器学习的角度


```
均线斜率
ATR
ADX
RSI
MACD
成交量变化
波动率
收益率
Hurst指数
布林带宽度
```
再由模型（如XGBoost、LightGBM、LSTM等）学习哪些特征组合对应较高的未来上涨或下跌概率，而不是人工规定“这就是趋势”。

14. 另类数据（Alternative Data）

指标：离散导数
