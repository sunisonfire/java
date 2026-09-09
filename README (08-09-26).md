# Apuntes de Java — Clase 2: Condicionales

Repositorio de apuntes personales para repasar Java. Esta primera entrada cubre las formas básicas de mostrar información en pantalla.

## 📌 Contenido de hoy

- Condicional IF
- Condicional Ternario

---

## 1. Condicional IF básico

```java
package com.s2.explicacion_s2;
import java.util.Scanner;


public class Explicacion_s2 {

    public static void main(String[] args) {
        System.out.println("Ingrese la inversion inicial");
        double inversion=new Scanner(System.in).nextDouble();
        
        System.out.println("Ingrese el valor unitario de la materia prima");
        double valor_unitario=new Scanner(System.in).nextDouble();
        
        System.out.println("Ingrese la cantidad de materia prima");
        int cantidad=new Scanner(System.in).nextInt();
        
        System.out.println("Ingrese el tiempo de produccion por producto realizado");
        int hora_hombre=new Scanner(System.in).nextInt();
        
        System.out.println("Ingrese el valor de costo por mano de obra");
        double valor_mano_obra=new Scanner(System.in).nextDouble();
        
        System.out.println("Ingrese cuantos productos va a realizar");
        int productos=new Scanner(System.in).nextInt();
        
        System.out.println("Ingrese el iva de la materia prima");
        double iva=new Scanner(System.in).nextDouble();
        
        double valor_creacion_productos=(hora_hombre*valor_mano_obra)*productos;
        double valor_materia_productos=(valor_unitario*cantidad);
        double total=0;
        if (iva>0){
            total=(valor_creacion_productos+valor_materia_productos)+((100+iva)/100);
        }else{
            total=(valor_creacion_productos+valor_materia_productos);
        }
        System.out.println("Ingrese la ganancia individual por producto");
        double ganancia=new Scanner(System.in).nextDouble();
        double margen=(total+(ganancia*producto));
        double utilidad=total_venta-inversion;
        if((utilidad/inversion)*100>20){
            System.out.println("Negocio viable");
        }else{
            System.out.println("Negocio no viable");
        }
        System.out.println("Total de creación "+total);
        System.out.println("Margen");
}
}
/*
O la version corregida*/

package com.s2.explicacion_s2;
import java.util.Scanner;

public class Explicacion_s2 {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Ingrese la inversion inicial");
        double inversion = sc.nextDouble();

        System.out.println("Ingrese el valor unitario de la materia prima");
        double valor_unitario = sc.nextDouble();

        System.out.println("Ingrese la cantidad de materia prima");
        int cantidad = sc.nextInt();

        System.out.println("Ingrese el tiempo de produccion por producto realizado");
        int hora_hombre = sc.nextInt();

        System.out.println("Ingrese el valor de costo por mano de obra");
        double valor_mano_obra = sc.nextDouble();

        System.out.println("Ingrese cuantos productos va a realizar");
        int productos = sc.nextInt();

        System.out.println("Ingrese el iva de la materia prima");
        double iva = sc.nextDouble();

        double valor_creacion_productos = (hora_hombre * valor_mano_obra) * productos;
        double valor_materia_productos = (valor_unitario * cantidad);
        double total = 0;

        if (iva > 0) {
            total = (valor_creacion_productos + valor_materia_productos) * (1 + iva / 100);
        } else {
            total = (valor_creacion_productos + valor_materia_productos);
        }

        System.out.println("Ingrese la ganancia individual por producto");
        double ganancia = sc.nextDouble();

        double margen = ganancia * productos;
        double total_venta = total + margen;
        double utilidad = total_venta - inversion;

        if ((utilidad / inversion) * 100 > 20) {
            System.out.println("Negocio viable");
        } else {
            System.out.println("Negocio no viable");
        }

        System.out.println("Total de creación: " + total);
        System.out.println("Margen: " + margen);
        System.out.println("Utilidad: " + utilidad);
    }
}
```


---

## 2. Condicionales ternarios

```java
public class Explicacion_s2 {

    public static void main(String[] args) {
        System.out.println("Ingrese los años de vida del preso");
        int años = new Scanner(System.in).nextInt();

        System.out.println("Ingrese el tipo de crimen, de 1 en adelante");
        int crimen = new Scanner(System.in).nextInt();

        double condena =
                crimen >= 1 && crimen <= 3 ?
                años * 1.08 :
                crimen >= 4 && crimen <= 9 ?
                años * 1.15 :
                crimen > 10 ?
                años * 0.5 :
                0;

        System.out.println(
        crimen < 1
        ? "El acusado es inocente"
        : "El acusado es condenado a " + condena + " años"
);

    }
}

/*
O usar la version corregida*/

double condena =
        crimen >= 1 && crimen <= 3 ?
        años * 1.08 :
        crimen >= 4 && crimen <= 9 ?
        años * 1.15 :
        crimen >= 10 ?
        años * 0.5 :
        0;
```


## 3. Switch

```
public class Explicacion_s2 {

    public static void main(String[] args) {
        /*SWITCH
        CONDICIONAL 1 variable con base a su dato, aquellos no contemplados, 
        quedan en default(int, string)
        switch(variable){
        case 1:
        break;
        case 2:
        break;
        default:
        break;
        
        Realizar un aplicativo que calcule el valor a pagar por ADDI
        mensualmente dependiendo de las cuotas escogidas
        */
        System.out.println("Ingrese el monto a financiar");
        double monto=new Scanner(System.in).nextDouble();
        System.out.println("Ingrese el numero de cuotas:1 - 3 - 6");
        int option=new Scanner(System.in).nextInt();
        double cuota=0;
        switch (option) {
            case 1:
                cuota= monto* 0.03;
                break;
            case 3:
                cuota= monto * 0.08;
                break;
            case 6:
                cuota= monto * 0.11;
                break;
            default:
                System.out.println("Cuota no encontrada, credito RECHAZADO");
        }
        System.out.println("El monto de cuota es: "+cuota);
}
}

/* o se puede*/
<img width="678" height="425" alt="image" src="https://github.com/user-attachments/assets/28b64fab-6c13-49cd-af3d-004a487e5a2c" />

```

---
## Apuntes extra

1. Cuidado con == para comparar decimales

En tu código usas double para casi todo (dinero, iva, condena). Nunca compares double con == para verificar igualdad exacta (como hiciste con condena == 0), porque los decimales tienen errores de redondeo por cómo se almacenan en binario. Por ejemplo 0.1 + 0.2 == 0.3 da false en Java. Mejor usa comparaciones con un margen de tolerancia, o evita depender de igualdad exacta en decimales cuando puedas.

2. Validar antes de dividir

Ya lo mencioné con inversion, pero es un patrón general: cualquier división con un valor que viene del usuario necesita validación previa. Un if (denominador != 0) te ahorra un ArithmeticException (con enteros) o un Infinity/NaN silencioso (con doubles), que es peor porque no truena, simplemente da resultados absurdos sin avisar.

3. Diferencia entre int y double al dividir

Ojo con esto, es un error clásico de principiante:

java
int a = 5, b = 2;
double resultado = a / b; // da 2.0, NO 2.5 ❌
double resultado2 = (double) a / b; // da 2.5 ✅

Si divides dos int, Java hace división entera y trunca el decimal antes de asignarlo al double. Hay que castear ((double)) al menos uno de los operandos.

4. Scanner y el error típico nextInt() + nextLine()

No lo usaste esta vez, pero te va a pasar pronto: si mezclas nextInt()/nextDouble() con nextLine() en el mismo Scanner, nextLine() a veces "se come" un salto de línea vacío y parece que se salta la pregunta. Cuando llegues a leer texto (String) después de un número, probablemente necesites un sc.nextLine() extra para "limpiar" el buffer.

5. Nombres de variables: evita tildes y ñ

Usaste años como nombre de variable — funciona en Java porque soporta Unicode, pero no es buena práctica: puede dar problemas de encoding según el editor/consola (verías símbolos raros), y la convención de la industria es nombrar variables en inglés sin caracteres especiales. Mejor anios o years.

6. switch con Strings y enums (para más adelante)

Ya viste switch con int. Cuando avances, vas a poder usarlo también con String:

java
switch (opcionTexto) {
    case "mensual": ...
    case "anual": ...
}

Y en versiones más nuevas de Java existe el switch expression (con -> en vez de : y sin necesidad de break), que es más moderno y menos propenso a errores de fall-through accidental. Si tu profesor menciona switch (x) { case 1 -> ...; }, es esa versión.

7. Regla mental para elegir el condicional correcto

Cuando dudes entre if, ternario o switch, pregúntate:

¿Necesito ejecutar varias líneas de código (no solo devolver un valor)? → if/else
¿Solo necesito asignar un valor según una condición simple? → ternario
¿Estoy comparando una sola variable contra valores exactos y discretos? → switch

## 📝 Notas

<img width="742" height="169" alt="image" src="https://github.com/user-attachments/assets/eed2b8ee-6aa4-4a3e-a97a-d7c2573fa619" />
