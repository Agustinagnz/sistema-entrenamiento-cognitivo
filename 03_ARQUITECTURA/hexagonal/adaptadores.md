Adaptadores de la Arquitectura Hexagonal
Propósito

Los adaptadores implementan los puertos definidos por la arquitectura y permiten conectar el núcleo del sistema con tecnologías externas.

Adaptadores de Entrada

Los adaptadores de entrada reciben solicitudes externas y las transforman en invocaciones a los casos de uso.

API REST
Tecnología

FastAPI

Responsabilidades
recibir solicitudes HTTP
validar datos de entrada
invocar casos de uso
devolver respuestas al cliente
Adaptadores de Salida

Los adaptadores de salida implementan los servicios requeridos por el dominio y la aplicación.

Persistencia de Usuarios
Tecnología

SQLite + SQLAlchemy

Implementa

UserRepository

Responsabilidad

Persistir y recuperar usuarios.

Persistencia de Perfiles Cognitivos
Tecnología

SQLite + SQLAlchemy

Implementa

CognitiveProfileRepository

Responsabilidad

Gestionar la evolución longitudinal del usuario.

Persistencia de Sesiones
Tecnología

SQLite + SQLAlchemy

Implementa

SessionRepository

Responsabilidad

Almacenar sesiones de entrenamiento.

Persistencia de Ejercicios
Tecnología

SQLite + SQLAlchemy

Implementa

ExerciseRepository

Responsabilidad

Gestionar plantillas e instancias de ejercicios.

Persistencia de Eventos
Tecnología

SQLite + SQLAlchemy

Implementa

EventRepository

Responsabilidad

Mantener trazabilidad del sistema.

Persistencia de Métricas
Tecnología

SQLite + SQLAlchemy

Implementa

MetricsRepository

Responsabilidad

Almacenar métricas derivadas del rendimiento.

Generador de Ejercicios
Implementa

ExerciseGenerationPort

Responsabilidad

Generar instancias de ejercicios de acuerdo con la dificultad requerida.

Evaluador de Respuestas
Implementa

ResponseEvaluationPort

Responsabilidad

Determinar la corrección de las respuestas del usuario.

Motor de Adaptación
Implementa

AdaptationEnginePort

Responsabilidad

Modificar la dificultad de los ejercicios según el desempeño observado.

Principio arquitectónico

Las reglas del dominio no conocen tecnologías concretas.

La infraestructura depende del dominio, pero el dominio no depende de la infraestructura.

Evolución futura

La arquitectura permitirá sustituir:

SQLite por PostgreSQL.
FastAPI por otro mecanismo de presentación.
El generador de ejercicios por un servicio externo.
El motor de adaptación por algoritmos más avanzados.

Sin modificar el núcleo del negocio.