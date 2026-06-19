Esquema Lógico
Propósito

Definir las entidades persistentes y sus relaciones mediante claves primarias y foráneas.

Usuario
Clave primaria
id_usuario
Relaciones
1 Perfil Cognitivo
N Sesiones de Entrenamiento
Perfil Cognitivo
Clave primaria
id_perfil
Claves foráneas
id_usuario → Usuario
Relación
pertenece a un único Usuario
Sesión de Entrenamiento
Clave primaria
id_sesion
Claves foráneas
id_usuario → Usuario
Relaciones
N Instancias de Ejercicio
N Eventos
N Métricas
Plantilla de Ejercicio
Clave primaria
id_plantilla
Relaciones
N Instancias de Ejercicio
Instancia de Ejercicio
Clave primaria
id_instancia
Claves foráneas
id_sesion → SesionEntrenamiento
id_plantilla → PlantillaEjercicio
Evento
Clave primaria
id_evento
Claves foráneas
id_sesion → SesionEntrenamiento
Métrica
Clave primaria
id_metrica
Claves foráneas
id_sesion → SesionEntrenamiento
Relaciones globales
Usuario
│
├── Perfil Cognitivo
│
└── SesionEntrenamiento
        │
        ├── InstanciaEjercicio
        │         │
        │         └── PlantillaEjercicio
        │
        ├── Evento
        │
        └── Metrica
Integridad referencial

Las relaciones entre entidades deberán mantenerse mediante claves foráneas.

No podrán existir:

perfiles sin usuario
sesiones sin usuario
ejercicios sin sesión
eventos sin sesión
métricas sin sesión
Principios de diseño
minimizar redundancia
mantener consistencia referencial
favorecer trazabilidad
permitir evolución futura