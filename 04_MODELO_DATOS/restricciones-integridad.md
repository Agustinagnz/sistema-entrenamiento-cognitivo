Restricciones de Integridad
Propósito

Definir las reglas de integridad del modelo de datos del Sistema de Entrenamiento Cognitivo Adaptativo.

Restricciones NOT NULL
Usuario

Obligatorios:

id_usuario
fecha_creacion
estado_cuenta
Perfil Cognitivo

Obligatorios:

id_perfil
id_usuario
nivel_global
SesionEntrenamiento

Obligatorios:

id_sesion
id_usuario
fecha_inicio
estado
PlantillaEjercicio

Obligatorios:

id_plantilla
tipo_cognitivo
dificultad_base
InstanciaEjercicio

Obligatorios:

id_instancia
id_sesion
id_plantilla
dificultad_efectiva
Evento

Obligatorios:

id_evento
id_sesion
tipo_evento
timestamp
Metrica

Obligatorios:

id_metrica
id_sesion
precision
tiempo_respuesta
Restricciones UNIQUE
Usuario
id_usuario
Perfil Cognitivo
id_perfil
id_usuario

Un usuario posee un único perfil cognitivo.

SesionEntrenamiento
id_sesion
PlantillaEjercicio
id_plantilla
InstanciaEjercicio
id_instancia
Evento
id_evento
Metrica
id_metrica
Restricciones CHECK
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
Precisión

Debe encontrarse entre:

0 ≤ precision ≤ 100
Dificultad

Debe ser positiva.

dificultad_base > 0
dificultad_efectiva > 0
Tiempo de respuesta

Debe ser mayor que cero.

tiempo_respuesta > 0
Valores por defecto (DEFAULT)
Usuario

estado_cuenta:

activa

fecha_creacion:

fecha actual

SesionEntrenamiento

estado:

activa
Perfil Cognitivo

nivel_global:

1
Integridad Referencial

Se deberá garantizar:

PerfilCognitivo.id_usuario
          ↓
Usuario.id_usuario
SesionEntrenamiento.id_usuario
          ↓
Usuario.id_usuario
InstanciaEjercicio.id_sesion
          ↓
SesionEntrenamiento.id_sesion
InstanciaEjercicio.id_plantilla
          ↓
PlantillaEjercicio.id_plantilla
Evento.id_sesion
          ↓
SesionEntrenamiento.id_sesion
Metrica.id_sesion
          ↓
SesionEntrenamiento.id_sesion

Principios aplicados:
consistencia de datos
integridad referencial
prevención de estados inválidos
minimización de errores de persistencia