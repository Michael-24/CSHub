## 设计模式



### 写单例模式

#### 饿汉模式

```C++
template <typename T> 
class Singleton {  
private:   
    static T* m_instance = new Singleton();  
	Singleton() {}
	~Singleton() {}
public:  
    Singleton(const Singleton&)=delete;  
    Singleton& operator=(const Singleton&)=delete;  
    T& Instance()   
    {  
        return *m_instance;  
    }  
}; 
```

#### 懒汉模式



#### 线程安全版本

可以利用pthread_once，保证对象仅仅初始化一次，如果这个版本的单例模式出错，说明pthread库的实现有问题。（如果ptherad没有问题，可以保证正确性）。

```C++
template<typename T>
class Singleton {
 public:
  static T *getInstance() {
    // 通过pthread_once机制保证只初始化一次
    pthread_once(&ponce_, &Singleton::init);
    return value_.get();
  }

 private:
  Singleton() = default;
  ~Singleton() = default;

  static void init() {
    value_ = std::make_unique<T>();
  }

  static pthread_once_t ponce_;
  static std::unique_ptr<T> value_;

};

template<typename T>
pthread_once_t Singleton<T>::ponce_ = PTHREAD_ONCE_INIT;

template<typename T>
std::unique_ptr<T> Singleton<T>::value_ = nullptr;
}
```

### MVC设计模式

MVC是三个单词的首字母缩写，它们是Model（模型）、View（视图）和Controller（控制）。

这个模式认为，程序不论简单或复杂，从结构上看，都可以分成三层。

* 最上面的一层，是直接面向最终用户的"视图层"（View）。它是提供给用户的操作界面，是程序的外壳。
* 最底下的一层，是核心的"数据层"（Model），也就是程序需要操作的数据或信息。
* 中间的一层，就是"控制层"（Controller），它负责根据用户从"视图层"输入的指令，选取"数据层"中的数据，然后对其进行相应的操作，产生最终结果。

这三层是紧密联系在一起的，但又是互相独立的，每一层内部的变化不影响其他层。每一层都对外提供接口（Interface），供上面一层调用。这样一来，软件就可以实现模块化，修改外观或者变更数据都不用修改其他层，大大方便了维护和升级。

