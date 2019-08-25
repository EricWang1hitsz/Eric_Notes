# 1. 类 Clss
`volume=Box1.getvolume()`
//`Box1`是`Class Box`的一个对象，`getvolume`是`Classs Box`的成员函数
调用成员函数实在对象上使用点运算符（.),这样就能操作与对象相关的数据和函数。

#2.std:share_ptr
`#include<memory>`share_ptr定义在memory头文件中.

**Example:**
`std:share_ptr<anydrive_ethercat::AnydriveManagerEthercat> anydriveManager`

**anydriveManager指向AnydriveManagerEthercat类，因此anydriveManager可以调用类的函数.**
`anydriveManager.reset(new anydrive_ethercat::AnydriveManagerEthercat(standalone, installSignalHandler, timeStep));`
`p.reset(new int(2014))`**P指向一个新对象**

#3.Typedef/  Typedef typename

##3.1Typedef:
**简化类型的定义，别名**

`vector <list<int *>*>temp(10);`
可简化为：
`typedef list<int *> listnum;`
`typedef vector<listnum> *> vectornum;`
`vectornum temp(10);`

**声明结构体结构**
`typedef struct`
`{`
  `int month;`
  `int day;`
  `int year;`
  `}DATE;`
`DATE birthday;`//birthday是结构体变量.
**DATE是新类型名，不是结构体变量名**

##3.2 typedef typename
`template <class T>`
`void function()`
`{`
  `typedef typename T::A TA`//声明TA的类型是T：：A
  `TA a5`//声明a5的类型是TA
  `}`
**T只有末班实例化的时候才能知道其类型，所以编译器对T：：A不知所措，为了通知编译器T::A是一个合法的类型，使用typename语句可以避免编译器报错.**

#4. ROS::Time and Duration Class 依赖于roslib
**Time/Duration是为节点设置的模拟时钟.**

###4.1.Getting the Current timeStep
`ros::Time::now();`return time 0 until first message has been received.
`ros::Time begin = ros::Time::now();`

###4.2. Creating Time and Duration Instance.
`ros::Time a_little_after_the_beginning(0.001)`时间点；
`ros::Duration five_second(5.0)`时间段；
**a_little_after_the_beginning and five_second是类对象，括号内单位为秒**

###4.3. Converting Time and Duration Instance时间点和时间段之间的转化.
`double secs = ros::Time::now.toSec();`时间点转化为时间段，即多少秒.

###4.4 Sleeping and Rates
`ros::Duration(0.5).sleep();`//sleep for 0.5s.

#5. Thread
`boost::recursive_mutex`//用于保护共享数据免受从多个多线程同时访问.

###5.1 Lock__
这里的锁是动词而非名词，互斥对象的主要操作有两个加锁`lock`和释放锁`unlock`.
当一个线程对互斥对象进行`lock`操作并成功获得这个互斥对象的所有权，在此线程对此对象`unlock`前，其他线程对这个互斥对象的`lock`操作都会被阻塞.

#6. Github

`git config user.name user.email`

**1.创建本地仓库**：
`git init` 把当前目录设置为Git可管理的仓库；
`git add readme.txt` 告诉Git,把文件添加到本地仓库；
`git commot -m "wrote a readme file"` 告诉Git，把文件提交到本地仓库；
**可以`git add`多个文件，最后一起`git commit`到本地仓库。

**2.关联远程仓库**
`git remote add origin https://github.com/EricWang1hitsz/Eric_Note.git` 将本地仓库与远程仓库关联；
`git push -u origin master` 将本地仓库的所有内容推送到远程仓库，注意是git commit的文件！
<kdb>-u<kdb>将本地master分支与远程master分支关联起来，在以后的推送和拉取就可以简化命令。

**3.推送与拉取**

`git pull`拉取；
`git add`--`git commit`--`git push origin master`推送；
**在本地仓库修改需要推送到远程仓库时，也需要执行<kdb>git add<kdb>。**

**4.Sign in to Github for Atom**

Your Github token:

``71e7f5ff5e904f66b7722a7ea6882d660896c6be``

LINK: https://github.atom.io/auth/github_package/token
