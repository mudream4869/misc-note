# Por fin entiendo qué son las mónadas

[Slide](https://github.com/joaquintides/usingstdcpp2014/blob/master/Por%20fin%20entiendo%20qué%20son%20las%20mónadas/Por%20fin%20entiendo%20qué%20son%20las%20mónadas.pdf)

翻譯是：我終於明白什麼是單子了...

## None or Value

總之，一開始先定義這種東西

```c++
template<tyename T>
struct optional{
    optional(const& T _value);
    optional(none_t);
};
```

然後就可以這樣弄出一些**安全**的函數，像是開根號或者倒數：

```c++
optional<double> sqr(double x){
    if(x < 0) return none;
    return sqrt(x);
}
optional<double> inv(double x){
    if(x == 0) return none;
    return 1.0/x;
}
```

## >>=

可當我們遇到這樣的運算：

![](https://latex.codecogs.com/gif.latex?%5Cfrac%7B1%7D%7B%5Csqrt%7Bx%7D%7D)

```c++
optional<double> f(double x){
    return inv(sqr(x));
}
```

便會遇到困難，因為無法把`optional<double>`轉乘`double`
，並且sqr所出現的none需要傳遞。所以要改寫成

```c++
optional<double> f(double x){
    auto y = sqr(x);
    return y ? inv(y.get()) : none;
}
```

我們可以追加一個operator `>>=`：

```c++
template<typename T, typename F>
auto operator >>= (const optional<T>& x, F&& f){
    return x ? f(x.get()) : none;
}
```

然後

```c++
optional<double> f(double x){
    return x >>= sqr >>= inv;
}
```
