# Bifröst Learning Path

**Puente entre la academia y la industria tecnológica.**

Bifröst Learning Path es un programa de orientación académica diseñado para estudiantes de informática — tanto universitarios como de formación técnico-profesional (TP) — que busca reducir el desenfoque en el aprendizaje mediante una ruta formativa clara y estructurada.

## Motivación

Los estudiantes de informática a menudo enfrentan dificultades para conectar los contenidos de las asignaturas con su aplicación en el mundo real. Esta desconexión genera desmotivación, bajo rendimiento y, en muchos casos, deserción.

## Objetivo

Bifröst conecta los contenidos de cada asignatura con las competencias profesionales y las demandas de la industria tecnológica, ayudando a los estudiantes a comprender **qué aprender**, **por qué es importante** y **cómo aplicarlo** en proyectos reales.

## Componentes

- **Diagnósticos** — Evaluación inicial y continua del nivel del estudiante.
- **Material educativo** — Recursos curados alineados con la industria.
- **Mentorías** — Acompañamiento personalizado por profesionales del sector.
- **Talleres prácticos** — Experiencias hands-on con tecnologías actuales.
- **Guía de aprendizaje** — Ruta formativa clara y adaptativa.

## Impacto esperado

- Aumentar la motivación y el rendimiento académico.
- Disminuir la deserción universitaria.
- Facilitar la transición desde la formación académica hacia el mundo laboral.

## Stack tecnológico

| Capa | Tecnología |
|------|-----------|
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original.svg" width="20" height="20"> Web | Next.js + <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg" width="20" height="20"> Tailwind CSS |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" width="20" height="20"> Backend | Python (<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original.svg" width="20" height="20"> FastAPI) |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/flutter/flutter-original.svg" width="20" height="20"> Mobile | Flutter + <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/dart/dart-original.svg" width="20" height="20"> Dart (Android Studio) |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" width="20" height="20"> Base de datos | PostgreSQL |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original.svg" width="20" height="20"> Cache | Redis |

## Clean Architecture

El proyecto sigue los principios de **Clean Architecture** para mantener el código desacoplado, testeable y sostenible. La regla fundamental es que las dependencias apuntan **hacia adentro**: el centro (`domain`) no sabe nada de lo exterior.

```
        ┌─────────────────────────┐
        │      PRESENTATION       │  Interfaz con el usuario (API, UI)
        │ ─────────────────────── │
        │    INFRASTRUCTURE       │  Implementaciones concretas (DB, Redis, HTTP)
        │ ─────────────────────── │
        │     APPLICATION         │  Casos de uso, orquestación
        │ ─────────────────────── │
        │       DOMAIN            │  Entidades, reglas de negocio, interfaces
        └─────────────────────────┘
```

### Capas

**Domain** — El núcleo de la aplicación. Contiene entidades, value objects y las interfaces de repositorio. No tiene dependencias externas.

**Application** — Casos de uso que orquestan el flujo de la aplicación. Depende solo de `domain`.

**Infrastructure** — Implementa las interfaces definidas en `domain`. Conexión a PostgreSQL, Redis, clientes HTTP, etc.

**Presentation** — Expone la funcionalidad al exterior. En `backend` son las rutas de la API. En `web` y `mobile` son los componentes y pantallas.

### Estructura

```
bifrost-turing-path/
├── backend/                    # Python (FastAPI)
│   ├── domain/                 # Entidades, value objects, interfaces de repositorio
│   ├── application/            # Casos de uso, DTOs, puertos
│   ├── infrastructure/         # Implementaciones concretas (DB, Redis, APIs externas)
│   ├── presentation/           # Controladores/rutas de la API
│   └── main.py
├── web/                        # Next.js + Tailwind
│   ├── domain/                 # Modelos, interfaces
│   ├── application/            # Hooks, servicios de estado
│   ├── infrastructure/         # Cliente API, repositorios
│   ├── presentation/           # Componentes, páginas
│   └── package.json
├── mobile/                     # Flutter + Dart
│   ├── lib/
│   │   ├── domain/             # Entidades, interfaces de repositorio
│   │   ├── data/               # Implementaciones de repositorio, fuentes de datos
│   │   └── presentation/       # Bloc/Cubit, screens, widgets
│   ├── android/
│   ├── ios/
│   └── pubspec.yaml
├── docker-compose.yml          # PostgreSQL + Redis
└── README.md
```

## Licencia

MIT
