# 來源

[SlideShare](http://www.slideshare.net/olvemaudal/deep-c/)

各種更深入的問題

## 問題1

```c
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

```c
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

```c
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

## 問題3

```c
#include <stdio.h>

int main(){
    int a = 41;
    a = a++;
    printf("%d\n", a);
}
```

* `a`是未定義，因為違反了C和C++基本規則：在同一指令(`Sequence Point`)下更新同一個變數一次以上。

```c
#include <stdio.h>

int b(){puts("3"); return 3;}
int c(){puts("4"); return 4;}

int main(){
    int a = b() + c();
    printf("%d\n", a);
}
```

* 可能會是`3 4 7`或者`4 3 7`，因為大部份的運算子沒有特別聲明(`unspecified`)計算順序
* 順序有可能會因為不同平台，不同優化而有所不同。

## 問題4

```c
#include <stdio.h>
struct X{int a; char b; int c;};

int main(){
    printf("%d\n", sizeof(int));
    printf("%d\n", sizeof(char));
    printf("%d\n", sizeof(struct X));
}
```

* 首先是`sizeof`的回傳型態是`size_t`，是`unsigned`型態，在32bit機器和64bit機器上通常分別是`unsigned int`和`unsigned long`
* 在C99底下，有`%zu`對應。
* 首先`sizeof(char)`確認是`1`。
* 在32bit模式底下，會是`4 1 12`。假如想獲得`4 1 9`的話，要加`-fpack-struct`來避免對齊。
* 對齊的原因是因為假如不對齊，執行期間會耗掉很多時間。
* *耗時原因待理解* **(TODO)**
