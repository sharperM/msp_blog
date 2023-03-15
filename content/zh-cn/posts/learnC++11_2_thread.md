---
title: "C++11 的线程  join()函数"
date: 2023-03-07T23:02:32+08:00
draft: false
---
```cpp {hl_lines=[2 "17-18"]}

// constructing threads
#include <iostream>       // std::cout
#include <atomic>         // std::atomic
#include <thread>         // std::thread
#include <vector>         // std::vector

std::atomic<int> global_counter (0);

void increase_global (int n) { for (int i=0; i<n; ++i) ++global_counter; }

void increase_reference (std::atomic<int>& variable, int n) { for (int i=0;   i<n; ++i) ++variable; }

struct C : std::atomic<int> {
  C() : std::atomic<int>(0) {}
  void increase_member (int n) { for (int i=0; i<n; ++i) fetch_add(1); }
};

int main ()
{
  std::vector<std::thread> threads;

  std::cout << "increase global counter with 10 threads...\n";
  for (int i=1; i<=10; ++i)
    threads.push_back(std::thread(increase_global,1000));

  std::cout << "increase counter (foo) with 10 threads using   reference...\n";
  std::atomic<int> foo(0);
  for (int i=1; i<=10; ++i)
  {
      threads.push_back(std::thread(increase_reference,std::ref(foo),1000));  
  }

  std::cout << "increase counter (bar) with 10 threads using member...\n";
  C bar;
  for (int i=1; i<=10; ++i)
  {
    //threads.push_back(std::thread(&C::increase_member,std::ref(bar) ,1000));  //原来语法有错误
	  threads.push_back(std::thread([&bar](){bar.increase_member(1000);}));
  }

  std::cout << "synchronizing all threads...\n";
  for (auto& th : threads) th.join();

  std::cout << "global_counter: " << global_counter << '\n';
  std::cout << "foo: " << foo << '\n';
  std::cout << "bar: " << bar << '\n';

  return 0;
}
```
运行输出

    increase global counter with 10 threads...
    increase counter (foo) with 10 threads using   reference...
    increase counter (bar) with 10 threads using member...
    synchronizing all threads...
    global_counter: 10000
    foo: 10000
    bar: 10000


原子值std::atomic

join

同步synchronizing

