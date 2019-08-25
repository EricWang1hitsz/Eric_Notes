## 1.`undefined reference error`
**问题描述**：模板类的声明与实现分离实现，声明位于头文件中，实现位于源文件中，在类实例化时会出现`undefined reference to matrix<int>::matrix(int,int) `链接器报错，提示找不到模板；类的实现。
**解决方案**:在模板类实例化的文件中，将模板类实现.cpp文件include进来即可`#included "matrix_de.cpp"`

**模板类的声明与实现分离实现，连接器会报错；普通类不会报错**

https://blog.csdn.net/weixin_40539125/article/details/83375452

## 2. 读取文件绝对路径
`pcl::io::loadPCDFile("/home/hit/room_scan1.pcd",cloud)`

## 3. 
