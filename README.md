量化策略是否真的能赚钱 的完整评估框架

数据 → 回测 → 统计 → 稳健性 → 样本外 → 真实交易 六层验证

1. 确认回测本身没有造假
    避免
      Look-ahead Bias
      Survivorship Bias
      Corporate Actions
      Transaction Cost
2. 策略到底赚了什么
    记录收益：
      Total Return
      CAGR
      年度收益
      月度收益
      Benchmark Return
3. 看风险
    最大回撤 Max Drawdown
4. 收益 / 风险是否合理
    Sharpe Ratio：
      承担一单位波动，获得多少超额收益。
      有些策略收益分布极不对称，Sharpe 会掩盖尾部风险。
    Sortino Ratio：
      下行波动
    Calmar Ratio：
      最大回撤关系非常大
5. 交易统计
    看交易次数比看胜率更有意义
      Win Rate
      Profit Factor
      Expectancy
6. 样本外测试
    判断“是不是过拟合”的核心之一
7. 参数敏感性测试：比如 MA 布林带
8. 市场环境测试
9. 不同资产测试
10. Monte Carlo Test
      可以随机重新排列交易顺序，或者对交易结果进行统计模拟。
11. 最后才进入真实市场

```
项目	  要检查
数据	  是否有 survivorship bias
数据	  是否有 look-ahead bias
数据	  Corporate actions 是否正确
成交	  手续费
成交	  Spread
成交	  Slippage
成交	  Market impact
收益	  CAGR
收益	  年度收益
风险	  Max Drawdown
风险	  Drawdown Duration
风险	  Volatility
风险	  Tail Risk
风险收益  	Sharpe
风险收益  	Sortino
风险收益  	Calmar
交易	  Trade Count
交易	  Win Rate
交易	  Profit Factor
交易	  Expectancy
稳健性	  参数敏感性
稳健性	  不同市场环境
稳健性	  不同资产
稳健性	  Walk-forward
泛化能力	  Out-of-sample
随机性	  Monte Carlo
实盘	  Paper trading
实盘	  Live vs Backtest
```
```
                  量化策略
                     │
                     ▼
            数据和回测有没有偏差？
                 /       \
               有         没有
               │           │
             淘汰          ▼
                    扣除成本后赚钱吗？
                       /       \
                     否         是
                     │           │
                   淘汰          ▼
                         样本外赚钱吗？
                           /       \
                         否         是
                         │           │
                       淘汰          ▼
                       参数稳健吗？
                         /       \
                       否         是
                       │           │
                     警惕          ▼
                    不同市场环境稳定吗？
                         │
                         ▼
                    Monte Carlo
                         │
                         ▼
                    Paper Trading
                         │
                         ▼
                     小资金实盘

```



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

14. 另类数据（Alternative Data）

指标：离散导数


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
