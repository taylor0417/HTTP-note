http
====

Cookie
------

-	http协议是一个无状态（没脑子）的协议，因为Apache不会记录曾经谁来访问过。举例：登陆后刷新需反复验证登陆信息。
-	Http的会话机制是用来解决这个问题的新技术，其主要构成是Cookie。
-	注：Cookie不是实现登录的唯一方案
-	Cookie的创建和记录都在客户端（浏览器）中完成。

### 如何创建和读取Cookie

-	通过document.cookie进行设置
-	Cookie的本质就是一个带有格式的字符串，格式：key=val;key1=val1;.....

```javascript
    //设置cookie(需多次创建)
    document.cookie = 'name=xiaoming';
    document.cookie = 'age=16';
    //读取cookie
    console.log(document.cookie);
```

-	读取cookie可以通过浏览器的Application中的Cookies中查看

### Cookie的一些特点

1.	Cookie是有"寿命"的
	-	默认关闭浏览器时清除
	-	在设置cookie的同时可以对其到期时间进行设置

```javascript
		document.cookie = 'name=xiaoming;expires='+ new Date('2018-06-10');
	```
2. Cookie是有访问权限的
  * 当设置了cookie只能当前路径或者子路径可以访问
  * 可以对默认访问的路径进行修改
  ```javascript
    document.cookie = 'name=xiaoming;path=/'
```

1.	Cookie有大小限制约为4kb

### Cookie的完整设置

```javascript
  document.cookie = 'age=16;path=/;expires'+ new Date('2018-12-01');
```
