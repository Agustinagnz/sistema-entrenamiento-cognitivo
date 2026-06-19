Modelo Entidad-Relación
Propósito

Definir las entidades principales y las relaciones del Sistema de Entrenamiento Cognitivo Adaptativo.

Entidades
Usuario

Representa al entrenante del sistema.

Perfil Cognitivo

Almacena la evolución del rendimiento del usuario.

Sesión de Entrenamiento

Representa una ejecución concreta del proceso adaptativo.

Instancia de Ejercicio

Representa un ejercicio generado durante una sesión.

Plantilla de Ejercicio

Define las reglas de generación y evaluación.

Evento

Representa un hecho ocurrido durante una sesión.

Métrica

Representa información derivada del desempeño.

Relaciones
Usuario — Perfil Cognitivo

Cardinalidad:

Usuario (1) -------- (1) Perfil Cognitivo

Un usuario posee un único perfil cognitivo.

Usuario — Sesión de Entrenamiento

Cardinalidad:

Usuario (1) -------- (N) Sesión de Entrenamiento

Un usuario puede realizar múltiples sesiones.

Sesión de Entrenamiento — Instancia de Ejercicio

Cardinalidad:

Sesión de Entrenamiento (1) -------- (N) Instancia de Ejercicio

Una sesión genera múltiples ejercicios.

Plantilla de Ejercicio — Instancia de Ejercicio

Cardinalidad:

Plantilla de Ejercicio (1) -------- (N) Instancia de Ejercicio

Una plantilla puede producir muchas instancias.

Sesión de Entrenamiento — Evento

Cardinalidad:

Sesión de Entrenamiento (1) -------- (N) Evento

Una sesión genera múltiples eventos.

Sesión de Entrenamiento — Métrica

Cardinalidad:

Sesión de Entrenamiento (1) -------- (N) Métrica

Una sesión produce múltiples métricas.

Vista global
Usuario
│
├── Perfil Cognitivo
│
└── Sesión de Entrenamiento
      │
      ├── Instancia de Ejercicio
      │        │
      │        └── Plantilla de Ejercicio
      │
      ├── Evento
      │
      └── Métrica
Principios de diseño
separación entre entidades y métricas derivadas
trazabilidad mediante eventos
persistencia longitudinal del usuario
independencia entre agregados