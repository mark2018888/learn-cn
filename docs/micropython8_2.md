
- 一个程序的所有的变量并不是在哪个位置都可以访问的。访问权限决定于这个变量是在哪里赋值的。

- 变量的作用域决定了在哪一部分程序你可以访问哪个特定的变量名称。在此之前我们所写的程序都只有一个作用域，当学习了如何自定义函数后，就要考虑变量的作用范围了。两种最基本的变量作用域如下：


### 全局变量 ###

- 定义在函数外的变量拥有全局变量域，可以在整个程序范围内访问。两个自定义函数可以修改同一个全局变量以完成信息传递。

### 局部变量 ###

- 定义在函数内部的变量拥有局部作用域，局部变量只能在当前函数体内被访问，是当前函数独有的变量，允许在不同的函数中定义相同变量名的变量，互不相干，也不会发生混淆。局部变量如果和全局变量同名，则局部变量会覆盖全局变量。

```python
 
total = 0								# 这是一个全局变量

def sum( arg1, arg2 ):
    #返回2个参数的和."
    total = arg1 + arg2					# total在这里是局部变量.
    print ("函数内是局部变量 : ", total)
    return total
 
#调用sum函数
sum( 10, 20 )
print ("函数外是全局变量 : ", total)


#输出结果如下：
#函数内是局部变量 :  30
#函数外是全局变量 :  0


```