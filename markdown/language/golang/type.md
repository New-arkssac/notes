# type类型

在go语言中，类型不相同的无法进行运算

```
var pi float32 = 3.1415926
var b int = 10
c := b + pi ❯❯❯ invalid operation: mismatched types int and float32
```

如果以上变量相加就会报错`invalid operation: mismatched types int and float32`

如果要整型和浮点型相加的话，就要必须进行类型转换

```go
var pi float32 = 3.1415926

var b int = 10

c 	:= float32(b) + pi

a 	:= b + int(pi)
```

这样写就没问题