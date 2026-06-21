# Algoritmo de Búsqueda A*: Implementación y Análisis Comparativo en Grafos y Matrices

Artículo académico que documenta, analiza y valida la implementación del algoritmo A* y su comparación con BFS, DFS, Dijkstra y Bidirectional Search, aplicados a grafos ponderados y grids bidimensionales.

## Ecosistema del Proyecto

| Componente | Repositorio | Descripción |
|---|---|---|
| Core Library | [search-library](https://github.com/ahincho/search-library) | Framework extensible de algoritmos de búsqueda ([PyPI](https://pypi.org/project/search-library/)) |
| Benchmark Grafos | [graph-search](https://github.com/ahincho/graph-search) | Comparación de algoritmos en red vial real |
| Benchmark Grids | [path-search](https://github.com/ahincho/path-search) | Comparación en grids 2D con obstáculos y terrenos |
| Artículo | [search-paper](https://github.com/ahincho/search-paper) | Este repositorio |

## Estructura del Repositorio

```
search-paper/
├── main.tex                    # Documento principal
├── references.bib              # Bibliografía (BibTeX)
├── sections/
│   ├── 01-introduction.tex
│   ├── 02-theory.tex
│   ├── 03-methodology.tex
│   ├── 04-implementation.tex
│   ├── 05-results.tex
│   ├── 06-discussion.tex
│   ├── 07-conclusions.tex
│   └── 08-reproducibility.tex
├── figures/
├── compile.ps1                 # Compilación (PowerShell)
├── compile.bat                 # Compilación (CMD)
├── scripts/
│   ├── build.sh                # Compilación (Linux/macOS)
│   ├── clean.sh
│   └── watch.sh
├── .latexmkrc                  # Configuración latexmk
└── .github/workflows/ci.yml    # CI/CD: Build + Release
```

## Compilación Local

### Windows (PowerShell)

```powershell
.\compile.ps1
```

### Windows (CMD)

```cmd
compile.bat
```

### Linux / macOS

```bash
chmod +x scripts/build.sh
./scripts/build.sh
```

### Requisitos

- [MiKTeX](https://miktex.org/) (Windows) o [TeX Live](https://tug.org/texlive/) (Linux/macOS)
- Paquetes: `IEEEtran`, `babel-spanish`, `amsmath`, `tikz`, `listings`, `algorithms`, `booktabs`, `hyperref`

## CI/CD

El pipeline de GitHub Actions compila automáticamente el PDF:

- **Push a `main`**: Valida compilación y sube PDF como artifact
- **Tag `v*.*.*`**: Compila, renombra con versión y crea GitHub Release con el PDF adjunto

### Crear un release

```bash
git tag v1.1.0
git push origin v1.1.0
```

## Reproducción de Experimentos

### Benchmark en grafos (red de ciudades)

```bash
git clone https://github.com/ahincho/graph-search
cd graph-search
uv sync && uv run python src/main.py
# o con pip:
pip install search-library>=1.0.0 && python src/main.py
```

### Benchmark en grids (pathfinding 2D)

```bash
git clone https://github.com/ahincho/path-search
cd path-search
uv sync && uv run grid-benchmark
# o con pip:
pip install search-library>=1.0.0 && python src/main.py
```

## Autor

**Angel Hincho** — Universidad Nacional de San Agustín de Arequipa

- Email: ahincho@unsa.edu.pe
- GitHub: [@ahincho](https://github.com/ahincho)

## Licencia

MIT
