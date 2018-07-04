# Google Play联想词
## 联想词基本情况
### 1.1 联想词是什么
即在GP搜索时产生的联想词
![image](https://github.com/motodriver/Google_play_search_keyword/blob/master/example_1.jpg)

### 1.2 联想词是怎么抓取的
1. 输入A词，抓取包含A的5个联想词A1~5
2. 依次输入A1~A5，抓取对应的25个词
3. 按着这种方法多次迭代，即可抓取全部联想词
#### 1.2.1 抓取细节
##### 1.2.1.1 url构成
完整url示例↓
https://market.android.com/suggest/SuggRequest?json=1&c=3&query=#keyword#&hl=#language#&gl=#country#&callback=#callback#
组成部分：
1.前缀
https://market.android.com/suggest/SuggRequest?json=1&c=3
2.请求的根词（#号中间放根词）
&query=#keyword#
3.语言
&hl=#language#
4.国家
&gl=#country#
5.回执
随机或为空即可获得有效url，但是callback字段消失则是无效url
&callback=#callback#

### 1.3 联想词有多少
| 根词 | 联想词数量 |
| ------------- | ------------- |
| Camera | 26107 |
| Launcher | 20136 |
| Weather | 10517 |
| Live wallpaper | 7997 |
| Keyboard | 4537 |

### 1.4 联想词是怎么来的
初步分析，联想词是由用户搜索产生、开发者上传的信息产生的，原因有如下几点
1. 在联想词中会出现大量weether\colock这种明显是输入错误的词 ———— 用户搜索产生
2. 有Xperia™这种词出现 ———— 开发者上传产生

### 1.5 联想词有什么用
#### 1.选题
例：将Launcher下的20136个联想词做词频分析







