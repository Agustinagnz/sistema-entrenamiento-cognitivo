Visión Arquitectónica
Objetivo

El Sistema de Entrenamiento Cognitivo Adaptativo tiene como finalidad proporcionar sesiones de entrenamiento personalizadas mediante un mecanismo de adaptación basado en métricas obtenidas durante la interacción del usuario con los ejercicios.

Principios arquitectónicos

La solución se diseñará siguiendo los siguientes principios:

separación de responsabilidades
bajo acoplamiento entre componentes
alta cohesión
independencia entre dominio e infraestructura
extensibilidad para incorporar nuevos ejercicios y estrategias de adaptación
mantenibilidad y facilidad de pruebas
Estilo arquitectónico

La solución adoptará una combinación de:

arquitectura hexagonal
clean architecture ligera
dominio fuerte
trazabilidad basada en eventos
Organización general

La arquitectura estará compuesta por:

Dominio

Contendrá las entidades y reglas de negocio.

Aplicación

Orquestará los casos de uso.

Infraestructura

Implementará persistencia y servicios externos.

Presentación

Expondrá las funcionalidades mediante una API REST.

Tecnologías principales
Python
FastAPI
SQLite
Objetivo de diseño

La arquitectura deberá permitir la evolución del sistema sin modificar las reglas centrales del dominio.