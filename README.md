# CV-HMI: Control Gestual mediante Visión Artificial
### Propuesta de Transferencia Tecnológica | Fablab UV

Este repositorio contiene el material técnico y didáctico para el taller intensivo de **Interfaz Hombre-Máquina (HMI)** basado en visión artificial. El proyecto está diseñado para ser implementado en una sesión de 90 minutos, transformando una cámara web en un sensor de control sin contacto.

## Objetivo del Taller
Desarrollar un sistema de control gestual funcional capaz de:
1.  **Captura Proactiva:** Procesar video en tiempo real con latencia mínima.
2.  **Detección de Landmarks:** Localizar los 21 puntos clave de la mano usando el modelo de grafos de **MediaPipe**.
3.  **Lógica de Interacción:** Mapear coordenadas espaciales para activar "Botones Virtuales" (ROI - Region of Interest).

## Requisitos del Sistema
Para asegurar la compatibilidad durante el taller, se requiere:

*   **Lenguaje:** Python 3.8 o superior.
*   **Hardware:** Webcam integrada o USB.
*   **Librerías Necesarias:**
    ```bash
    pip install opencv-python mediapipe numpy
    ```

## Estructura del Repositorio
*   `main.py`: Código final con la lógica de colisión y feedback visual completa.
*   `starter_template.py`: Código base (esqueleto) para que los estudiantes completen durante el taller.
*   `requirements.txt`: Archivo de dependencias para instalación rápida.

## Implementación Técnica
El flujo de trabajo se centra en la detección del **Landmark 8** (punta del dedo índice). El script calcula si la posición $(x, y)$ del dedo se encuentra dentro de los límites de un rectángulo dibujado mediante OpenCV:

$$ (x_{min} < x_{finger} < x_{max}) \land (y_{min} < y_{finger} < y_{max}) $$

Al cumplirse esta condición, el sistema dispara un evento visual (cambio de color) que simula el accionamiento de un actuador físico en un entorno industrial o de salud.

## Metodología (ABP)
El taller utiliza **Aprendizaje Basado en Problemas**, desafiando a los alumnos a resolver la operatividad de interfaces en entornos donde el contacto físico es riesgoso o imposible (ej. quirófanos, talleres mecánicos o manipulación de sustancias peligrosas).

---
**Desarrollado para el Fablab de la Universidad de Valparaíso**  
*Módulo: Visión Artificial Aplicada*
