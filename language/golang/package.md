# golang package

golang的所有文件都需要指定其所在的包(package)，包有两种类型，一种是main包，使用`package main`在代码的最前面声明。另外一种就是非main包，使用`package + 包名`。main包的可以有唯一的一个main函数，这个函数也是程序的入口。也只有main包可以编译可执行的文件