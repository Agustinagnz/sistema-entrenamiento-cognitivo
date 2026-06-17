Diagrama C4 - Nivel 3: Componentes
Propósito

Este diagrama identifica los principales componentes internos del Sistema de Entrenamiento Cognitivo Adaptativo y sus responsabilidades.

API REST
Responsabilidad

Exponer los casos de uso del sistema mediante endpoints HTTP.

Componentes
Controladores
DTOs de entrada y salida
Validación de datos
Servicios de Aplicación
SessionService

Responsable de coordinar el ciclo de vida de las sesiones de entrenamiento.

ExerciseGenerationService

Responsable de solicitar la generación de ejercicios.

ResponseEvaluationService

Responsable de evaluar las respuestas del usuario.

MetricsCalculationService

Responsable de calcular métricas de desempeño.

AdaptationService

Responsable de determinar la evolución de la dificultad.

UserProgressService

Responsable de actualizar el perfil cognitivo y recuperar información histórica.

EventRecordingService

Responsable de registrar eventos relevantes para garantizar trazabilidad.

Dominio
Entidades
Usuario
Perfil Cognitivo
Sesión de Entrenamiento
Plantilla de Ejercicio
Instancia de Ejercicio
Evento
Métrica
Servicios de Dominio
Motor de Adaptación
Evaluador de Respuestas
Generador de Ejercicios
Persistencia
Repositorios
UserRepository
CognitiveProfileRepository
SessionRepository
ExerciseRepository
EventRepository
MetricsRepository
Relaciones principales
API REST
     │
     ▼
Servicios de Aplicación
     │
     ▼
Dominio
     │
     ▼
Repositorios
     │
     ▼
SQLite
Principios de diseño
una única responsabilidad por componente
alta cohesión
bajo acoplamiento
independencia entre dominio e infraestructura
facilidad para realizar pruebas y sustituir implementaciones