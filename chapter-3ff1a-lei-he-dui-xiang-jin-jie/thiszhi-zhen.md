# this指针

C++程序到C程序的翻译

```java
class CCar{
    public:
        int price;
        void SetPrice(int p);
};
void CCar::SetPrice(int p)
{    price=p;}
int
```

作用：指向成员函数所作用的**对象**

