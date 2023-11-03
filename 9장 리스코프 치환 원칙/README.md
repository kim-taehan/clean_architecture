## 9장 리스코프 치환 원칙
- 상호 대체 가능한 구성요소를 이용해 소프트웨어 시스템을 만들려면, 이들 구성요소는 반드시 서로 치환 가능해야 한다.

### 정사각형/직사각형 문제

```java
class Rectangle{
    private int h;
    private int w;

    private void setH(int h);
    private void setW(int w);
}
```

```java
class Square extends Rectangle{
    private int h;
    private int w;

    private void setSide(int hOrW);
}
```