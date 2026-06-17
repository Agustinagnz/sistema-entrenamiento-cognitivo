ADR-001: Adopción de Arquitectura Hexagonal
Estado

Aceptado

Contexto

El Sistema de Entrenamiento Cognitivo Adaptativo posee un núcleo de negocio con reglas de adaptación, generación de ejercicios, evaluación de respuestas y persistencia de información histórica.

Se requiere una arquitectura que permita mantener independientes las reglas del dominio respecto de las tecnologías utilizadas para exponer la aplicación y almacenar la información.

Decisión

Se adopta una Arquitectura Hexagonal basada en puertos y adaptadores.

El dominio y los casos de uso se mantendrán independientes de la infraestructura.

La comunicación con elementos externos se realizará mediante interfaces (puertos) e implementaciones concretas (adaptadores).

Justificación

La Arquitectura Hexagonal permite:

desacoplar dominio e infraestructura
facilitar las pruebas unitarias
reemplazar tecnologías sin modificar la lógica de negocio
mantener alta cohesión y bajo acoplamiento
favorecer la evolución futura del sistema
Consecuencias
Positivas
mayor mantenibilidad
facilidad para realizar pruebas
independencia tecnológica
extensibilidad del sistema
Negativas
incremento inicial de la complejidad estructural
mayor cantidad de componentes y abstracciones
Alternativas consideradas
Arquitectura en capas tradicional

Ventaja:

menor complejidad inicial

Desventaja:

mayor acoplamiento entre dominio e infraestructura
Arquitectura monolítica sin separación estricta

Ventaja:

implementación rápida

Desventaja:

dificultad para evolucionar y mantener el sistema
Decisión final

Se selecciona Arquitectura Hexagonal por proporcionar un mejor equilibrio entre simplicidad, mantenibilidad y extensibilidad para un proyecto académico orientado al aprendizaje de arquitectura de software.