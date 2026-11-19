# Entrega 1 · Mapa de Comunidad — VisualNotes AI

> Estado: propuesta construida a partir del Reto 1 y del código del repositorio.
> Los campos marcados `[validar con el equipo]` deben confirmarse antes de entregar.

## Dominio

**Práctica compartida:** convertir material de clase (audios, fotos de pizarra y texto) en kits de estudio reutilizables con ayuda de IA, y compartirlos para que otras personas puedan repasar sin depender de la grabación original.

**Necesidad real atendida:** en el curso, los apuntes quedan dispersos entre grabaciones, fotos y documentos. Una persona que se quedó con dudas, se perdió una clase o quiere repasar en su propio ritmo no tiene un punto de partida ordenado. El kit de estudio reduce esa fricción y puede pasar de una persona a otra.

**Límite del dominio:** la comunidad no se define por la herramienta (`visualnotesia`), sino por la práctica de producir, revisar y compartir esos kits. La herramienta es el soporte, no el fin.

## Intención, función y prueba

> Queremos crear **una comunidad de estudiantes y docentes que producen, revisan y comparten kits de estudio generados a partir de material de clase**, para que **cualquier estudiante pueda repasar un tema y reutilizar el trabajo de otra persona** pueda **hacerlo sin necesitar la grabación original ni pedirle permiso a quien generó el apunte**.

**Prueba concreta:** una persona nueva clona el repo, sigue la [guía rápida](../recursos/guia-de-uso-rapida.md), genera un kit con una fuente propia, lo revisa y lo propone como recurso mediante un Pull Request. Si puede hacerlo sin preguntarnos, la infraestructura funciona.

## Participantes

| Grupo | Quiénes son | Qué buscan | Qué aportan |
|---|---|---|---|
| **Núcleo** | Grupo 4 — Universidad Cenfotec `[validar nombres y roles]` | Que la práctica continúe después del curso | Código, documentación, decisiones de diseño y apertura de los primeros Issues |
| **Activos** | Compañeros de clase que probaron la app `[validar]` | Kits listos para repasar y un lugar donde reportar fallos | Pruebas reales, reportes de errores, mejoras a la documentación |
| **Periféricos** | Estudiantes que descargan o leen los recursos | Apuntes y quizzes sin tener que generarlos desde cero | Reutilización, comentarios breves, señales de qué recurso sirve |
| **Externos** | Docentes, otros grupos y personas que lleguen por GitHub `[validar]` | Adaptar la práctica a sus propios cursos | Forks, nuevos recursos, mirada outside del proyecto |

> Nota: reemplazar los marcadores por nombres reales solo si las personas autorizaron aparecer. La guía del proyecto pide evitar datos personales no autorizados.

## Trayectorias de participación

| Nivel | Acción concreta en este repositorio | Qué cambia para la persona |
|---|---|---|
| 1. Observar | Leer el [README](../README.md) y los [recursos](../recursos/) | Entiende para qué sirve la comunidad |
| 2. Probar | Ejecutar la app con Docker o local y generar un kit propio | Pasa de lector a usuario |
| 3. Contribuir | Abrir un Issue con un error o enviar un PR con un recurso | Deja de consumir y empieza a aportar |
| 4. Facilitar | Dar la bienvenida, revisar PRs y coordinar una sesión | Sostiene la comunidad sin el núcleo original |

La [escalera de participación](../CONTRIBUTING.md#escalera-de-participación) explica cada paso. Cada nivel tiene una acción mínima, para que nadie tenga que adivinar cómo empezar.

## Rituales y espacios

| Ritual | Frecuencia propuesta | Espacio | Estado |
|---|---|---|---|
| Show & Tell de 30 minutos: alguien muestra un kit y cuenta qué ajustó | Quincenal `[validar]` | Sala del curso / videollamada | Propuesto |
| Revisión de Issues y PRs nuevos | Semanal `[validar]` | Pestaña Issues / Pull requests de GitHub | Propuesto |
| Actualización de la bitácora | Después de cada activación | [docs/bitacora.md](bitacora.md) | Propuesto |

> Estos rituales son una propuesta de diseño. No se registran como ejecutados hasta que exista evidencia real en la [bitácora](bitacora.md).

## Cómo se conecta con el resto del repositorio

- [Mapa de Comunidad](mapa-de-comunidad.md) — esta entrega.
- [Recursos reutilizables](../recursos/) — Entrega 2.
- [Plan de evolución y sostenibilidad](plan-de-sostenibilidad.md) — Entrega 3.
- [Bitácora de activación](bitacora.md) — evidencia real.
- [Retroalimentación](retroalimentacion.md) y [uso de IA](uso-de-ia.md) — transparencia.
