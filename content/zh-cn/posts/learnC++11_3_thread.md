---
title: "C++11 的线程  join()函数"
date: 2023-03-07T23:02:32+08:00
draft: false
---


```cpp
// example for thread::operator=
#include <iostream>       // std::cout
#include <thread>         // std::thread, std::this_thread::sleep_for
#include <chrono>         // std::chrono::seconds

void pause_thread(int n) 
{
  std::this_thread::sleep_for (std::chrono::seconds(n));
  std::cout << "pause of " << n << " seconds ended\n";
}

int main() 
{
  std::thread threads[5];                         // default-constructed threads

  std::cout << "Spawning 5 threads...\n";
  for (int i=0; i<5; ++i)
    threads[i] = std::thread(pause_thread,i+1);   // move-assign threads

  std::cout << "Done spawning threads. Now waiting for them to join:\n";
  for (int i=0; i<5; ++i)
  {
    std::cout <<i<< " joined!\n";
    threads[i].join();
    std::cout <<i<< " joined!\n";
  }

  std::cout << "All threads joined!\n";

  return 0;
}


```

运行结果

    Spawning 5 threads...
    Done spawning threads. Now waiting for them to join:
    0 joined!
    pause of 1 seconds ended
    0 joined!
    1 joined!
    pause of 2 seconds ended
    1 joined!
    2 joined!
    pause of 3 seconds ended
    2 joined!
    3 joined!
    pause of 4 seconds ended
    3 joined!
    4 joined!
    pause of 5 seconds ended
    4 joined!
    All threads joined!

join是阻塞的