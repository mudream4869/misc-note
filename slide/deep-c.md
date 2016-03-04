# 來源

[SlideShare](http://www.slideshare.net/olvemaudal/deep-c/)

各種更深入的問題

## 問題1

```
int main(){
    int a = 42;
    printf("%d\n", a);
}
```

### Compiler

* 假如是C++ Compiler，那他會拒絕編譯，原因是`printf`沒有事先宣告。
* 假如是C Compiler，那他會把檔案編成Object檔。
然後在Link時，link到一個standard library，然後恰好找到`printf`的定義，
然後正常執行，不過會有`warning`就是了

### Return Value

* 假如在`C99`或`C++98`，那會定義在程式是否執行成功
* `ANSI C`則會回傳一個垃圾，硬要說，應該愧是`3`，原因是`printf()`會回傳`3`，印出的字串長度。

## 問題2

```
#include <stdio.h>

void foo(void){
    static int a;
    ++a;
    printf("%d\n", a);
}

int main(void){
    foo();
    foo();
    foo();
}
```

* 會印出 `1` `2` `3`，因為Standard有說`static`會預設`0`

```
#include <stdio.h>

void foo(void){
    int a;
    ++a;
    printf("%d\n", a);
}

int main(void){
    foo();
    foo();
    foo();
}
```

* `a`的數值沒有定義，不過在執行階段，`a`的位址通常會位於`stack`上的同一個地方，所以可能會是三個連續數值。
* 假如在`debug mode`，`runtime`可能會`memset`，然後就印出`1` `2` `3`

### 為什麼`static var`和`auto var`一個會初始化，一個不會。

* 假如`auto var`要初始化，那就會在call function時多花一些時間，然而C想要省時間，所以不會初始化`auto var`。全域變數會是`0`因為只需要做一次。
