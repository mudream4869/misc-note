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

* 假如是C++ Compiler，那他會拒絕編譯，原因是`printf`沒有事先宣告。
* 假如是C Compiler，那他會把檔案編成Object檔。
然後在Link時，link到一個standard library，然後恰好找到`printf`的定義，
然後正常執行，不過會有`warning`就是了
    
