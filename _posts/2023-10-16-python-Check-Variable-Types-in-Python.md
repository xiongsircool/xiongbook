---
layout: post
title: Python查看变量数据类型
categories: python知识点
description: 今天遇到一个比较有意思的数据就是一个字典的键用的是tuple，这打破了我之前的认知，一个是回忆下自己的python变量数据类型查询方法,一个是发现tuple元组是否可以作为键，元组是可以作为字典的键的因为其是不可变的。
keywords: python
---

## Python查看变量数据类型

在Python中，你可以使用以下方法来查看变量的数据类型：

1. **使用 `type()` 函数：** `type()` 函数可用于查看变量的数据类型。例如：

   ```python
   x = 5
   print(type(x))  # 输出 <class 'int'>
   ```

   这将返回变量 `x` 的数据类型，例如整数（int）、字符串（str）、列表（list）等。

2. **使用 `isinstance()` 函数：** `isinstance()` 函数可用于检查一个变量是否属于指定的数据类型。例如：

   ```python
   x = "Hello"
   if isinstance(x, str):
       print("x 是字符串类型")
   ```

   这将检查变量 `x` 是否是字符串类型。

3. **使用 `__class__` 属性：** 可以直接访问对象的 `__class__` 属性来获取其类，从而查看数据类型。例如：

   ```python
   x = [1, 2, 3]
   print(x.__class__)  # 输出 <class 'list'>
   ```

4. **使用注释：** 在一些集成开发环境（IDE）中，当你将鼠标悬停在变量上时，IDE通常会显示变量的数据类型。

5. **使用 `print` 语句：** 在你想要查看变量类型的地方，将变量打印到控制台，然后观察输出。





### 补充

#### 在R中，你可以使用以下方法来查询变量的类型和属性：

1. **使用 `class()` 函数：** `class()` 函数用于查看一个对象的类（类型）。例如：

   ```R
   x <- 5
   class(x)  # 输出 [1] "numeric"
   ```

   这将返回变量 `x` 的类，例如 "numeric" 表示数值类型。

2. **使用 `typeof()` 函数：** `typeof()` 函数用于查看对象的基本数据类型。例如：

   ```R
   y <- "Hello"
   typeof(y)  # 输出 [1] "character"
   ```

   这将返回变量 `y` 的基本数据类型，例如 "character" 表示字符类型。

3. **使用 `str()` 函数：** `str()` 函数用于查看对象的结构，包括其类和属性。例如：

   ```R
   z <- c(1, 2, 3)
   str(z)
   ```

   这将显示变量 `z` 的结构，包括其类和元素。

4. **使用 `$` 运算符：** 如果你要查询数据框（data frame）中的列，可以使用 `$` 运算符来访问列，并查看其类型。例如：

   ```R
   df <- data.frame(Name = c("Alice", "Bob", "Charlie"), Age = c(25, 30, 22))
   class(df$Age)  # 输出 [1] "numeric"
   ```

   这将返回数据框 `df` 中列 `Age` 的类型。

除了上述基本方法外，R中还有一些其他用于查询变量和数据框的信息的方法，包括使用`dplyr`包等。

使用`dplyr`包的一些方法：

1. **使用`glimpse()`函数：** `glimpse()`函数在查看数据框的结构时非常有用，它会显示数据框的列名、数据类型和前几行数据。例如：

   ```R
   library(dplyr)
   df <- data.frame(Name = c("Alice", "Bob", "Charlie"), Age = c(25, 30, 22))
   glimpse(df)
   ```

   这将显示数据框 `df` 的结构信息。

2. **使用`summarise()`函数：** `summarise()`函数用于生成数据框中列的汇总统计信息。你可以使用它来查看列的统计摘要。例如：

   ```R
   library(dplyr)
   df <- data.frame(Age = c(25, 30, 22, 35, 28))
   summary <- df %>% summarise(mean_age = mean(Age), max_age = max(Age))
   print(summary)
   ```

   这将生成一个包含平均年龄和最大年龄的汇总统计信息。

3. **使用`class()`函数（dplyr中的变体）：** 你还可以使用`dplyr`包中的`class()`函数来查看数据框的列的类。例如：

   ```R
   library(dplyr)
   df <- data.frame(Name = c("Alice", "Bob", "Charlie"), Age = c(25, 30, 22))
   df %>%
     select(Age) %>%
     summarise(age_class = class(Age))
   ```

   这将返回数据框 `df` 中列 `Age` 的类。
