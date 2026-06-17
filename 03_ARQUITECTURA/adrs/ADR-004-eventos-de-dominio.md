ADR-004: Registro de Eventos de Dominio
Estado

Aceptado

Contexto

El Sistema de Entrenamiento Cognitivo Adaptativo necesita preservar información detallada sobre las interacciones realizadas durante las sesiones de entrenamiento.

La evaluación del rendimiento y la adaptación de la dificultad dependen de información histórica derivada de dichas interacciones.

Se requiere un mecanismo que permita mantener trazabilidad y posibilite futuras capacidades analíticas.

Decisión

Se registrarán eventos relevantes del dominio como unidades inmutables de información.

Los eventos representarán acciones y resultados significativos ocurridos durante la ejecución del sistema.

Eventos previstos
inicio_sesion
ejercicio_generado
respuesta_usuario
evaluacion_respuesta
ajuste_dificultad
fin_sesion
Justificación

El registro de eventos permite:

reconstruir la secuencia completa de una sesión
mantener trazabilidad del comportamiento del sistema
calcular métricas derivadas
facilitar auditoría y análisis posterior
preparar la arquitectura para futuras extensiones analíticas
Consecuencias
Positivas
mayor observabilidad
mejor capacidad de análisis
independencia entre eventos y métricas derivadas
posibilidad de reconstrucción histórica
Negativas
incremento del volumen de información almacenada
mayor complejidad respecto a un enfoque puramente basado en estados
Alternativas consideradas
Almacenar únicamente el estado final

Ventaja:

menor complejidad.

Desventaja:

pérdida de trazabilidad y dificultad para reconstruir sesiones.
Event Sourcing completo

Ventaja:

máxima trazabilidad.

Desventaja:

complejidad excesiva para un proyecto académico.
Decisión final

Se adopta un enfoque de registro de eventos del dominio como mecanismo de trazabilidad, sin implementar Event Sourcing completo.