### 函数的缺省参数

C++中，定义函数的时候可以让**最右边的连续若干个参数**有**缺省值**，那么调用函数的时候，若相应位置不写参数，参数就是**缺省值**。

```
void func(int x1,int x2=2,int x3=3){ }

func(10);    //等效于func(10,2,3)
func(10,8);    //等效于func(10,8,3)，第二个参数代替了缺省参数2.
func(10, ,8);    // 错误，只能最右边的连续若干个参数缺省
```

意义：提高程序的可扩充性。即如果某个写好的函数要添加新的参数，而原先那些调用该函数的语句，未必需要使用新增的参数。那么为了避免对原先那些函数调用语句的修改，就可以使用缺省参数。

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/2db913e6a4f245a28360e7ef8b84945f/7232357c324945f8b872a2d4d0d18a26/](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/2db913e6a4f245a28360e7ef8b84945f/7232357c324945f8b872a2d4d0d18a26/)

2017.06.12
