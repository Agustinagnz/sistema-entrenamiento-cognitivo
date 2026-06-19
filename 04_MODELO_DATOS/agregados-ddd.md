Agregados del Dominio
Propósito

Definir los agregados y sus límites de consistencia siguiendo Domain-Driven Design.

Agregado Usuario
Raíz del agregado

Usuario

Entidades internas
Perfil Cognitivo
Responsabilidades
mantener la identidad del usuario
almacenar configuración y preferencias
mantener la evolución longitudinal del perfil cognitivo
Invariantes
todo Perfil Cognitivo pertenece a un único Usuario
un Usuario debe poseer exactamente un Perfil Cognitivo
Agregado Sesión de Entrenamiento
Raíz del agregado

SesionEntrenamiento

Entidades internas
InstanciaEjercicio
Evento
Metrica
Responsabilidades
controlar el ciclo de vida de una sesión
mantener la secuencia de ejercicios
registrar eventos
generar métricas derivadas
Invariantes
una sesión debe pertenecer a un usuario existente
una sesión solo puede encontrarse en un estado válido
un evento siempre pertenece a una sesión
Agregado Ejercicio
Raíz del agregado

PlantillaEjercicio

Responsabilidades
definir reglas de generación
definir el mecanismo de evaluación
establecer dificultad base
Invariantes
toda plantilla posee un tipo cognitivo válido
toda plantilla debe tener una estrategia de validación
Relaciones entre agregados
Usuario
    │
    └─────< SesionEntrenamiento

SesionEntrenamiento
    │
    └─────> PlantillaEjercicio
Comunicación entre agregados

La comunicación entre agregados debe realizarse mediante identificadores y servicios del dominio.

No deben existir referencias directas entre entidades pertenecientes a distintos agregados.

Servicios de Dominio
MotorAdaptacion
GeneradorEjercicios
EvaluadorRespuestas
Principios aplicados
alta cohesión
bajo acoplamiento
consistencia transaccional por agregado
independencia entre agregados