## 设计模式



### 实现线程安全的单例模式

利用pthread_once

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

