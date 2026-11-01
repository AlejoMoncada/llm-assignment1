# Assignment 1: De las noticias a los vectores

Modelos de Lenguaje de Gran Escala, MIA, Universidad de La Sabana (Moodle, curso 27378).
Trabajo individual de Alejandro. Cierre: lunes 2 de noviembre de 2026, 23:59, hora de Bogotá.

Avance, decisiones y observaciones: `SEGUIMIENTO.md`.
Diagrama del proceso: `.archify/workflow-plan-assignment-20261031-082111/plan-assignment.html`.

## Entregable

Un solo `.ipynb` con todas las celdas ejecutadas, construido sobre `03_Assignment_Sesion1_BoW_Word2Vec` y el dataset BBC news del Moodle.

## Orden de prioridad

1. Rúbrica oficial (abajo).
2. Notebook base: sus celdas y su estructura mandan sobre las secciones del plan.
3. Observaciones de Alejandro registradas en `SEGUIMIENTO.md`.

## Rúbrica

5 criterios de 1 punto cada uno, con niveles 0 / 0,5 / 0,7 / 0,8 / 1.

| Criterio | Qué exige |
|---|---|
| C1 Corpus | Tokeniza y verifica conteos, vocabulario y decisiones de preprocesamiento |
| C2 Frecuencias y Zipf | Frecuencias y bigramas, con la distribución explicada con evidencia |
| C3 BoW | Construirlo y demostrar que pierde el orden de las palabras |
| C4 Concordancias | Comparar contextos y explicar el efecto de la ventana |
| C5 Word2Vec | Comparar embeddings entre ventanas y conectar frecuencia, contexto y límites |

Requisitos de entrega: justificar el preprocesamiento, usar el mismo corpus en todo y no tratar la cercanía entre vectores como sinonimia ni como verdad.

Referencia de la clase para verificar conteos: 1.000 noticias, unos 523.000 tokens y unas 25.600 palabras únicas. Una diferencia mayor a 1 % se investiga y se explica; el tokenizador no se ajusta solo para que dé el número.

## Secciones y criterios

| Sección del notebook base | Peso | Criterio |
|---|---|---|
| 0. Preparación, con EDA breve | — | C1 |
| 1. Tokenización y preparación del corpus | 20 % | C1 |
| 2. Frecuencias, bigramas y Zipf | 20 % | C2 |
| 3. Bag of Words | 20 % | C3 |
| 4. Concordancias y contexto | 15 % | C4 |
| 5. Word2Vec, con ventanas 2, 5 y 10 | 20 % | C5 |
| 6. Integración, con el análisis crítico | 5 % | C5 y requisito de entrega |
| Conclusión (máximo 5 líneas) | Incluida en el 5 % | Todos |

## Reglas

- Corpus: solo `BBC news.csv` del Moodle, en la raíz. No descargar de otra fuente. No tiene columna de categorías, así que BoW se hace sobre los primeros `n` documentos, como pide la plantilla.
- Plantilla: el notebook del Moodle es el único base. Se conservan sus secciones y nombres de funciones, pero no se copia el enunciado: el texto va en primera persona, con tono de estudiante. Al entregar no queda ningún `TODO` ni `pass`. Límites de texto: BoW 3 líneas, conclusión 5 líneas.
- Gráficos: seaborn, con la paleta definida al inicio del notebook. El título dice el hallazgo, las anotaciones marcan los puntos clave y los valores se calculan de los datos.
- Hilo conductor: el viaje de contar palabras a espacios latentes densos, con hipótesis antes de cada gráfica o tabla pesada y hallazgo después. Todo ejemplo sale del corpus y de las salidas reales; si un caso no se sostiene, se dice.
- Extras: TF-IDF (solo `TfidfTransformer`, sobre conteos del tokenizador propio), t-SNE, `adjustText` con `iter_lim` fijo para que la imagen sea determinista, y tabla resumen. Los tiempos de esa tabla cambian en cada ejecución; las cifras no.
- Tokenización: sin tokenizadores externos (tampoco `CountVectorizer` ni NLTK). Minúsculas, sin números por defecto, `[a-z]+(?:'[a-z]+)*`, sin normalizar `’`; el efecto de normalizarlo se muestra medido. Para oraciones, `;` cuenta como separador porque el CSV une párrafos con `; `.
- Entorno: `uv`, con las dependencias fijadas en `uv.lock`.
- Reproducibilidad: semillas fijas en Python, NumPy y gensim, con `workers=1` y un `hashfxn` estable, de modo que los vectores no dependen de `PYTHONHASHSEED`. `entrenar_word2vec(ventana, seed=42)` conserva el nombre de la plantilla; se agrega `modelo_10` y 2 semillas extra solo para medir el ruido.
- Git: solo commits locales con Conventional Commits, sin coautoría, sin push y sin publicar nada. Un commit por criterio; el notebook base se versiona primero intacto. El dataset queda fuera de git.
- Notebook: todo el código dentro del `.ipynb`, sin módulos externos. Texto en español y código en inglés. Se conserva "Autor: Andres Rosso" y se agrega el nombre de Alejandro como estudiante.
- Corpus único: se carga una vez y todas las secciones usan los mismos documentos y el mismo tokenizador. Quitar stopwords es solo una vista en tablas de frecuencias, bigramas y BoW, y se justifica.
- Conclusiones: se escriben al final, con cifras del propio notebook. Son un borrador: Alejandro las reescribe con su voz y revisa la política de IA del curso.
- Entrega: la sube Alejandro al Moodle.

## Reparto

- Opus: orquesta, diseña los experimentos, revisa cada entrega e interpreta los resultados.
- Subagentes con Haiku: andamiaje, celdas repetitivas y ejecuciones.

## Comando de verificación final

Con el notebook en su ubicación definitiva, ejecutar dos veces desde un kernel limpio y comparar los resultados:

```bash
uv run jupyter nbconvert --to notebook --execute --inplace 03_Assignment_Sesion1_BoW_Word2Vec.ipynb
```
