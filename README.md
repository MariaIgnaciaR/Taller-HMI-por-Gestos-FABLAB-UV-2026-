# CV-HMI: Control Gestual mediante Visión Artificial
### Propuesta de Transferencia Tecnológica | Fablab UV

Este repositorio contiene el material técnico y didáctico para el taller intensivo de **Interfaz Hombre-Máquina (HMI)** basado en visión artificial. El proyecto está diseñado para ser implementado en una sesión de 90 minutos, transformando una cámara web en un sensor de control sin contacto.

---

# Objetivo del Taller

Desarrollar un sistema de control gestual funcional capaz de:

1. **Captura Proactiva:** Procesar video en tiempo real con latencia mínima.
2. **Detección de Landmarks:** Localizar los 21 puntos clave de la mano usando el modelo de grafos de **MediaPipe**.
3. **Lógica de Interacción:** Mapear coordenadas espaciales para activar "Botones Virtuales" (ROI - Region of Interest).

---

# Requisitos del Sistema

Para asegurar compatibilidad durante el taller, se recomienda:

* **Python:** 3.10+ (64-bit)
* **Hardware:** Webcam integrada o USB.
* **Sistema Operativo:** Windows 10/11 recomendado.

---

# Instalación del Entorno

## 1. Instalar Python 3.10+

Descargar desde:

https://www.python.org/downloads/

Durante la instalación marcar:

```text
☑ Add python.exe to PATH
```

---

## 2. Crear entorno virtual

Abrir PowerShell en la carpeta del proyecto:

```bash
py -3 -m venv .venv
```

---

## 3. Activar entorno virtual

### Windows PowerShell

```bash
.venv\Scripts\activate
```

Si el entorno se activó correctamente, la terminal mostrará:

```bash
(.venv)
```

---

# Instalación de Librerías

Instalar:

```bash
pip install mediapipe opencv-python numpy
```

Nota: En la primera ejecucion, el modelo de mano se descarga automaticamente.

---

# Ejecución del Proyecto

Ejecutar:

```bash
python main.py
```

Presionar:

```text
ESC
```

para cerrar la ventana de OpenCV.

---

# Estructura del Repositorio

```text
CV-HMI/
│
├── main.py
├── starter_template.py
├── requirements.txt
└── README.md
```

### Archivos

* `main.py`  
  Código final con detección de mano, interacción y feedback visual.

* `starter_template.py`  
  Código base para desarrollo guiado durante el taller.

* `requirements.txt`  
  Dependencias necesarias para el proyecto.

---

# Implementación Técnica

El flujo de trabajo se centra en la detección del **Landmark 8** (punta del dedo índice).

El sistema calcula si la posición del dedo se encuentra dentro de una región rectangular dibujada mediante OpenCV:

$$
(x_{min} < x_{finger} < x_{max}) \land (y_{min} < y_{finger} < y_{max})
$$

Cuando esta condición se cumple, el sistema activa un evento visual que simula el accionamiento de un actuador físico.

---

# Flujo del Sistema

1. Captura de video mediante webcam.
2. Conversión BGR → RGB.
3. Procesamiento mediante MediaPipe.
4. Extracción de landmarks.
5. Obtención de coordenadas del dedo índice.
6. Verificación de colisión con ROI.
7. Activación visual del botón virtual.

---

# Tecnologías Utilizadas

* Python
* OpenCV
* MediaPipe
* NumPy
* Visión Artificial
* Procesamiento en Tiempo Real
* Interfaces HMI

---

# Aplicaciones Potenciales

* Interfaces médicas sin contacto
* Automatización industrial
* Control gestual
* Sistemas interactivos
* Robótica
* Accesibilidad
* Domótica

---

# Metodología (ABP)

El taller utiliza **Aprendizaje Basado en Problemas (ABP)**, desafiando a los estudiantes a resolver la operatividad de interfaces en entornos donde el contacto físico es riesgoso o imposible, por ejemplo:

* Quirófanos
* Talleres mecánicos
* Laboratorios
* Manipulación de sustancias peligrosas

---

# Resultados Esperados

Al finalizar el taller, el estudiante será capaz de:

* Capturar video en tiempo real.
* Utilizar modelos de visión artificial.
* Detectar landmarks de mano.
* Implementar regiones de interacción.
* Construir interfaces gestuales funcionales.
* Comprender principios básicos de HMI basados en visión computacional.

---

# Créditos

Desarrollado para el **Fablab de la Universidad de Valparaíso**  
*Módulo: Visión Artificial Aplicada*
