# 实现多线程的方式
1. MyThread继承Thread，重写Run方法。new MyThread().start()，启动线程会自动执行run方法  
2. 新建一个类，继承Runnable接口，实现run方法。
   ```
   MyRunnable mr = new MyRunnable();
   Thread t = new Thread(mr);
   t.start()
   ```

# 线程生命周期
新建状态 调用 start 方法，到达就绪状态（有抢夺时间片权力）  
就绪状态 执行 run 方法，进入运行状态  
失去cpu时间片后，继续进入就绪状态  
运行状态遇到阻塞，例如用户输入或者sleep方法，进入阻塞状态  
run执行完毕，进入死亡状态  

# sleep方法
是一个静态方法，让当前线程进入休眠，放弃cpu时间片，进入休眠状态。  
中断睡眠，动态方法，t.interrupt()，会让sleep抛出异常  

# synchronized用法
1. 同步代码块
2. 在实例方法前用synchronized修饰（一个对象一把）
3. 在静态方法前用synchronized修饰（类锁，一个类只有一把）
