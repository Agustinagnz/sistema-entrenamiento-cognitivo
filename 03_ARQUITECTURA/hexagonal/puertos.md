Puertos de la Arquitectura Hexagonal
Propósito

Los puertos definen los contratos que permiten aislar el dominio y los casos de uso de las tecnologías concretas.

Puertos de Entrada

Representan las operaciones que pueden invocar los usuarios o sistemas externos.

StartTrainingSessionUseCase

Responsabilidad:

Iniciar una sesión de entrenamiento.

SubmitAnswerUseCase

Responsabilidad:

Procesar la respuesta enviada por el usuario y desencadenar la evaluación y adaptación.

EndTrainingSessionUseCase

Responsabilidad:

Finalizar una sesión y consolidar las métricas obtenidas.

GetUserProgressUseCase

Responsabilidad:

Recuperar el progreso histórico del usuario.

ManageUsersUseCase

Responsabilidad:

Administrar usuarios del sistema.

ConfigureSystemUseCase

Responsabilidad:

Modificar parámetros globales del sistema.

Puertos de Salida

Representan servicios requeridos por el dominio y la aplicación.

UserRepository

Responsabilidad:

Persistir y recuperar usuarios.

CognitiveProfileRepository

Responsabilidad:

Persistir y recuperar perfiles cognitivos.

SessionRepository

Responsabilidad:

Persistir sesiones de entrenamiento.

ExerciseRepository

Responsabilidad:

Gestionar plantillas e instancias de ejercicios.

EventRepository

Responsabilidad:

Registrar y recuperar eventos del dominio.

MetricsRepository

Responsabilidad:

Persistir métricas de desempeño.

ExerciseGenerationPort

Responsabilidad:

Generar ejercicios en función del dominio cognitivo y la dificultad.

ResponseEvaluationPort

Responsabilidad:

Evaluar respuestas y determinar si son correctas.

AdaptationEnginePort

Responsabilidad:

Determinar ajustes en la dificultad del sistema.

Principio de dependencia

El dominio depende únicamente de los puertos.

Las implementaciones concretas pertenecen a la infraestructura y pueden sustituirse sin modificar las reglas del negocio.