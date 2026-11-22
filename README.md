# mineria-textos-esperanto
# Clasificación de textos en Esperanto

Práctica de **Minería de Textos** (4º Ingeniería Informática, CUNEF, curso 2026/2027).

**Equipo:** Mikel Echarri Richard · Joaquín Álvarez Julia · Víctor Hernández Enciso

## Qué hace
Clasifica párrafos en Esperanto en tres temas: **física** (`fiziko`), **química** (`kemio`) y **biología** (`biologio`).

1. **Fase 1 — Dataset:** descarga artículos de la Wikipedia en Esperanto con su API, los divide en párrafos y los limpia.
2. **Fase 2 — NLP:** modelo propio basado en reglas (tokenizador, lematizador, etiquetado gramatical y stop-words),
   sin librerías de NLP, que se usa como spaCy: `doc = nlp(texto)`.
3. **Fase 3 — Clasificación:** vectorización TF-IDF y Naive Bayes. Accuracy = 0,835 y F1 macro = 0,835 en test.
   También clasifica páginas web reales.

## Ficheros
| Fichero | Contenido |
|---|---|
| `Practica_Esperanto.ipynb` | Cuaderno de la práctica (fases 1, 2 y 3) |
| `dataset.csv` | Dataset: 1800 párrafos (600 por clase), UTF-8, separador `;`, columnas `text;class` |
| `dataset_con_articulos.csv` | El mismo dataset con la columna `article` (artículo de origen de cada párrafo) |
| `Practica_Esperanto_PuntoDeControl_Git.ipynb` | Versión entregada en el punto de control (fases 1 y 2) |

## Cómo ejecutarlo
Abrir `Practica_Esperanto.ipynb` en Google Colab y pulsar **Entorno de ejecución → Ejecutar todo**.
- `GENERAR_DATASET = False` (por defecto): lee el dataset de este repositorio.
- `GENERAR_DATASET = True`: lo vuelve a generar desde Wikipedia (unos 7 minutos).

Si alguna web no responde, el cuaderno usa su plan B (GitHub → Wikipedia; stop-words → lista propia;
páginas web → texto de respaldo).

## Fuentes
Textos de [Vikipedio](https://eo.wikipedia.org) (CC BY-SA 4.0). Stop-words: `vortoj.json` del repositorio de la
asignatura [nlp-esperantilo](https://github.com/jparisu/nlp-esperantilo).
