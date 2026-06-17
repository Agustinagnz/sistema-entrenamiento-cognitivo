ADR-003: Adopción de SQLite
Estado

Aceptado

Contexto

El Sistema de Entrenamiento Cognitivo Adaptativo requiere persistir usuarios, perfiles cognitivos, sesiones, eventos y métricas para mantener continuidad y trazabilidad.

La solución debe ser simple, fácilmente desplegable y adecuada para un proyecto académico orientado al aprendizaje de arquitectura de software.

Decisión

Se utilizará SQLite como sistema de gestión de base de datos en la versión inicial del proyecto.

Justificación

SQLite proporciona:

configuración mínima
ausencia de servidor dedicado
almacenamiento persistente en un único archivo
facilidad de uso en proyectos pequeños
compatibilidad con Python y SQLAlchemy
portabilidad entre sistemas operativos
Consecuencias
Positivas
instalación sencilla
bajo consumo de recursos
facilidad para pruebas y desarrollo local
menor complejidad operativa
Negativas
capacidad limitada para escenarios concurrentes
menor escalabilidad frente a motores cliente-servidor
restricciones para cargas de trabajo intensivas
Alternativas consideradas
PostgreSQL

Ventaja:

mayor escalabilidad y robustez.

Desventaja:

complejidad innecesaria para un MVP académico.
MySQL

Ventaja:

amplia adopción.

Desventaja:

necesidad de administrar un servidor adicional.
Decisión final

Se selecciona SQLite como solución de persistencia inicial por ofrecer la simplicidad y capacidades necesarias para la primera versión del sistema.