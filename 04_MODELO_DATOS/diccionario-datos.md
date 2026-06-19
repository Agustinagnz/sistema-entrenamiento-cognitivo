Diccionario de Datos
Propósito

Definir los atributos del modelo de datos y describir su significado dentro del dominio.

USUARIO
Atributo	Descripción
id_usuario	Identificador único del usuario
fecha_creacion	Fecha de alta en el sistema
estado_cuenta	Estado actual de la cuenta
idioma	Idioma preferido
preferencias_sesion	Configuración de sesión
sensibilidad_adaptacion	Intensidad con que cambia la dificultad
velocidad_progresion	Ritmo de progresión configurado
PERFIL_COGNITIVO
Atributo	Descripción
id_perfil	Identificador del perfil
id_usuario	Usuario propietario
nivel_global	Nivel cognitivo general
nivel_memoria	Nivel estimado en memoria
nivel_logica	Nivel estimado en lógica
nivel_atencion	Nivel estimado en atención
precision_promedio	Precisión promedio histórica
tiempo_respuesta_promedio	Tiempo medio de respuesta
estabilidad	Variabilidad del desempeño
tendencia	Evolución del rendimiento
SESION_ENTRENAMIENTO
Atributo	Descripción
id_sesion	Identificador de la sesión
id_usuario	Usuario que ejecuta la sesión
fecha_inicio	Momento de inicio
fecha_fin	Momento de finalización
estado	Estado actual de la sesión
dificultad_actual	Nivel de dificultad vigente
PLANTILLA_EJERCICIO
Atributo	Descripción
id_plantilla	Identificador de la plantilla
tipo_cognitivo	Dominio cognitivo asociado
dificultad_base	Nivel inicial de dificultad
reglas_generacion	Parámetros para generar ejercicios
modelo_solucion	Regla de validación
semilla	Valor utilizado para reproducibilidad
INSTANCIA_EJERCICIO
Atributo	Descripción
id_instancia	Identificador del ejercicio generado
id_sesion	Sesión asociada
id_plantilla	Plantilla utilizada
enunciado	Ejercicio concreto presentado
dificultad_efectiva	Dificultad aplicada
timestamp_generacion	Fecha y hora de generación
EVENTO
Atributo	Descripción
id_evento	Identificador del evento
id_sesion	Sesión asociada
tipo_evento	Tipo de evento registrado
timestamp	Fecha y hora del evento
datos_entrada	Información recibida
resultado_evaluacion	Resultado obtenido
METRICA
Atributo	Descripción
id_metrica	Identificador de la métrica
id_sesion	Sesión asociada
precision	Exactitud obtenida
tiempo_respuesta	Tiempo empleado
impacto_nivel	Variación sobre el nivel del usuario
variacion_dificultad	Cambio aplicado a la dificultad
Enumeraciones del dominio
EstadoCuenta

Valores permitidos:

activa
inactiva
bloqueada
EstadoSesion

Valores permitidos:

activa
pausada
finalizada
TipoCognitivo

Valores permitidos:

memoria
logica
atencion