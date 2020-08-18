# 什么是python的鸭子类型：
- Ref: [python ducking](https://blog.csdn.net/qq_18824345/article/details/105786417)

1. “当你看到一只鸟走起来像鸭子，游泳起来鸭子，叫起来也像鸭子，那么这只鸟就被称为鸭子类型“
2. 鸭子类型是多态一种形式，这这种形式中，不管对象属于哪个类，也不管声明的具体接口是什么，只要对象实现了相应的方法，函数就可以在对象上执行操作。

```python3
def func(obj):
    obj.who()

if __name__ == "__main__":
    duck=Duck()
    dog=Dog()
    cat=Cat()
    func(duck)
    func(dog)
    func(cat)
    
"""output    
I am a duck
I am a dog
I am a cat
"""
```
定义一个函数func()，这个函数对参数有一个要求，
那就是参数必须有who()这个方法。不管你是什么对象，
是duck对象也好，是dog对象也罢，只管对象实现who()方法就可。
这就是鸭子类型，它根本不管你是什么对象，只要你有这个方法，有这个行为，
表现得像鸭子，走起来像鸭子，游泳起来鸭子，叫起来也像鸭子，
那么尽管你是一只会飞天的猪，也是称为鸭子类型。

# c++中的抽象基类




# c++