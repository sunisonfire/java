# Apuntes de Java — Clase 2: Swing (GUI)

Repositorio de apuntes personales. Esta entrada cubre el uso de **Swing** para construir interfaces gráficas, usando como ejemplo el formulario "Registro Persona" (versión personalizada con temática ORV) hecho en clase con el editor visual de NetBeans.

---

## 📌 Contenido de hoy

- ¿Qué es Swing?
- Contenedores principales: `JFrame`, `JDialog`, `JPanel`
- Componentes de entrada: `JLabel`, `JTextField`, `JComboBox`, `JRadioButton`, `JCheckBox`, `JButton`
- `ButtonGroup` para radios excluyentes
- `JOptionPane` (mensajes, confirmaciones)
- Flujo de trabajo en **modo diseño visual** (drag & drop) vs modo código
- Mapeo del formulario práctico + código de los eventos

---

## 1. ¿Qué es Swing?

Swing es la librería de Java para crear **interfaces gráficas de escritorio** (GUI).

> **GUI (Componentes visuales) + CODE (lógica en Java que reacciona a esos componentes)**

Cada componente visual (botón, campo de texto, etc.) puede tener **eventos** (ej: "cuando hagan click") que disparan código Java.

---

## 2. Contenedores principales

| Componente | Para qué sirve |
|---|---|
| `JFrame` | La **ventana principal** de la aplicación. Todo vive dentro de un JFrame. |
| `JDialog` | Una **ventana secundaria** (pop-up), útil para confirmaciones o formularios adicionales sin cerrar la ventana principal. |
| `JPanel` | Un **contenedor interno** para agrupar componentes (como una "caja" dentro de la ventana). Se usa para organizar secciones del formulario. |

Analogía: `JFrame` es la casa, `JPanel` son los cuartos donde organizas los muebles (componentes).

---

## 3. Componentes de entrada de datos

| Componente | Uso |
|---|---|
| `JLabel` | Texto no interactivo (títulos, etiquetas). También puede mostrar una **imagen** con un `icon`. |
| `JTextField` | Caja de texto para que el usuario escriba. |
| `JComboBox` | Lista desplegable (dropdown) para elegir una opción. |
| `JRadioButton` | Selección **única** dentro de un grupo. Necesita `ButtonGroup`. |
| `JCheckBox` | Selección **múltiple**, independiente entre sí. |
| `JButton` | Botón que dispara una acción (evento). |
| `JOptionPane` | Ventanas emergentes rápidas (mensajes, confirmaciones, inputs). |

⚠️ **Diferencia clave `JRadioButton` vs `JCheckBox`:**
- `JRadioButton` → mutuamente excluyentes (solo uno del grupo puede estar marcado).
- `JCheckBox` → independientes (se pueden marcar varios a la vez).

---

## 4. Modo diseño visual (NetBeans) vs modo código

En clase se trabajó **arrastrando componentes al lienzo** (Swing Containers / Swing Controls), no escribiendo `setBounds()` a mano. El IDE genera ese código automáticamente en la pestaña "Source" (entre comentarios protegidos que no se deben editar a mano).

### Paso a paso del flujo visual

1. **Crear el proyecto** → click derecho en el paquete → `New → JFrame Form`.
2. **Arrastrar contenedores** (`JPanel`) desde "Swing Containers" para dividir zonas del formulario (ej: foto a la izquierda, campos a la derecha).
3. **Arrastrar componentes** desde "Swing Controls": `JLabel`, `JTextField`, `JComboBox`, `JRadioButton`, `JCheckBox`, `JButton`.
4. **Editar propiedades sin código** en el panel "Properties": `text` (texto mostrado), `font`, `foreground` (color), `icon` (imagen).
5. **Agrupar los RadioButtons manualmente:**
   - Arrastrar un `ButtonGroup` desde la paleta (componente invisible, aparece debajo del lienzo).
   - En las propiedades de cada `JRadioButton`, asignar la propiedad `buttonGroup` al mismo grupo.
   - Sin este paso, los radios **no** son excluyentes.
6. **Doble click en un botón** → NetBeans genera automáticamente el método vacío en Source:
   ```java
   private void btnAgregarActionPerformed(java.awt.event.ActionEvent evt) {
       // tu código va aquí
   }
   ```
7. Escribir la lógica dentro de ese método (usando lo ya aprendido: `if`, `switch`, ternarios, etc.).

### Tabla comparativa

| | Modo código (a mano) | Modo diseño (drag & drop) |
|---|---|---|
| Posicionamiento | Escribes `setBounds()` | Arrastras y sueltas visualmente |
| Velocidad para prototipar | Más lento | Mucho más rápido |
| Control fino | Total | El IDE decide algunos detalles |
| Código generado | Lo escribes tú | Se genera solo, no editar zona protegida |
| Dónde va tu lógica | En cualquier parte | Solo en métodos `...ActionPerformed()` |

### ⚠️ Checklist antes de correr el programa

1. ¿Los `JRadioButton` están dentro de un `ButtonGroup`?
2. ¿Renombraste las variables (`txtNombre` en vez de `jTextField1`) **antes** de generar los eventos con doble click? (si las renombras después, el código puede quedar apuntando al nombre viejo)
3. ¿Validaste que los campos de texto no estén vacíos antes de usarlos?
4. ¿El evento está dentro del método `...ActionPerformed`, no fuera de él?

---

## 5. Caso práctico: Formulario "Registro Persona" (versión ORV)

### Mapeo de componentes

> Nombres reales del proyecto pendientes de completar — esta tabla usa la convención estándar de NetBeans (nombres por defecto) y una propuesta de nombres renombrados. Reemplazar con los nombres reales cuando se recuperen.

| Componente en el diseño | Nombre por defecto | Nombre recomendado | Tipo |
|---|---|---|---|
| Imagen del personaje | `jLabel1` | `lblFoto` | `JLabel` (con icon) |
| "[COIN BALANCE...]" | `jLabel2` | `lblBalance` | `JLabel` |
| Campo Nombre | `jTextField1` | `txtNombre` | `JTextField` |
| Campo Apellido | `jTextField2` | `txtApellido` | `JTextField` |
| Campo Documento | `jTextField3` | `txtDocumento` | `JTextField` |
| Combo Sexo | `jComboBox1` | `comboSexo` | `JComboBox` |
| Radio "T.I" | `jRadioButton1` | `radioTI` | `JRadioButton` |
| Radio "C.C" | `jRadioButton2` | `radioCC` | `JRadioButton` |
| Grupo invisible de los radios | `buttonGroup1` | `grupoTipoDoc` | `ButtonGroup` |
| Check "Principal" | `jCheckBox1` | `chkPrincipal` | `JCheckBox` |
| Check "Antagonista" | `jCheckBox2` | `chkAntagonista` | `JCheckBox` |
| Check "K.D. Companion" | `jCheckBox3` | `chkCompanion` | `JCheckBox` |
| Botón 1 | `jButton1` | `btnAgregar` (pendiente confirmar función real) | `JButton` |
| Botón 2 | `jButton2` | `btnLimpiar` (pendiente confirmar función real) | `JButton` |
| Botón 3 | `jButton3` | `btnListar` (pendiente confirmar función real) | `JButton` |

> **Pendiente:** los 3 botones hacían cosas distintas pero no se alcanzaron a anotar todas. Actualizar esta tabla y el código de abajo en cuanto se recuerden/revisen en el proyecto.

### Código de los eventos (plantilla de referencia)

#### Botón "Agregar" — leer, validar y mostrar los datos

```java
private void btnAgregarActionPerformed(java.awt.event.ActionEvent evt) {

    // 1. Leer los campos de texto
    String nombre = txtNombre.getText();
    String apellido = txtApellido.getText();
    String documento = txtDocumento.getText();

    // 2. Validar que no estén vacíos
    if (nombre.isEmpty() || apellido.isEmpty() || documento.isEmpty()) {
        JOptionPane.showMessageDialog(this,
            "Por favor complete todos los campos",
            "Error",
            JOptionPane.ERROR_MESSAGE);
        return;
    }

    // 3. Leer el combo
    String sexo = (String) comboSexo.getSelectedItem();

    // 4. Leer los radio buttons
    String tipoDoc = "";
    if (radioTI.isSelected()) {
        tipoDoc = "T.I";
    } else if (radioCC.isSelected()) {
        tipoDoc = "C.C";
    } else {
        JOptionPane.showMessageDialog(this, "Seleccione un tipo de documento");
        return;
    }

    // 5. Leer los checkbox (pueden ser varios true a la vez)
    String rol = "";
    if (chkPrincipal.isSelected())    rol += "Principal ";
    if (chkAntagonista.isSelected())  rol += "Antagonista ";
    if (chkCompanion.isSelected())    rol += "K.D. Companion ";

    if (rol.isEmpty()) {
        rol = "Sin rol asignado";
    }

    // 6. Mostrar confirmación
    String resumen = "Nombre: " + nombre + " " + apellido + "\n"
                    + "Documento: " + tipoDoc + " " + documento + "\n"
                    + "Sexo: " + sexo + "\n"
                    + "Rol: " + rol;

    JOptionPane.showMessageDialog(this, resumen, "Personaje agregado", JOptionPane.INFORMATION_MESSAGE);
}
```

#### Botón "Limpiar" — vaciar el formulario

```java
private void btnLimpiarActionPerformed(java.awt.event.ActionEvent evt) {
    txtNombre.setText("");
    txtApellido.setText("");
    txtDocumento.setText("");
    comboSexo.setSelectedIndex(0);
    grupoTipoDoc.clearSelection(); // deselecciona ambos radios a la vez
    chkPrincipal.setSelected(false);
    chkAntagonista.setSelected(false);
    chkCompanion.setSelected(false);
}
```

📌 `grupoTipoDoc.clearSelection()` es el truco para limpiar radios — no existe un `setSelected(false)` directo que deseleccione ambos sin pasar por el grupo.

#### Botón "Listar" — confirmación con `JOptionPane`

```java
private void btnListarActionPerformed(java.awt.event.ActionEvent evt) {
    int respuesta = JOptionPane.showConfirmDialog(this,
        "¿Desea ver la lista completa de personajes?",
        "Confirmar",
        JOptionPane.YES_NO_OPTION);

    if (respuesta == JOptionPane.YES_OPTION) {
        // lógica para mostrar la lista
        JOptionPane.showMessageDialog(this, "Mostrando lista...");
    }
}
```

---

## 6. Tipos de `JOptionPane`

| Método | Para qué sirve |
|---|---|
| `showMessageDialog(...)` | Solo informar algo (un botón "OK") |
| `showConfirmDialog(...)` | Preguntar Sí/No/Cancelar |
| `showInputDialog(...)` | Pedir un dato rápido por texto (devuelve un `String`) |

---

## 7. Ejemplo completo alternativo (modo 100% código, sin editor visual)

Útil como referencia si alguna vez se quiere construir el mismo formulario escribiendo el código a mano en lugar de arrastrar componentes.

```java
import javax.swing.*;
import java.awt.*;

public class RegistroPersona extends JFrame {

    public RegistroPersona() {
        setTitle("Registro Persona");
        setSize(650, 500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);

        JLabel lblNombre = new JLabel("Nombre");
        lblNombre.setBounds(350, 20, 100, 25);
        add(lblNombre);

        JTextField txtNombre = new JTextField();
        txtNombre.setBounds(350, 45, 200, 25);
        add(txtNombre);

        String[] opcionesSexo = {"Masculino", "Femenino"};
        JComboBox<String> comboSexo = new JComboBox<>(opcionesSexo);
        comboSexo.setBounds(350, 150, 150, 25);
        add(comboSexo);

        JRadioButton radioTI = new JRadioButton("T.I");
        radioTI.setBounds(350, 200, 60, 25);
        JRadioButton radioCC = new JRadioButton("C.C");
        radioCC.setBounds(420, 200, 60, 25);
        ButtonGroup grupoDocumento = new ButtonGroup();
        grupoDocumento.add(radioTI);
        grupoDocumento.add(radioCC);
        add(radioTI);
        add(radioCC);

        JCheckBox chkPrincipal = new JCheckBox("Principal");
        chkPrincipal.setBounds(350, 250, 100, 25);
        add(chkPrincipal);

        JButton btnAgregar = new JButton("Agregar");
        btnAgregar.setBounds(350, 360, 100, 30);
        btnAgregar.addActionListener(e -> {
            String nombre = txtNombre.getText();
            String sexo = (String) comboSexo.getSelectedItem();
            JOptionPane.showMessageDialog(this, "Agregado: " + nombre + " (" + sexo + ")");
        });
        add(btnAgregar);

        setVisible(true);
    }

    public static void main(String[] args) {
        new RegistroPersona();
    }
}
```

📌 `addActionListener(e -> { ... })` usa una **expresión lambda**, la forma moderna y corta de decir "cuando hagan click en este botón, ejecuta esto". La forma antigua era con una clase anónima `new ActionListener() { public void actionPerformed(...) {...} }`.

---

## 8. Resumen del flujo mental (cualquier formulario Swing)

1. Crear el `JFrame` (o `JFrame Form` en el editor visual).
2. Elegir layout (`null` manual, o arrastrar en el editor visual).
3. Agregar/declarar cada componente y posicionarlo.
4. Agrupar los excluyentes (`ButtonGroup` para radios).
5. Renombrar variables **antes** de generar eventos (doble click).
6. Conectar cada botón con su lógica (`...ActionPerformed`).
7. Validar datos de entrada antes de usarlos.
8. Mostrar la ventana (`setVisible(true)`, siempre al final en modo código).

---

## 📝 Pendientes para la próxima revisión

- [ ] Confirmar los nombres reales de las variables del proyecto (`jTextField1`, `jButton1`, etc.) y actualizar la tabla de mapeo.
- [ ] Anotar qué hace exactamente cada uno de los 3 botones "Agregar" del formulario.
- [ ] Revisar si se usó `JPanel` para dividir la zona de la imagen vs la zona de los campos.
- [ ] Preguntar si vieron `LayoutManager` (`FlowLayout`, `BorderLayout`, `GridLayout`) o si todo quedó en posicionamiento libre del editor visual.
