``` 
1 : 获取股票行情
可以获取多只股票的行情信息

需要传入一个列表，每个列表由一个市场代码， 一个股票代码构成的元祖构成[ (市场代码1， 股票代码1)，(市场代码2， 股票代码2) ... (市场代码n， 股票代码n) ]

如：python
api.get_security_quotes([(0, '000001'), (1, '600300')])

2 : 获取k线
category-> K线种类0 5分钟K线 1 15分钟K线 2 30分钟K线 3 1小时K线 4 日K线5 周K线6 月K线7 1分钟8 1分钟K线 9 日K线10 季K线11 年K线
market -> 市场代码 0:深圳，1:上海
stockcode -> 证券代码;
start -> 指定的范围开始位置;
count -> 用户要请求的 K 线数目，最大值为 800
如：

python
api.get_security_bars(9,0, '000001', 4, 3)

3 : 获取市场股票数量
0 - 深圳， 1 - 上海pythonapi.get_security_count(0)

4 : 获取股票列表
参数：市场代码, 起始位置， 数量 如： 0,0 或 1,100

python
api.get_security_list(1, 0)

5 : 获取指数k线
category-> K线种类0 5分钟K线 1 15分钟K线 2 30分钟K线 3 1小时K线 4 日K线5 周K线6 月K线7 1分钟8 1分钟K线 9 日K线10 季K线11 年K线
market -> 市场代码 0:深圳，1:上海
stockcode -> 证券代码;
start -> 指定的范围开始位置;
count -> 用户要请求的 K 线数目，最大值为 800
如：

python
api.get_index_bars(9,1, '000001', 1, 2)

6 : 查询分时行情
参数：市场代码， 股票代码， 如： 0,000001 或 1,600300
python
api.get_minute_time_data(1, '600300')

7 : 查询历史分时行情
参数：市场代码， 股票代码，时间 如： 0,000001,20161209 或 1,600300,20161209
python
api.get_history_minute_time_data(TDXParams.MARKET_SH, '600300', 20161209)

注意，在引入 TDXParams 之后， （from pytdx.params import TDXParams）我们可以使用 TDXParams.MARKETSH , TDXParams.MARKETSZ 常量来代替 1 和 0 作为参数

8 : 查询分笔成交
参数：市场代码， 股票代码，起始位置， 数量 如： 0,000001,0,10
python
api.get_transaction_data(TDXParams.MARKET_SZ, '000001', 0, 30)

9 : 查询历史分笔成交
参数：市场代码， 股票代码，起始位置，日期 数量 如： 0,000001,0,10,20170209

python
api.get_history_transaction_data(TDXParams.MARKET_SZ, '000001', 0, 10, 20170209)

10 : 查询公司信息目录
参数：市场代码， 股票代码， 如： 0,000001 或 1,600300
python
api.get_company_info_category(TDXParams.MARKET_SZ, '000001')

11 : 读取公司信息详情
参数：市场代码， 股票代码, 文件名, 起始位置， 数量, 如：0,000001,000001.txt,2054363,9221
python
api.get_company_info_content(0, '000001', '000001.txt', 0, 100)

注意这里的 起始位置， 数量 参考上面接口的返回结果。

12 : 读取除权除息信息
参数：市场代码， 股票代码， 如： 0,000001 或 1,600300
python
api.get_xdxr_info(1, '600300')

13 : 读取财务信息
参数：市场代码， 股票代码， 如： 0,000001 或 1,600300
python
api.get_finance_info(0, '000001')



```
