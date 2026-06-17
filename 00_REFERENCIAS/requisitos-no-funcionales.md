# Requisitos No Funcionales

## Introducción

Los requisitos no funcionales establecen los atributos de calidad y las restricciones bajo las cuales deberá operar el Sistema de Entrenamiento Cognitivo Adaptativo.

---

## Rendimiento

### RNF-01. Tiempo de respuesta

El sistema deberá responder a las operaciones habituales en un tiempo adecuado para mantener la continuidad de las sesiones de entrenamiento.

### RNF-02. Adaptación en tiempo de ejecución

La actualización del nivel de dificultad deberá realizarse durante la sesión sin interrupciones perceptibles para el usuario.

---

## Persistencia

### RNF-03. Conservación de la información

El sistema deberá almacenar de forma persistente la información de usuarios, sesiones y eventos.

### RNF-04. Integridad de los datos

La información almacenada deberá mantenerse consistente durante las operaciones del sistema.

---

## Mantenibilidad

### RNF-05. Separación de responsabilidades

La solución deberá organizarse en módulos con responsabilidades claramente definidas.

### RNF-06. Bajo acoplamiento

Los componentes del sistema deberán minimizar las dependencias entre sí.

### RNF-07. Alta cohesión

Cada módulo deberá concentrarse en una única responsabilidad principal.

---

## Escalabilidad y Extensibilidad

### RNF-08. Incorporación de nuevos ejercicios

El diseño deberá permitir agregar nuevos tipos de ejercicios sin modificar significativamente los componentes existentes.

### RNF-09. Evolución del motor de adaptación

El mecanismo de adaptación deberá poder reemplazarse o ampliarse sin afectar al resto del sistema.

---

## Trazabilidad

### RNF-10. Registro de eventos

El sistema deberá conservar evidencia de las interacciones realizadas durante las sesiones.

### RNF-11. Reconstrucción histórica

La información almacenada deberá permitir reconstruir el historial de entrenamiento del usuario.

---

## Portabilidad

### RNF-12. Independencia de plataforma

La aplicación deberá poder ejecutarse en distintos sistemas operativos compatibles con Python.

---

## Seguridad

### RNF-13. Protección de la información

El acceso a los datos deberá limitarse a usuarios autorizados.

### RNF-14. Validación de datos

Las entradas recibidas por el sistema deberán ser validadas antes de ser procesadas.

---

## Usabilidad

### RNF-15. Facilidad de uso

La interfaz deberá permitir realizar sesiones de entrenamiento de forma sencilla e intuitiva.

---

## Restricciones Tecnológicas

### RNF-16. Tecnologías base

La solución se desarrollará utilizando Python, FastAPI y SQLite.

### RNF-17. Arquitectura modular

El sistema deberá estructurarse mediante una arquitectura por capas con separación entre dominio, aplicación e infraestructura.
