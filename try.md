# 寒假出遊攻略 
  1. Google 一下，決定寒假玩臺南
  2. 找到台南市景點資料表
  3. 開始行前準備啦~
  
![image](https://github.com/yiping0422/-/blob/master/%E7%A7%80.gif?raw=true)

------

## 目標！臺南！

怎麼決定台南的不是重點，
#### 重 . 點 . 是 . 

台南辣麼大， 要去哪兒呢~

接著把資料載下來  ヾ ( * ´  ∀  ˋ  * ) ﾉ

臺南景點.csv'

#### 燈燈燈燈！

![image](https://github.com/yiping0422/-/blob/master/1515323051798.jpg?raw=true)

####                  好多！

![image](https://github.com/yiping0422/-/blob/master/%E5%92%A9.gif?raw=true)

記事本  - - - 又多又花

Excel  - - - 嗯 . . . 顯然一堆不需要的，整欄選取刪一刪  >>>

![image](https://github.com/yiping0422/-/blob/master/1515323158800.jpg?raw=true)

![image](https://github.com/yiping0422/-/blob/master/%E5%92%A9.gif?raw=true)

. . . . . .

台南依山傍海，這三百多個地點還是篩選一下吧  >>>

![image](https://github.com/yiping0422/-/blob/master/try.jpg?raw=true)

![image](https://github.com/yiping0422/-/blob/master/%E5%92%A9.gif?raw=true)

這 . . . 還真不是用 Excel 的時機啊  ~ ( 茶

------

## 目標！ R 的彼方！

認真上生態資訊的好孩子都知道，老師極推崇 "R" 的應用。

那我們就來 "R" 一下吧 ~

#### 1. 把資料扔進 R

這裡是先把檔案下載到電腦裡，再用 ```fread```讀取並建立名為```jin```的表格

( 檔案位置格式因電腦而異，此為 Windows 系統 )

```
library(data.table)
jin <- fread('C:\\Users\\user\\Desktop\\臺南景點.csv')
```

讀出來的表格長這樣

![image](https://github.com/yiping0422/-/blob/master/R3.jpg?raw=true)

#### 2. 開始刪

```
jin <- jin[,-2]
jin <- jin[,-3]
jin <- jin[,-4]
jin <- jin[,-4]
    .
    .
    .
```

初步把不需要的簡單刪一下後 . . . . . .

![image](https://github.com/yiping0422/-/blob/master/R4.jpg?raw=true)

一長串的，把需要的留下，不需要的取代掉、刪掉 . . . . . . 

```
jin[, opentime2 := substr(jin$開放時間,start=1,stop=3)]
jin <- jin[,-3]

jin[, local5 := substr(jin$地址,start=4,stop=5)]
jin <- jin[,-3]


gsub('沒有開|請洽建|請洽勝|請洽詢','電洽',jin$opentime2)
jin[, opentime3 := gsub('沒有開|請洽建|請洽勝|請洽詢','電洽',jin$opentime2)]

gsub('尚未開','未開',jin$opentime3)
jin[, opentime4 := gsub('尚未開','未開',jin$opentime3)]


jin <- jin[,-3]
jin <- jin[,-4]
jin <- jin[-14,]
    .
    .
    .
```

出來長這樣

![image](https://github.com/yiping0422/-/blob/master/R1.jpg?raw=true)

是不是清爽多了 ( ？

------

## 目標！終端攻略！

最終階段，抽出地點並建立表格，再抽出地點 ![image](https://github.com/yiping0422/-/blob/master/%E7%BF%BC%E7%A9%BA%E5%A4%A7.gif?raw=true)

```
city<- table(jin$local5)

city1<-data.table(city)
```

就這樣，整理出我們要的數據了。

![image](https://github.com/yiping0422/-/blob/master/R2.jpg?raw=true)

最後把數字披上地圖  >>>

. . . . . .

![image](https://github.com/yiping0422/-/blob/master/%E7%A7%80.gif?raw=true) 哇~~

![image](https://github.com/yiping0422/-/blob/master/26694057_1771546239542927_301456047_n.jpg?raw=true)




     *
     * 
     *
     *
     *
     *


### 然後報告就做完了


-

-

-
   
   
### 現在報完了

### 所以寒假開始


*

*

*

*

*

*


## 報告，是進入寒假前的終極大BOSS


