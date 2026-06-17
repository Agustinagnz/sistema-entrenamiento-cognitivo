ADR-002: Adopción de FastAPI
Estado

Aceptado

Contexto

El sistema requiere un mecanismo para exponer los casos de uso mediante una API REST, permitiendo la interacción con clientes externos y manteniendo una separación clara entre presentación y dominio.

Se busca una tecnología sencilla, moderna y adecuada para un proyecto académico basado en Python.

Decisión

Se utilizará FastAPI como framework para implementar la capa de presentación del sistema.

Justificación

FastAPI proporciona:

integración natural con Python
soporte para tipado estático
validación automática mediante Pydantic
generación automática de documentación OpenAPI
facilidad para construir APIs REST
buena mantenibilidad
Consecuencias
Positivas
menor complejidad de desarrollo
documentación automática
validación de datos integrada
facilidad para pruebas y mantenimiento
Negativas
dependencia del framework
necesidad de comprender conceptos propios de FastAPI
Alternativas consideradas
Flask

Ventaja:

simplicidad

Desventaja:

requiere mayor configuración y herramientas adicionales.
Django

Ventaja:

ecosistema amplio

Desventaja:

mayor complejidad para un proyecto pequeño.
Decisión final

Se adopta FastAPI por ofrecer un equilibrio adecuado entre simplicidad, productividad y mantenibilidad.