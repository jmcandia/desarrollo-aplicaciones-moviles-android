# CONTEXT.md

## 1. Propósito
Sitio web estático del libro online sobre Kotlin y Android moderno (Jetpack Compose, Room, offline-first) para desarrolladores Java. Emplea el caso didáctico ParkFlow como hilo conductor educativo (sin implementar app funcional ejecutable).

## 2. Arquitectura del Repositorio
```text
.
├── docs/                                  # Fuente Markdown del libro
│   ├── unidad-1-kotlin/                   # Kotlin puro consola/JVM (sin dependencias Android)
│   ├── unidad-2-android/                  # Android, Compose, Room, MVVM, validación PPU
│   ├── unidad-3-integracion-y-distribucion/# Servicios gestionados, sync, testing, release
│   ├── apendices/                         # POO, SOLID, KISS/DRY
│   └── assets/                            # Estilos CSS, scripts JS e imágenes
├── .github/workflows/deploy-docs.yaml     # CI/CD: build estricto y deploy a GitHub Pages
├── mkdocs.yml                             # Contrato canónico de navegación y extensiones
└── requirements.txt                       # Dependencias mínimas Python (MkDocs Material)
```

## 3. Core Tech Stack
- **Generador & Documentación:** MkDocs, Material for MkDocs, PyMdown Extensions, Mermaid.js.
- **Entorno de compilación:** Python 3 (venv).
- **Dominio técnico enseñado:** Kotlin (JVM), Jetpack Compose, Material 3, AndroidX Room, DataStore, Coroutines/Flow, Navigation Compose.

## 4. Índice de Documentación
- [`CLAUDE.md`](CLAUDE.md): Comandos operativos y directrices técnicas.
- [`AGENTS.md`](AGENTS.md): Contrato editorial y especificación didáctica.
- [`CHANGELOG.md`](CHANGELOG.md): Historial de versiones y cambios.
