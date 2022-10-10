# Diseño 

![](img/DiagramaCachipun.PNG)

# Implementacion

```java
interface Hand {
  // 1 win, 0 draw, -1 loose
  int play(Hand v);
  int playWithStone(Stone stone);
  int playWithPaper(Paper paper);
  int playWithScissor(Scissor scissor);
}
```

```java
class Stone implements Hand {
  public int play(Hand v) {
    return v.playWithStone (this);
  }
  public int playWithStone (Stone v) {
    return 0;
  }
  public int playWithScissor (Scissor v) {
    return -1;
  }
  public int playWithPaper (Paper v) {
    return 1;
  }
}
```

```java
class Paper implements Hand {
  public int play(Hand v) {
    return v.playWithPaper (this);
  }
  public int playWithStone (Stone v) {
    return -1;
  }
  public int playWithScissor (Scissor v) {
    return 1;
  }
  public int playWithPaper (Paper v) {
    return 0;
  }
}
```

```java
class Scissor implements Hand {
  public int play(Hand v) {
    return v.playWithScissor (this);
  }
  public int playWithStone (Stone v) {
    return 1;
  }
  public int playWithScissor (Scissor v) {
    return 0;
  }
  public int playWithPaper (Paper v) {
    return -1;
  }
}
```

* Como se observa las llamadas se encuentran en orden inverso, esto quiere decir que el valor de retorno es para el objeto que envió el mensaje, y no para el que realiza el envio de mensaje de vuelta.