Diagrama C4 - Nivel 2: Contenedores
Propósito

Este diagrama describe los principales contenedores del Sistema de Entrenamiento Cognitivo Adaptativo y las relaciones existentes entre ellos.

Contenedor 1: API REST
Tecnología

FastAPI

Responsabilidad

Exponer los casos de uso del sistema mediante endpoints HTTP.

Funciones principales
recibir solicitudes de los usuarios
validar datos de entrada
invocar los casos de uso de la aplicación
devolver respuestas
Contenedor 2: Aplicación
Responsabilidad

Orquestar los procesos del sistema y coordinar la ejecución de los casos de uso.

Funciones principales
iniciar sesiones
procesar respuestas
finalizar sesiones
consultar progreso
coordinar la adaptación dinámica
Contenedor 3: Dominio
Responsabilidad

Contener las reglas de negocio y el modelo central del sistema.

Elementos principales
Usuario
Perfil Cognitivo
Sesión de Entrenamiento
Plantilla de Ejercicio
Instancia de Ejercicio
Evento
Motor de Adaptación
Métricas
Contenedor 4: Persistencia
Tecnología

SQLite

Responsabilidad

Almacenar la información necesaria para garantizar continuidad y trazabilidad.

Información almacenada
usuarios
perfiles cognitivos
sesiones
ejercicios
eventos
métricas
Relaciones entre contenedores
Usuario
   │
   ▼
API REST (FastAPI)
   │
   ▼
Aplicación
   │
   ▼
Dominio
   │
   ▼
Persistencia (SQLite)
Principios arquitectónicos
separación entre dominio e infraestructura
bajo acoplamiento
alta cohesión
posibilidad de sustituir la persistencia sin modificar las reglas de negocio
independencia de la interfaz de usuario