# **简单理解Smali语法**
## Smali在哪里能看到?
Smali是在安卓逆向过程中常见的语言。使用AndroidKiller等软件分析apk文件时，dex文件被反编译为*.smali文件，各个.smali文件中保存着安卓应用的的程序逻辑。Smali语言可以和java相互转化。       
## Smali基本语法
### 单行注释
`#blablabla`   
例：`#这是Smali语言的一句单行注释`
### 类声明
`.class <访问控制符> L类路径`  
例：`.class public Lcom/test/Test`   
我们可以看到，类的目录(com.test.Test)前有一个`'L'`  
### 方法声明   
#### 一个无参方法
```
.method <访问控制符> 方法名(<参数1>,<参数2>,...)返回值类型
    [方法体]
.end method
```
例：   
```
.method public methodnoparam()V     
    [...]
.end method
```
#### 一个带参方法  
例：
```
.method public methodhasparam(Lcom/lang/String)V
    [...]
.end method
```
可以看出，如果参数为引用数据类型，同样要写其绝对路径，这里的参数`String`就要写成`"Lcom/lang/String"`
