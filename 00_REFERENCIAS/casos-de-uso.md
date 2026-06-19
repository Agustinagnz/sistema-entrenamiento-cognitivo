# Casos de Uso

## Introducción

Los casos de uso describen las interacciones principales entre los actores y el Sistema de Entrenamiento Cognitivo Adaptativo.

---

# CU-01 Iniciar sesión de entrenamiento

Objetivo

Iniciar una sesión de entrenamiento cognitivo personalizada basada en el perfil del usuario.

Actores

Usuario final

Disparador

El usuario solicita iniciar entrenamiento.

Precondiciones
Usuario existente y activo
Perfil cognitivo disponible
Sistema operativo y sin fallos de infraestructura
Postcondiciones
Sesión creada y persistida
Ejercicio inicial generado
Evento inicio_sesion registrado
Flujo principal
El usuario solicita iniciar sesión.
El sistema valida existencia y estado del usuario.
El sistema recupera el perfil cognitivo.
Se crea una nueva sesión en estado “activa”.
El motor de generación produce el primer ejercicio parametrizado.
El ejercicio se asocia a la sesión.
Se registra el evento de inicio de sesión.
El sistema devuelve la sesión activa con el ejercicio inicial.
Flujos alternativos

A1. Usuario sin perfil cognitivo

Se crea un perfil inicial con valores base.
Se continúa en el paso 4.
Excepciones

E1. Usuario inactivo o bloqueado

Se rechaza la operación
Se notifica error de estado de cuenta

E2. Falla del generador de ejercicios

Se crea sesión sin ejercicio inicial
Se registra evento de error técnico
Reglas de negocio
Una sola sesión activa por usuario
Toda sesión debe iniciar con al menos un ejercicio
Puertos involucrados
StartTrainingSession (entrada)
UserRepository (salida)
CognitiveProfileRepository (salida)
ExerciseGenerationPort (salida)
EventRepository (salida)
# CU-02 Resolver ejercicio

Objetivo

Registrar, evaluar y adaptar dinámicamente la dificultad en función de la respuesta del usuario.

Actores

Usuario final

Disparador

El usuario envía una respuesta a un ejercicio activo.

Precondiciones
Sesión activa
Ejercicio pendiente de resolución
Postcondiciones
Respuesta registrada
Métricas actualizadas
Dificultad adaptada
Nuevo ejercicio generado o sesión en espera
Eventos de evaluación y adaptación registrados
Flujo principal
El sistema recibe la respuesta del usuario.
Se valida que el ejercicio pertenezca a la sesión activa.
Se registra tiempo de respuesta.
El motor de evaluación procesa la respuesta.
Se generan métricas de rendimiento.
El motor de adaptación ajusta la dificultad.
Se genera un nuevo ejercicio con la nueva configuración.
Se registra el evento evaluacion_respuesta y ajuste_dificultad.
Flujos alternativos

A1. Respuesta fuera de tiempo límite

Se marca como incorrecta o incompleta según política del sistema.

A2. Ejercicio ya respondido

Se rechaza la operación
Excepciones

E1. Fallo en evaluación

Se registra respuesta sin evaluación
Se marca métrica como pendiente

E2. Error en motor de adaptación

Se mantiene dificultad previa
Reglas de negocio
Toda respuesta genera métricas
La adaptación es obligatoria salvo error técnico
No se permite doble respuesta por ejercicio
Puertos involucrados
SubmitAnswer (entrada)
ResponseEvaluationPort (salida)
AdaptationEnginePort (salida)
MetricsRepository (salida)
EventRepository (salida)

# CU-03 Finalizar sesión


Objetivo

Cerrar una sesión de entrenamiento consolidando métricas y actualizando el perfil cognitivo.

Actores

Usuario final

Precondiciones
Sesión activa existente
Postcondiciones
Sesión finalizada
Perfil cognitivo actualizado
Métricas consolidadas
Evento fin_sesion registrado
Flujo principal
El usuario solicita finalizar sesión.
El sistema valida sesión activa.
Se consolidan métricas acumuladas.
Se actualiza el perfil cognitivo.
Se cambia estado de sesión a “finalizada”.
Se registran eventos finales.
Flujos alternativos

A1. Sesión sin actividad

Se finaliza sin actualización significativa del perfil.
Excepciones

E1. Error en persistencia de métricas

La sesión se marca como “finalización parcial”
Reglas de negocio
Toda sesión finalizada debe generar actualización de perfil
No se puede reabrir una sesión finalizada
Puertos involucrados
EndTrainingSession (entrada)
MetricsRepository (salida)
CognitiveProfileRepository (salida)
SessionRepository (salida)
EventRepository (salida)
# CU-04 Consultar progreso histórico
I
Objetivo

Visualizar evolución cognitiva del usuario a lo largo del tiempo.

Actores

Usuario final

Flujo principal
El usuario solicita historial.
El sistema recupera sesiones.
El sistema agrega métricas por dimensión cognitiva.
Se calcula evolución temporal.
Se devuelve resumen analítico.
Excepciones

E1. Sin datos suficientes

Se devuelve estado inicial sin evolución.
Reglas de negocio
Solo sesiones finalizadas cuentan para evolución
Puertos
GetUserProgress (entrada)
MetricsRepository (salida)
SessionRepository (salida)
# CU-05 Administrar usuarios
Objetivo

Gestionar ciclo de vida de usuarios del sistema.

Flujo principal
Administrador consulta usuarios.
Crea/modifica/desactiva usuario.
Se persisten cambios.
Reglas
No se eliminan usuarios, solo desactivación lógica
Puertos
ManageUsers (entrada)
UserRepository (salida)

# CU-06 Configurar parámetros globales
Objetivo

Modificar parámetros del sistema de adaptación y generación.

Flujo principal
Administrador accede configuración.
Modifica parámetros globales.
Se validan restricciones.
Se persiste configuración.
Reglas
Cambios afectan solo nuevas sesiones
Puertos
ConfigureSystem (entrada)