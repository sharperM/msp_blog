---
title: "C++11 的线程  join()函数"
date: 2023-03-07T23:02:32+08:00
draft: false
---
```cpp {hl_lines=[2 "17-18"]}
// thread example1.cpp
#include  <iostream>        // std::cout
#include  <thread>        // std::thread
void foo()  {
    std::cout << "foo is called" << std::endl;
}
void bar(int x) {
    std::cout << "bar is called" << std::endl;
}

int main()
{
    std::thread first (foo);    // spawn new thread that calls foo()
    std::thread second (bar,0);  // spawn new thread that calls bar(0)                                                 
    std::cout << "main, foo and bar now execute concurrently...\n";
    // synchronize threads:
    first.join();                // pauses until first finishes
    second.join();              // pauses until second finishes
    std::cout << "foo and bar completed.\n";
    return 0;
}
```
使用下面的命令编译

    g++ -std=c++11 example1.cpp -lpthread -o example1                                

运行输出

    foo is called
    bar is called
    main, foo and bar now execute concurrently...
    foo and bar completed.
或者

    main, foo and bar now execute concurrently...
    bar is called
    foo is called
    foo and bar completed.

只有 join之后的代码顺序是确保的

{{< youtube id="w7Ft2ymGmfc" autoplay="true" >}}

