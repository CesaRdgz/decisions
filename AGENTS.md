# Instrucciones para cualquier IA que trabaje en este repositorio

Este archivo lo leen Claude, Gemini y cualquier otro asistente. `CLAUDE.md` y `GEMINI.md` solo apuntan aquí.

## Antes de empezar cualquier tarea (obligatorio)

Trabajamos dos personas en paralelo. Antes de tocar nada:

1. `git fetch origin`
2. Si hay cambios nuevos en el remoto, bajarlos: `git pull --rebase`
3. Si hay cambios locales sin subir que entran en conflicto, **parar y avisar** antes de resolver nada.

Al terminar: commit pequeño y descriptivo, `git pull --rebase` otra vez y `git push`.

## Fuente de verdad

- Diseño del juego: `docs/GDD.md` (copia del documento maestro de diseño). Leerlo antes de proponer diseño o código.
- Toda idea nueva que no se use todavía va a la sección **Brainstorming** del GDD.
- Toda decisión técnica se apunta en `docs/decisiones/` (una nota corta por decisión).

## Estructura

| Carpeta | Contenido |
| --- | --- |
| `story/` | Historias en Ink (`.ink`) |
| `src/engine/` | Reglas puras en TypeScript: tiempo, combate, economía. Sin dependencias de Angular. |
| `src/app/` | UI Angular + Ionic + Capacitor |
| `docs/` | GDD, convenciones y decisiones |

## Reglas

- Una rama por tarea: `feature/<tarea>`. Nada directo a `main` salvo documentación.
- Los temporizadores usan siempre la hora del servidor, nunca la del móvil.
- La lógica de combate y aleatoriedad usa semilla guardada (reproducible y validable en servidor).
- Gestor de paquetes: pnpm.
