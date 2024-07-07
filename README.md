# Pipelines-as-Code - Demo Repository

a badly written hello world in Golang used for demo using [Pipelines-as-Code](https://pipelinesascode.com)


遇到的问题：

1. build vars 变量不能使用
2. pvc 不能自动清理？
3. 如果用到了本地 task，每次提交执行流水线的时候 pac controller 都会导入一次 task，如果不同 pr 对 task 做了修改，会导致 task 的行为可能不一致
4. 
