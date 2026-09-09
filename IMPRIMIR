# Apuntes de Java — Clase 1: Salida de datos por consola y ventanas

Repositorio de apuntes personales para repasar Java. Esta primera entrada cubre las formas básicas de mostrar información en pantalla.

## 📌 Contenido de hoy

- Las 3 formas de imprimir en consola
- Uso de `JOptionPane`
- Qué es Swing
- Atajos de teclado útiles para escribir más rápido

---

## 1. Las 3 formas de mostrar texto por consola

```java
public class Main {
    public static void main(String[] args) {
        System.out.print("Hola");      // No salta de línea
        System.out.println("Hola");    // Sí salta de línea
        System.out.printf("Hola %s, tienes %d años%n", "Ana", 20); // Con formato
    }
}
```

| Método      | Salta de línea | Uso principal                        |
|-------------|:--------------:|---------------------------------------|
| `print()`   | No             | Texto simple, pegado                  |
| `println()` | Sí             | Texto simple, ordenado (el más usado) |
| `printf()`  | No (hay que poner `%n`) | Texto con formato / variables |

**Placeholders comunes de `printf`:**
- `%s` → texto (String)
- `%d` → número entero
- `%f` → número decimal
- `%n` → salto de línea

---

## 2. JOptionPane

Clase de la librería `javax.swing` para mostrar **ventanas emergentes** en vez de usar la consola.

```java
import javax.swing.JOptionPane;

public class Main {
    public static void main(String[] args) {
        // Mostrar un mensaje
        JOptionPane.showMessageDialog(null, "¡Hola, mundo!");

        // Pedir un dato (siempre devuelve String)
        String nombre = JOptionPane.showInputDialog("¿Cómo te llamas?");

        // Mostrar el resultado
        JOptionPane.showMessageDialog(null, "Hola " + nombre);
    }
}
```

**Métodos más usados:**
- `showMessageDialog(null, mensaje)` → muestra un mensaje.
- `showInputDialog(pregunta)` → pide un dato (String). Si necesito un número: `Integer.parseInt(dato)`.
- `showConfirmDialog(...)` → pregunta con botones Sí / No / Cancelar.

⚠️ **Recordar:** siempre hay que importar la clase arriba del todo con `import javax.swing.JOptionPane;`

---

## 3. ¿Qué es Swing?

**Swing** es la biblioteca de Java para construir **interfaces gráficas** (ventanas, botones, campos de texto, etc.).

`JOptionPane` es solo una parte de Swing (una ventanita ya armada). Otras clases de Swing que probablemente veamos después:

- `JFrame` → ventana completa
- `JButton` → botón
- `JLabel` → etiqueta de texto
- `JTextField` → caja de texto para escribir

Truco para reconocerlas: casi todas las clases de Swing empiezan con **J**.

---

## 4. Atajos de teclado para escribir más rápido

Estos son "live templates" o "code snippets": escribes la palabra clave y presionas `Tab` (o `Enter` según el IDE) y se autocompleta el código.

### En IntelliJ IDEA
| Escribes   | Se convierte en                          |
|------------|-------------------------------------------|
| `sout`     | `System.out.println();`                   |
| `souf`     | `System.out.printf();`                    |
| `soutv`    | `System.out.println("variable = " + variable);` |
| `psvm`     | `public static void main(String[] args) {}` |
| `main`     | igual que `psvm` (variante corta)          |
| `fori`     | ciclo `for` clásico con índice `i`         |
| `iter`     | ciclo `for-each`                           |
| `ifn`      | `if (var == null)`                        |

### En Eclipse
Son parecidos, se llaman "templates": `sysout` + `Ctrl+Espacio` (o Tab), `psvm` + Tab, etc.

> 💡 Tip: si el autocompletado no aparece, revisa que estés dentro del cuerpo de un método (dentro de las llaves `{ }` de `main`, por ejemplo), estos atajos no funcionan afuera de un bloque de código.

---

## 5. Cómo pedir datos al usuario (2 formas)

**Forma 1: con `Scanner` (consola)**
```java
Scanner leer = new Scanner(System.in);
String nombre = leer.nextLine();
int edad = leer.nextInt();
float estatura = leer.nextFloat();
```

**Forma 2: con `JOptionPane` (ventana)**
```java
String nombre = JOptionPane.showInputDialog("Ingrese el nombre");
int edad = Integer.parseInt(JOptionPane.showInputDialog("Ingrese su edad"));
```
⚠️ `showInputDialog` **siempre devuelve un `String`**. Si necesitas un número, hay que convertirlo con `Integer.parseInt(...)` o `Float.parseFloat(...)`.

## 6. Text blocks (`"""`) + `.formatted()`

Sirven para escribir texto de varias líneas sin usar `\n`, y `.formatted()` reemplaza los `%s` con variables (como `printf`).

```java
System.out.println("""
        Bienvenido %s a nuestro sistema
        Tu edad es %s y tu estatura %s
        """.formatted(nombre, edad, estatura));
```

## 7. Errores comunes que ya cometí (para no repetirlos)

- **Declarar la misma variable dos veces** en el mismo método → error de compilación (`variable ya está definida`). Pasa cuando pruebo dos formas distintas de pedir el mismo dato y no borro la primera.
- **Mezclar `nextInt()` / `nextFloat()` con `nextLine()`**: los primeros no consumen el "enter" que queda en el buffer, entonces el siguiente `nextLine()` se ejecuta solo y devuelve vacío. Solución: agregar un `leer.nextLine();` extra después de leer un número, antes de volver a usar `nextLine()`.
- **Crear un `Scanner` nuevo cada vez** (`new Scanner(System.in)`) en vez de reutilizar el que ya abrí al principio. No siempre es un error pero no es buena práctica.
- **Copiar y pegar un mensaje de diálogo sin cambiar el texto** (ej. pedir la edad pero el mensaje dice "Ingrese su nombre").

## 📝 Notas personales
_(espacio para dudas, errores comunes, cosas que el profe explicó y borró antes de que las copiara, etc.)_

-
-
