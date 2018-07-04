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
#### 1.2.1.1 联想词生成方式
在搜索框中输入根词后，会动态生成对应的url，以get的方式获取包含联想词的一条json

例：
[{"s":"launcher","t":"q"},{"s":"launcher google","t":"q"},{"s":"Launcher\u003c3","t":"q"},{"s":"launcher ios","t":"q"},{"s":"Launcher for Android ™","t":"q"}]

#### 1.2.1.2 url构成
完整url示例↓

https://market.android.com/suggest/SuggRequest?json=1&c=3&query=#根词#&hl=#语言#&gl=#国家#&callback=#回执k#

注：

随机或为空即可获得有效url，但是callback字段消失则是无效url

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
1. 在联想词中会出现大量weether\colock\wedget这种明显是输入错误的词 ———— 用户搜索产生
2. 有Xperia™这种词出现 ———— 开发者上传产生

### 1.5 联想词有什么意义
#### 1.5.1 判断需求大小
示例：
A词下有X个联想词，B词下有Y个联想词(X>Y)
那么A大概率是比B更强的需求，有更大的市场

#### 1.5.2 判断需求内容
分析联想词中出现较多的词，即可知道在该需求下细分需求的强弱

### 1.6 联想词有什么用
#### 1.6.1 选题
例：将Launcher下的20136个联想词做词频分析,得到高频词

| 联想词（部分） | 出现次数 |
| ------------- | ------------- |
| launcher | 9270 |
| theme | 8044 |
|go | 1102|
|new | 735|
|Keyboard | 678|
|samsung | 674|
|iphone | 664|
|galaxy | 371|
|2018 | 369|
|cm | 367|
|wallpaper | 366|

将这些词人工分类，即可得到该词下的需求情况
![image](https://github.com/motodriver/Google_play_search_keyword/blob/master/Launcher%20联想词分析-001.jpg)




