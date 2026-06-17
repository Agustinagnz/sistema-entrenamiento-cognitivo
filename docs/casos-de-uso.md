# Casos de Uso

## Introducción

Los casos de uso describen las interacciones principales entre los actores y el Sistema de Entrenamiento Cognitivo Adaptativo.

---

# CU-01. Iniciar sesión de entrenamiento

## Actor principal

Usuario Final

## Descripción

Permite al usuario iniciar una sesión de entrenamiento cognitivo.

## Precondiciones

* El usuario debe existir en el sistema.

## Flujo principal

1. El usuario solicita iniciar una sesión.
2. El sistema recupera el perfil cognitivo del usuario.
3. El sistema inicializa la sesión.
4. El sistema genera el primer ejercicio.
5. La sesión queda activa.

## Postcondiciones

* Existe una sesión activa asociada al usuario.

---

# CU-02. Resolver ejercicio

## Actor principal

Usuario Final

## Descripción

Permite al usuario responder un ejercicio generado por el sistema.

## Precondiciones

* Debe existir una sesión activa.
* Debe existir un ejercicio disponible.

## Flujo principal

1. El sistema presenta el ejercicio.
2. El usuario envía una respuesta.
3. El sistema registra el tiempo de respuesta.
4. El sistema evalúa la respuesta.
5. El sistema genera métricas de desempeño.
6. El motor de adaptación determina la dificultad siguiente.
7. El sistema genera un nuevo ejercicio.

## Postcondiciones

* El desempeño queda registrado.
* La dificultad puede modificarse.

---

# CU-03. Finalizar sesión

## Actor principal

Usuario Final

## Descripción

Permite concluir una sesión de entrenamiento.

## Precondiciones

* Debe existir una sesión activa.

## Flujo principal

1. El usuario solicita finalizar la sesión.
2. El sistema consolida las métricas obtenidas.
3. El sistema actualiza el perfil cognitivo.
4. El sistema registra los eventos finales.
5. La sesión se marca como finalizada.

## Postcondiciones

* La sesión queda almacenada en el historial.

---

# CU-04. Consultar progreso histórico

## Actor principal

Usuario Final

## Descripción

Permite visualizar la evolución del rendimiento del usuario.

## Precondiciones

* El usuario debe poseer sesiones registradas.

## Flujo principal

1. El usuario solicita consultar su historial.
2. El sistema recupera las sesiones previas.
3. El sistema muestra las métricas disponibles.

## Postcondiciones

* El usuario puede analizar su evolución.

---

# CU-05. Administrar usuarios

## Actor principal

Administrador del Sistema

## Descripción

Permite gestionar usuarios registrados.

## Flujo principal

1. El administrador consulta usuarios.
2. El administrador crea, modifica o desactiva usuarios.
3. El sistema almacena los cambios realizados.

## Postcondiciones

* La información de los usuarios queda actualizada.

---

# CU-06. Configurar parámetros globales

## Actor principal

Administrador del Sistema

## Descripción

Permite modificar parámetros generales del sistema.

## Flujo principal

1. El administrador accede a la configuración.
2. El administrador modifica los parámetros.
3. El sistema guarda los cambios.

## Postcondiciones

* Los nuevos parámetros quedan disponibles para futuras sesiones.
