# 寒假出遊攻略
  
  1. Google 一下，決定寒假玩臺南
  2. 找到台南市景點資料表
  3. 開始行前準備啦~

---
## 目標！臺南！

```
library(data.table)
jin <- fread('C:\\Users\\user\\Desktop\\臺南景點.csv')
```

```
jin <- jin[,-2]
jin <- jin[,-3]
jin <- jin[,-4]
jin <- jin[,-4]
    .
    .
    .
```


```
jin[, opentime2 := substr(jin$開放時間,start=1,stop=3)]
jin <- jin[,-3]

jin[, local5 := substr(jin$地址,start=4,stop=5)]
jin <- jin[,-3]
```

```
gsub('沒有開|請洽建|請洽勝|請洽詢','電洽',jin$opentime2)
jin[, opentime3 := gsub('沒有開|請洽建|請洽勝|請洽詢','電洽',jin$opentime2)]

gsub('尚未開','未開',jin$opentime3)
jin[, opentime4 := gsub('尚未開','未開',jin$opentime3)]
```

```
jin <- jin[,-3]
jin <- jin[,-4]
jin <- jin[-14,]
    .
    .
    .
```

```
city<- table(jin$local5)
View(city)
city1<-data.table(city)
```

![image](picture or gif url)
