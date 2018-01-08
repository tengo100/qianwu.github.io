---
title: frames
date: 2018-01-08 16:00:31
tags:
---
### 框架之间的通信

1.top、parent、window、self 之间的关系

---
top表示最外层框架（...window对象）
parent表示当前框架的父框架（...window对象）
window表示当前框架（...window对象）
self===window

2.window.frames

---
框架集合对象   
可以通过框架的name与索引访问到相应的框架window对象   
例如：   
**window.frames[0] ,    
window.frames['mainFrame']**

3.contentWindow,contentDocument   

---

所有浏览器都有contentWindow，非ie有contentDocument   
代表选定框架的window对象 或文档对象document

例如：   
```javascript
document.getElementById('mainFrame').contentWindow//id为mainFrame框架的window对象 
document.getElelmentById('mainFrame').contentDocument//idweimainFrame框架的document对象
```
4.子框架操作父级框架

---

==key： parent==

例如:获取父框架的DOM
```javascript
parent.document.getElementById('id')//父级
parent.parent.document.getElementById('id')//父级的父级
top.document.getElementById('id')//最外层父级
```

5.父框架操作子级框架

---

==key：获取子框架的window对象==

```javascript
document.getElementById('mainFrame').contentWindow.document.getElementById('childElement')//子框架元素
```