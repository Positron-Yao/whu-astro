---
layout: mypost
title: 在Markdown中输入化学方程式
categories: [Markdown, Chemistry]
---

## 化学环境：\\ce

~~为什么渲染不了？？？？~~

在Markdown中的数学公式（`$...$`或`$$...$$`）中，使用`\ce{expressions}`可以渲染化学式，如：
$$
\ce{  
H2O, CO2, \Delta_fH_m^{\small{\ominus}} \\ 
2H2 +O2 \xlongequal{点燃}2H2O \\ 
N2 + 3H2 \underset{催化剂}{\xlongequal{高温高压}} 2NH3 \\ 
2NaCl_{(l)} \xlongequal{通电}2Na + Cl2 ^ \\ 
Ba^2+ + SO_4^2- = BaSO4 v
}
$$
上面的源码是：

```latex
$$
\ce{  
H2O, CO2, \Delta_fH_m^{\small{\ominus}} \\ 
2H2 +O2 \xlongequal{点燃}2H2O \\ 
N2 + 3H2 \underset{催化剂}{\xlongequal{高温高压}} 2NH3 \\ 
2NaCl_{(l)} \xlongequal{通电}2Na + Cl2 ^ \\ 
Ba^2+ + SO_4^2- = BaSO4 v
}
$$
```

