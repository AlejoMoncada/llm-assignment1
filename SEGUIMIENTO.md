# Seguimiento: Assignment 1

Cierre: lunes 2 de noviembre de 2026, 23:59, hora de Bogotá.

**Estado actual:** notebook completo y ejecutado. Falta lo que le toca a Alejandro: reescribir las conclusiones, revisar la política de IA y entregar.

## Checklist

### Preparación

- [x] Visto bueno de Alejandro al plan
- [x] `CLAUDE.md` y `SEGUIMIENTO.md`
- [x] Diagrama del proceso
- [x] `03_Assignment_Sesion1_BoW_Word2Vec` en la carpeta
- [x] Dataset BBC news en la carpeta
- [x] Notebook base y dataset leídos
- [x] Visto bueno de Alejandro al plan ajustado
- [x] Commit del notebook base intacto
- [x] Entorno `uv` y `uv.lock`, según lo que importe el notebook

### C1 Corpus

- [x] EDA: noticias, fechas, longitudes, duplicados y artefactos
- [x] Tokenización, oraciones y vocabulario
- [x] Conteos frente a la referencia: 1.000 noticias, 522.750 tokens (−0,05 %) y 25.616 palabras únicas (+0,06 %)
- [x] Decisiones de preprocesamiento justificadas, con su efecto medido

### C2 Frecuencias y Zipf

- [x] Frecuencias de palabras
- [x] Bigramas
- [x] Zipf en log-log con pendientes por tramo
- [x] Explicación con evidencia de dónde se cumple y dónde se desvía

### C3 BoW

- [x] Matriz documento-término de los primeros `n` documentos
- [x] Demostración de que pierde el orden: vectores idénticos, comprobado en el código

### C4 Concordancias

- [x] Índice, concordancias y comparación de `strike` y `market`
- [x] Efecto de la ventana con ±2, ±5 y ±10
- [x] Conexión con la hipótesis distribucional

### C5 Word2Vec

- [x] Modelos con ventanas 2, 5 y 10 y 3 semillas
- [x] Vecinos por similitud coseno y solapamiento entre ventanas
- [x] Estabilidad según la frecuencia de la palabra
- [x] Integración con `doctors`
- [x] Análisis crítico: cercanía no es sinonimia ni verdad, con vecinos reales

### Cierre

- [x] Borrador de conclusiones con cifras del notebook
- [x] Ejecución doble desde kernel limpio, con resultados iguales
- [x] Cifras del texto contrastadas con las salidas del notebook
- [ ] Alejandro revisa el notebook y sus respuestas
- [ ] Alejandro reescribe las conclusiones con su voz y revisa la política de IA del curso
- [ ] Alejandro vuelve a ejecutar el notebook si cambia algo en las celdas de código
- [ ] Alejandro sube el `.ipynb` al Moodle antes del lunes 2 de noviembre, 23:59, hora de Bogotá

## Observaciones de Alejandro

Se registran aquí a medida que llegan, con fecha y lo que cambió.

- 2026-10-31: en Teams no se compartió ningún notebook de la clase. El notebook base oficial es `03_Assignment_Sesion1_BoW_Word2Vec.ipynb`, del Moodle, y se trabaja sobre ese. Cambio: no se espera otro notebook; las decisiones de tokenización "de clase" se contrastan solo con los conteos de referencia.

## Pendientes futuros (fuera del alcance de esta sesión)

- [ ] Anteproyecto del proyecto final. Vence el 29 de noviembre de 2026. Word de máximo 2 páginas, en grupo de 3 a 6 personas. Secciones: problema, estado del arte, dataset, método propuesto (opcional) y resultados esperados.

## Bitácora

### 2026-10-31

- Rúbrica oficial recibida: manda sobre el plan inicial. Se descarta descargar el corpus de `mlg.ucd.ie` o Hugging Face; solo vale el dataset del Moodle.
- Alejandro dio el visto bueno y pidió diagramar y documentar el proceso.
- Creados `CLAUDE.md`, `SEGUIMIENTO.md` y el diagrama del proceso.
- El notebook base y el dataset aún no están en la carpeta. El notebook y el entorno quedan a la espera.
- Llegaron el notebook base y `BBC news.csv` (SHA-256 `caad658d…673d`). Se leyeron y se ajustó el plan; pendiente de visto bueno.
- Mediciones exploratorias, sin escribir en el repo: 1.000 noticias, sin categorías en el CSV. Con minúsculas y `[a-z]+(?:'[a-z]+)*` salen 522.750 tokens y 25.616 palabras únicas. Si además se normaliza `’` a `'`, salen 521.019 y 25.755.
- Plan ajustado aprobado. Notebook completado en un commit por criterio y ejecutado.
- Word2Vec: gensim imprime `Exception ignored in: ...our_dot_float` al entrenar. Con tres combinaciones de NumPy y SciPy y con distinto `PYTHONHASHSEED`, los vectores salen idénticos. Queda visible y explicado en el notebook.
- Costo conocido de no normalizar `’`: el fragmento `s` entra al top 10 sin stop words (1.370). Está explicado en el notebook.
- Texto repetido al final de las notas (`follow bbc`, `story ideas`): se deja para no alterar los conteos de referencia, y se avisa en el notebook.

## Dudas abiertas

- Descriptores de los niveles de la rúbrica (0 / 0,5 / 0,7 / 0,8 / 1): no los tenemos; se apunta al nivel máximo.
- Política de IA del curso: no consultada; la revisa Alejandro.
