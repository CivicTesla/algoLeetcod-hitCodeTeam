[[_TOC_]]

# 介绍
一个用来练习打代码的repository
```
hi
HitCode 即打码
```

## tip：
### 第三方包的简单使用
仓库根目录的include/文件夹用于存放一些自定义包，第三方库等，可供便捷地调用;
引用即可使用
1. 仿gtest框架，自定义的程序运行时间测试。```#include "include/test/timeTest.h"```
2. print.h，简化输出，引入后，使用print(变量)即可输出，支持int，int []，vector数组。
```c++
 #include "../../include/breaknine/print.h" 
//  输出整数
 print(i)
//  输出数组，要输入数组的个数
 print(list,sizeof(list)/sizeof(list[1]));
//  输出vector数组
 print(vec)
//  c++ printf
int a = 1;
printf("%d\n",i);
 ```
### gtest
- google测试框架，位于win-gtest文件夹

### 其他文件说明
- package.json用于记录所用的包，框架；
- .gitkeep 无用文件，只为向git证明该文件夹存在

***
## 算法笔记

创建n维数组：
```c++
//* 构造一维数组vec
int ele[] = {2,7,11,15};
vector<int> vec0(ele, ele+sizeof(ele)/sizeof(int));//sizeof(ele)用于统计int ele[]所有元素的字节数，sizeof(int)表示单个int类型所占字节数，两者相除即ele[]中元素的个数
// 简约写法
vector<int> vec1{2,7,11,15};

//* 构造二维数组
int element0[] = {1,0,1,1,0,1,0,1};
vector<int> vec0(element0, element0+sizeof(element0)/sizeof(int));
int element1[] = {1,0,1,1,0,1,1,1};
vector<int> vec1(element1, element1+sizeof(element1)/sizeof(int));
int element2[] = {0,0,0,0,0,0,0,1};
vector<int> vec2(element2, element2+sizeof(element2)/sizeof(int));

vector<int> ele[] = {vec0,vec1,vec2};
vector<vector<int>> vec(ele,ele+sizeof(ele)/sizeof(vector<int>));
// 简约写法
vector<vector<int>> vec{{1,0,1,1,0,1,0,1},{1,0,1,1,0,1,1,1},{0,0,0,0,0,0,0,1}};
```
输出数组vec：
C++的cout输出不了vector<>类型数组，因此用下面的方法输出
```c++
// 输出数组vec
// * ----------------------显示数组
    vector<int> vec =  vec0;
    vector<int>::iterator ite = vec.begin();
	for (; ite != vec.end(); ite++){
		cout << *ite;
		cout << ",";
	}
    cout << endl;// * ----------------------显示数组结束
```
break的用法：
當滿足中斷條件時，就離開迴圈( while 或 for )
```c++
while / for( ... )
{
    ...
    if( 中斷條件 )
    {
        break;
    }
    ...
}
```