# 字符串条件判断

- 错误的情况

`[ -n $str2 ]`返回ture，因为会把`-n $str2`当成一个字符串。所以不管`$str2`是否为空，条件都是成立的。 

- 正确的使用

`[ -n "$str2" ]`返回false，`[ -n "$str1"]`会返回true。但是很多书在介绍的时候都是按照`[ -n $str2 ]`这么介绍的。  
ubuntu实测`[ -n $str ]`不管`str`是否有值，永远返回ture。所以一定记住要使用`"$var"` 

```bash
    str1=hhp
    str2=
    if [ -n $str2 ]; then
        echo 'str2='$str2 #输出str2=
    fi

    if [ -n "$str1" ]; then
        echo 'str1='$str1 #输出str1=hhp
    fi
```



