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
| Web | Next.js + Tailwind CSS |
| Backend | Python (FastAPI) |
| Mobile | Flutter + Dart (Android Studio) |
| Base de datos | PostgreSQL |
| Cache | Redis |

## Estructura del proyecto (Clean Architecture)

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
