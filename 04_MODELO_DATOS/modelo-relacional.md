Modelo Relacional
Propósito

Definir las relaciones del modelo de datos en términos relacionales, preparando la futura implementación en SQLite mediante SQLAlchemy.

USUARIO
Clave primaria
id_usuario
Atributos
fecha_creacion
estado_cuenta
idioma
preferencias_sesion
sensibilidad_adaptacion
velocidad_progresion
PERFIL_COGNITIVO
Clave primaria
id_perfil
Clave foránea
id_usuario → USUARIO(id_usuario)
Atributos
nivel_global
nivel_memoria
nivel_logica
nivel_atencion
precision_promedio
tiempo_respuesta_promedio
estabilidad
tendencia
SESION_ENTRENAMIENTO
Clave primaria
id_sesion
Clave foránea
id_usuario → USUARIO(id_usuario)
Atributos
fecha_inicio
fecha_fin
estado
dificultad_actual
PLANTILLA_EJERCICIO
Clave primaria
id_plantilla
Atributos
tipo_cognitivo
dificultad_base
reglas_generacion
modelo_solucion
semilla
INSTANCIA_EJERCICIO
Clave primaria
id_instancia
Claves foráneas
id_sesion → SESION_ENTRENAMIENTO(id_sesion)
id_plantilla → PLANTILLA_EJERCICIO(id_plantilla)
Atributos
enunciado
dificultad_efectiva
timestamp_generacion
EVENTO
Clave primaria
id_evento
Clave foránea
id_sesion → SESION_ENTRENAMIENTO(id_sesion)
Atributos
tipo_evento
timestamp
datos_entrada
resultado_evaluacion
METRICA
Clave primaria
id_metrica
Clave foránea
id_sesion → SESION_ENTRENAMIENTO(id_sesion)
Atributos
precision
tiempo_respuesta
impacto_nivel
variacion_dificultad
Relaciones globales
USUARIO
│
├── PERFIL_COGNITIVO
│
└── SESION_ENTRENAMIENTO
        │
        ├── INSTANCIA_EJERCICIO
        │         │
        │         └── PLANTILLA_EJERCICIO
        │
        ├── EVENTO
        │
        └── METRICA
Cardinalidades
USUARIO (1) -------- (1) PERFIL_COGNITIVO

USUARIO (1) -------- (N) SESION_ENTRENAMIENTO

SESION_ENTRENAMIENTO (1) -------- (N) INSTANCIA_EJERCICIO

PLANTILLA_EJERCICIO (1) -------- (N) INSTANCIA_EJERCICIO

SESION_ENTRENAMIENTO (1) -------- (N) EVENTO

SESION_ENTRENAMIENTO (1) -------- (N) METRICA
Forma Normal

El modelo se encuentra diseñado para cumplir:

Primera Forma Normal (1FN)
Segunda Forma Normal (2FN)
Tercera Forma Normal (3FN)

El objetivo es minimizar redundancias y asegurar consistencia en los datos.

Principios de diseño aplicados:
alta cohesión
bajo acoplamiento
integridad referencial
trazabilidad mediante eventos
persistencia longitudinal del aprendizaje