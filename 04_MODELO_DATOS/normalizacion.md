Normalización del Modelo de Datos
Propósito

Justificar la estructura del modelo relacional y verificar el cumplimiento de las formas normales para minimizar redundancias y mantener la integridad de los datos.

Primera Forma Normal (1FN)

La Primera Forma Normal establece que:

cada atributo debe contener valores atómicos;
no deben existir grupos repetidos;
cada fila debe ser identificable de forma única.
Aplicación al sistema

Todas las entidades poseen una clave primaria:

USUARIO(id_usuario)
PERFIL_COGNITIVO(id_perfil)
SESION_ENTRENAMIENTO(id_sesion)
PLANTILLA_EJERCICIO(id_plantilla)
INSTANCIA_EJERCICIO(id_instancia)
EVENTO(id_evento)
METRICA(id_metrica)

Todos los atributos almacenan valores simples.

Por lo tanto, el modelo cumple la Primera Forma Normal.

Segunda Forma Normal (2FN)

La Segunda Forma Normal establece que:

debe cumplirse la 1FN;
todos los atributos no clave deben depender completamente de la clave primaria.
Aplicación al sistema

Los atributos de cada entidad dependen exclusivamente de su clave primaria.

Ejemplo:

USUARIO

id_usuario → fecha_creacion, estado_cuenta, idioma, preferencias_sesion, sensibilidad_adaptacion, velocidad_progresion

PERFIL_COGNITIVO

id_perfil → nivel_global, nivel_memoria, nivel_logica, nivel_atencion, precision_promedio, tiempo_respuesta_promedio, estabilidad, tendencia

No existen dependencias parciales.

Por lo tanto, el modelo cumple la Segunda Forma Normal.

Tercera Forma Normal (3FN)

La Tercera Forma Normal establece que:

debe cumplirse la 2FN;
los atributos no clave no deben depender de otros atributos no clave.
Aplicación al sistema

Las entidades almacenan información propia y específica.

Ejemplo:

los datos del usuario se encuentran en USUARIO;
la evolución del rendimiento se encuentra en PERFIL_COGNITIVO;
las sesiones se almacenan en SESION_ENTRENAMIENTO;
los eventos se almacenan en EVENTO;
las métricas se almacenan en METRICA.

No existen dependencias transitivas significativas.

Por lo tanto, el modelo cumple la Tercera Forma Normal.

Beneficios obtenidos

La normalización permite:

reducir redundancia;
evitar anomalías de inserción;
evitar anomalías de actualización;
evitar anomalías de eliminación;
mejorar la consistencia de los datos;
facilitar la evolución futura del sistema.
Compromisos asumidos

La normalización incrementa la cantidad de relaciones entre tablas, pero proporciona:

mayor integridad;
menor duplicación de información;
mejor mantenibilidad.
Conclusión

El modelo de datos del Sistema de Entrenamiento Cognitivo Adaptativo se encuentra diseñado para cumplir:

Primera Forma Normal (1FN);
Segunda Forma Normal (2FN);
Tercera Forma Normal (3FN).

La estructura obtenida favorece la consistencia, la trazabilidad y la evolución futura del sistema.