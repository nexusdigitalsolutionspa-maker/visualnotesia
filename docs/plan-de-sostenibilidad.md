# Entrega 3 · Plan de evolución y sostenibilidad — VisualNotes AI

> La continuidad no puede depender de una sola persona. Los nombres se completan con el equipo; si alguien no autoriza aparecer, se usa su rol.

## Responsabilidades compartidas

| Tarea | Responsable actual | Suplente | Rotación |
|---|---|---|---|
| Facilitar el Show & Tell | `[nombre o rol]` | `[nombre o rol]` | Cada 2 sesiones |
| Documentar la activación en la bitácora | `[nombre o rol]` | `[nombre o rol]` | Cada activación |
| Dar la bienvenida a personas nuevas | `[nombre o rol]` | `[nombre o rol]` | Cada 2 semanas |
| Revisar Issues y PRs entrantes | `[nombre o rol]` | `[nombre o rol]` | Cada semana |
| Mantener los recursos actualizados | `[nombre o rol]` | `[nombre o rol]` | Cada mes |

**Regla de rotación:** al terminar cada ciclo, la persona responsable pasa el rol a su suplente y deja constancia en un comentario del Issue de seguimiento. Nadie acumula dos roles críticos a la vez.

## Próximos rituales

| Fecha propuesta | Ritual | Objetivo | Responsable |
|---|---|---|---|
| 2026-11-26 | Show & Tell de 30 min | Mostrar un kit generado por una persona que no sea del núcleo | `[completar]` |
| 2026-12-10 | Revisión de recursos | Actualizar la guía y la plantilla con lo aprendido | `[completar]` |
| 2027-01-15 | Sesión de bienvenida | Recibir a estudiantes del siguiente ciclo | `[completar]` |

> Fechas propuestas: confírmalas con el equipo y registra lo que realmente ocurra en la [bitácora](bitacora.md).

## Cómo recibir a nuevos miembros

1. Leer el [README](../README.md): propósito, qué genera la app y cómo empezar.
2. Elegir un camino de entrada según la [escalera de participación](../CONTRIBUTING.md#escalera-de-participación).
3. Seguir la [guía rápida](../recursos/guia-de-uso-rapida.md) y generar un kit de prueba.
4. Copiar la [plantilla de kit de estudio](../recursos/plantilla-kit-de-estudio.md), revisarla y compartirla en un PR.
5. Presentarse en un Issue de bienvenida con qué quiere probar y en qué tema puede ayudar.

**Tiempo esperado hasta la primera contribución:** menos de 30 minutos para probar; menos de una sesión para enviar un primer recurso.

## Señales reales de comunidad

| Señal real | Cómo la observaremos | No confundir con |
|---|---|---|
| Recurrencia | La misma persona vuelve a segunda sesión o abre un segundo Issue | Número total de visitas |
| Ayuda entre pares | Una persona responde a otra en un Issue sin intervención del núcleo | Cantidad de mensajes |
| Facilitación distribuida | Sesiones dirigidas por alguien que no es del Grupo 4 | Que el repo tenga muchos colaboradores |
| Reutilización | Un recurso se copia y se adapta en otro fork o curso | Stars, forks o descargas sin uso |

**Métricas de vanidad** (se reportan, pero no se usan como evidencia de comunidad): `stars`, `forks`, visitas, descargas y seguidores.

## Cómo copiar o continuar la comunidad

1. Hacer **fork** del repositorio y mantener la licencia MIT ([LICENSE](../LICENSE)).
2. Seguir la [guía rápida](../recursos/guia-de-uso-rapida.md): `cp .env.example .env`, configurar `GEMINI_API_KEY` y levantar con Docker o Uvicorn.
3. Conservar `docs/` y `recursos/`: ahí está el conocimiento, no solo el código.
4. Cambiar los nombres de las personas responsables en este archivo y en el README.
5. Abrir un Issue de bienvenida en el nuevo repositorio y repetir el primer ritual con el cronograma de arriba.

**Condición mínima para continuar:** que otra persona pueda generar un kit y compartirlo sin pedirnos acceso, explicación o permiso.

---

Relacionado: [Mapa de Comunidad](mapa-de-comunidad.md) · [Bitácora](bitacora.md) · [Retroalimentación](retroalimentacion.md).
