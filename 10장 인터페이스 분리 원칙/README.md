## 10장 인터페이스 분리 원칙
- 소프트웨어 설계자는 사용하지 않은 것에 의존하지 않아야 된다.


### ISP를 위반하는 코드 
> Ops의 methodB가 변경되어도 User1를 다시 컴파일해야 된다.
```java
class Ops {
    void methodA();
    void methodB();
    void methodC();
}
```

```java
class User1 {
    private Ops ops;
    void test(){
        ops.methodA;
    }
}
```

### ISP를 위반하지 않도록 수정
```java
interface U1Ops {
    void methodA();
}
```

```java
class Ops implements U1Ops {
    void methodA();
    // 이하 생략
}
```

```java
class User1 {
    private U1Ops ops;
    void test(){
        ops.methodA;
    }
}
```