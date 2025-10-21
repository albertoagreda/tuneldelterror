<div align="center">

# 🎃 <span style="color:orange;">Proyecto JavaFX</span>  
## 🕸️ <span style="color:#ff7518;">“Túnel del Terror → Ruleta TRUCO / TRATO”</span>

**Autor:** Alberto  
**Centro:** MEDAC Sevilla  
**Módulo:** M5 – Desarrollo de Interfaces  

<img src="https://i.imgur.com/Xmp7Rfa.png" width="500" alt="Halloween Banner"/>

</div>

---

## 📚 **ÍNDICE**
1. 🎃 [Introducción](#-introducción)  
2. 🧭 [Objetivos del Proyecto](#-objetivos-del-proyecto)  
3. 🧩 [Estructura General](#-estructura-general)  
4. 💻 [Explicación del Código](#-explicación-del-código)  
   - [4.1. Pantalla de Entrada al Túnel](#️-41-pantalla-de-entrada-al-túnel)  
   - [4.2. Paso de Datos entre Pantallas](#-42-paso-de-datos-entre-pantallas)  
   - [4.3. Pantalla de la Ruleta](#-43-pantalla-de-la-ruleta)  
   - [4.4. Estilo y Diseño (CSS)](#️-44-estilo-y-diseño-css)  
5. ⚙️ [Dificultades y Aprendizaje](#-dificultades-y-aprendizaje)  
6. 🧡 [Conclusión](#-conclusión)  
7. 📸 [Capturas del Proyecto](#-capturas-del-proyecto)  

---

## 🎃 **Introducción**

El proyecto **“Túnel del Terror → Ruleta TRUCO/TRATO”** es una miniaplicación creada con **JavaFX** y **Scene Builder**.  
Su propósito es ofrecer una experiencia divertida e inmersiva inspirada en **Halloween**, combinando animaciones, validaciones y un diseño temático.

---

## 🎯 **Objetivos del Proyecto**

- Crear una interfaz visual atractiva y coherente con la temática.  
- Validar correctamente los campos de entrada antes de continuar.  
- Implementar una **ruleta animada** que muestre un resultado aleatorio.  
- Aprender a **pasar información entre pantallas** usando controladores JavaFX.  
- Ofrecer una **experiencia fluida y dinámica** al usuario.  

---

## 🧩 **Estructura General**

El proyecto se compone de **dos pantallas principales**:

1. **Entrada al Túnel** → (`entrada.fxml` + `EntradaController.java`)  
   Recoge el nombre, apellidos y curso del usuario.  

2. **Ruleta TRUCO/TRATO** → (`ruleta.fxml` + `RuletaController.java`)  
   Muestra los datos y lanza la animación de la ruleta.  

Ambas pantallas se comunican mediante **controladores JavaFX**, enlazados con archivos **FXML** y un **estilo CSS** común.

---

## 💻 **Explicación del Código**

### 🏚️ **4.1. Pantalla de Entrada al Túnel**

Esta vista contiene:
- **TextField** para nombre  
- **TextField** para apellidos  
- **ComboBox** para curso (DAM1, DAM2, DAW1, DAW2, SMR1, SMR2)  

Al pulsar **“Entrar si te atreves”**:
1. Se valida que no haya campos vacíos.  
2. Si falta alguno, se muestra un mensaje de error claro.  
3. Si todo es correcto, se pasa a la pantalla de la ruleta.  

📜 *Validación simple con condicionales y mensajes en etiquetas (`Label`).*

---

### 🧠 **4.2. Paso de Datos entre Pantallas**

El paso de datos se logra mediante un **setter** en el segundo controlador:

```java
public void setDatos(String nombre, String apellidos, String curso) {
    labelNombre.setText(nombre + " " + apellidos);
    labelCurso.setText(curso);
}
🔁 El controlador de la primera pantalla llama a este método antes de cargar la segunda vista.
De esta forma, los datos del usuario se muestran correctamente en la ruleta.

🎡 4.3. Pantalla de la Ruleta
En esta parte:

Se muestra el nombre completo y curso del usuario.

Al presionar GIRAR, se ejecuta una animación de rotación sobre la imagen de la ruleta.

java
Copiar código
RotateTransition rt = new RotateTransition(Duration.seconds(3), ruleta);
rt.setByAngle(720 + Math.random() * 360);
rt.setInterpolator(Interpolator.EASE_OUT);
rt.play();
Durante el giro:

El botón GIRAR se desactiva temporalmente.

Al terminar, se genera un valor aleatorio:

0 → TRUCO 🎭

1 → TRATO 🍬

🧠 Se muestra un mensaje claro en pantalla con el resultado, y el botón vuelve a estar disponible.

🕯️ 4.4. Estilo y Diseño (CSS)
El archivo halloween.css define la estética con:

🎨 Colores negros, naranjas y púrpuras.

✍️ Tipografía decorativa con buena legibilidad.

🕸️ Fondos temáticos y botones con efectos hover.

El diseño se realizó completamente con Scene Builder, ajustando anclajes y márgenes para una visualización perfecta.

⚙️ Dificultades y Aprendizaje
💀 Durante el desarrollo tuve que repetir la tarea 3 o 4 veces desde cero,
ya que el código original daba errores y la ruleta no giraba correctamente.

Cada intento me ayudó a:

Comprender mejor los controladores JavaFX.

Manejar la carga de escenas con FXMLLoader.

Controlar los eventos de animación y sincronización de interfaz.

📈 Gracias a la práctica constante, logré un resultado totalmente funcional y pulido.
