Estructura de la Arquitectura Hexagonal
Propósito

Definir la organización lógica del sistema y las dependencias permitidas entre sus componentes.

Adaptadores de Entrada

Responsables de recibir solicitudes externas.

Componentes
API REST (FastAPI)
Controllers
DTOs
Aplicación

Responsable de coordinar los casos de uso.

Componentes
Session Service
Exercise Generation Service
Response Evaluation Service
Metrics Calculation Service
Adaptation Service
User Progress Service
Event Recording Service
Dominio

Contiene las reglas centrales del negocio.

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
Generador de Ejercicios
Evaluador de Respuestas
Puertos

Interfaces utilizadas por el dominio y la aplicación.

Puertos de Entrada
StartTrainingSessionUseCase
SubmitAnswerUseCase
EndTrainingSessionUseCase
GetUserProgressUseCase
Puertos de Salida
UserRepository
CognitiveProfileRepository
SessionRepository
ExerciseRepository
EventRepository
MetricsRepository
ExerciseGenerationPort
ResponseEvaluationPort
AdaptationEnginePort
Adaptadores de Salida

Implementaciones concretas.

Persistencia
SQLite
SQLAlchemy
Servicios
Generador de Ejercicios
Evaluador de Respuestas
Motor de Adaptación
Regla de Dependencias

Las dependencias siempre deben seguir la dirección:

Adaptadores de Entrada
            ↓
        Aplicación
            ↓
         Dominio
            ↓
          Puertos
            ↑
Adaptadores de Salida

El dominio no depende de tecnologías concretas.

La infraestructura depende del dominio, pero el dominio nunca depende de la infraestructura.