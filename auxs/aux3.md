# JUnit 5

* Para crear tests debemos crear una clase con metodos especiales
* Anotaciones utiles del framework:
  * `@Test`: Son los metodos que prueban la funcionalidad del programa. Para esto se utilizan metodos de JUnit, los mas comunes son `assertEquals`, `assertTrue` y `assertFalse`.
  * `@BeforeEach`: El metodo marcado con esto se ejecuta **antes** de cada test.
  * `@AfterEach`: El metodo marcado con esto se ejecuta despues de cada test.

Ejemplo JUnit 5.x:
* En este caso no es necesario explicitar el privilegio de la clase ni de los metodos de test.

```java
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

class GameMat {
  @Override
  public bool equals(final Object obj) {
    return obj instanceof GameMat;
  }
}
class GameMatTest {
  private GameMat testMat;

  @BeforeEach
  void setUp() {
    testMat = new GameMat();
  }

  @Test
  void basicTest() {
    var expectedMat = new GameMat();
    assertEquals(expectedMat, testMat);
  }

}
```

**OBS:** El `equals()` implementado es solo para mostrar que el ejemplo del test funciona.