# KNACK

1. `1000ms`大概能进行`200000000`即2*10^8^次计算

2. `256M`一般可是申请`10000000`即1e7个int

3. 大量输入输出使用`printf\scanf`能快很多

4. `Array`一般快于`vector`

5. 圆周率=acos(-1.0)
   自然对数=exp(1.0)

6. `a>>n` `a<<n`会快一些

7. 浮点数的比较

   ```c++
   #define eps 1e-6
   fabs(a-b)<eps
   ```

8. 字符串<->整形

   ```
   sscanf(s,"%d",&n);
   sprintf(s,"%d",n);
   ```

9. 1

#### Reference

[ACM的小技巧](https://blog.csdn.net/power721/article/details/4503056)
