# Desarrollo de Aplicaciones Móviles Android

Curso que lleva a programadores con base en Java desde los fundamentos de **Kotlin** hasta una aplicación **Android** completa con **Jetpack Compose**, construyendo una app que consume una API REST con operaciones CRUD completas y persistencia local *offline-first*.

El contenido está escrito en Markdown y se publica como sitio web con [MkDocs](https://www.mkdocs.org) y el tema [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Contenido

Todo el material vive en la carpeta [`docs/`](docs/), organizado por capítulos y partes. La página de inicio del sitio es [`docs/index.md`](docs/index.md).

## Ver el sitio en local

Necesitas Python 3. Instala las dependencias:

```bash
pip install -r requirements.txt
```

Levanta el servidor de desarrollo (con recarga automática):

```bash
mkdocs serve
```

Luego abre `http://127.0.0.1:8000` en tu navegador.

Para generar el sitio estático (en la carpeta `site/`):

```bash
mkdocs build
```

## Autor

- José Miguel Candia — [GitHub](https://github.com/jmcandia)

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
