Modelo del Dominio
Propósito

Definir las entidades principales, objetos de valor y agregados del Sistema de Entrenamiento Cognitivo Adaptativo.

Agregado Usuario

Representa la evolución longitudinal del entrenante.

Entidades
Usuario

Responsable de identificar al usuario dentro del sistema.

Atributos principales:

id_usuario
fecha_creacion
estado_cuenta
idioma
preferencias_sesion
sensibilidad_adaptacion
velocidad_progresion
Perfil Cognitivo

Representa el estado dinámico del usuario.

Atributos principales:

nivel_global
nivel_memoria
nivel_logica
nivel_atencion
precision_promedio
tiempo_respuesta_promedio
estabilidad
tendencia
Agregado Sesión de Entrenamiento

Representa una ejecución concreta del sistema adaptativo.

Entidades
SesionEntrenamiento

Atributos principales:

id_sesion
fecha_inicio
fecha_fin
estado
dificultad_actual
InstanciaEjercicio

Representa un ejercicio generado para una sesión.

Atributos principales:

id_instancia
enunciado
dificultad_efectiva
timestamp_generacion
Evento

Representa un hecho ocurrido dentro del sistema.

Atributos principales:

id_evento
tipo_evento
timestamp
datos_entrada
resultado_evaluacion
Metrica

Información derivada del desempeño.

Atributos principales:

precision
tiempo_respuesta
impacto_nivel
variacion_dificultad
Agregado Ejercicio
Entidades
PlantillaEjercicio

Define la estructura reutilizable del ejercicio.

Atributos principales:

id_plantilla
tipo_cognitivo
dificultad_base
reglas_generacion
modelo_solucion
semilla
Servicios de Dominio
MotorAdaptacion
GeneradorEjercicios
EvaluadorRespuestas
Objetos de Valor
Tipo Cognitivo

Valores permitidos:

memoria
logica
atencion
Estado Sesion

Valores permitidos:

activa
pausada
finalizada
Estado Cuenta

Valores permitidos:

activa
inactiva
bloqueada