---
title: C++矩阵库
date: 2020-05-20 14:03:12
excerpt: 列出几种常见的C++矩阵库
tags: C++
categories: Program
---

## 前言
C++以其及其优异的计算速度在科学计算、工业工程等领域得到广泛的应用，在数值计算方面，调用矩阵库能简化编程过程，提高计算速度，下面介绍几种常用的矩阵库及其用法，此外，我也写了一个矩阵库在自己科研分析中[C++矩阵库（2）](https://ting2938.github.io/2020/05/22/C-%E7%9F%A9%E9%98%B5%E5%BA%93%EF%BC%882%EF%BC%89/)。

### Eigen
[Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page)是采用C++模板技术编写的纯头文件库，用法如下：

```c++
#include <iostream>
#include <Eigen/Dense>
int main()
{
    Eigen::MatrixXd mat(3, 4);
    for (int i = 0; i != 3; ++i)
    {
        for (int j = 0; j != 4; ++j)
        {
            mat(i, j) = 3*i+5*j;
        }
    }
    std::cout << mat << std::endl;
}
```

### Armadillo
[Armadillo](http://arma.sourceforge.net/)的语法与Matlab语法很相识，从Matlab迁移到Armadillo很方便，用法如下：

```c++
#include <iostream>
#include <Armadillo>
int main()
{
    arma::mat A(3, 4);
    for (int i = 0; i != 3; ++i)
    {
        for (int j = 0; j != 4; ++j)
        {
            A(i, j) = 3*i+5*j;
        }
    }
    A.print("A:");
}
```

### Boost
[Boost](https://www.boost.org/)在C++中地位非常高，被称为C++的准标准库，其中的ublas模块包含矩阵类，用法如下：

```c++
#include <boost/numeric/ublas/matrix.hpp>
#include <boost/numeric/ublas/io.hpp>
#include <iostream>
namespace ublas = boost::numeric::ublas;
int main()
{
    ublas::matrix<double> A(3, 3);
    for (unsigned i = 0; i < A.size1(); ++i)
        for (unsigned j = 0; j < A.size2(); ++j)
            A(i, j) = 3*i + j;
	std::cout << A << std::endl;
    return 0;
}

```