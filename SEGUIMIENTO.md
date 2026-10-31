# Seguimiento: Assignment 1

Cierre: lunes 2 de noviembre de 2026, 23:59, hora de Bogotá.

**Estado actual:** bloqueado hasta que el notebook base y el dataset estén en esta carpeta.

## Checklist

### Preparación

- [x] Visto bueno de Alejandro al plan
- [x] `CLAUDE.md` y `SEGUIMIENTO.md`
- [x] Diagrama del proceso
- [ ] `03_Assignment_Sesion1_BoW_Word2Vec` en la carpeta (lo pone Alejandro)
- [ ] Dataset BBC news en la carpeta (lo pone Alejandro)
- [ ] Notebook base leído y mapeo de secciones confirmado
- [ ] Commit del notebook base intacto
- [ ] Entorno `uv` y `uv.lock`, según lo que importe el notebook

### C1 Corpus

- [ ] EDA: noticias, categorías, longitudes y duplicados
- [ ] Tokenización y vocabulario
- [ ] Conteos frente a la referencia (1.000 noticias, unos 523.000 tokens, unas 25.600 palabras únicas)
- [ ] Decisiones de preprocesamiento justificadas, con su efecto medido

### C2 Frecuencias y Zipf

- [ ] Frecuencias de palabras
- [ ] Bigramas
- [ ] Zipf en log-log con pendiente ajustada
- [ ] Explicación con evidencia de dónde se cumple y dónde se desvía

### C3 BoW

- [ ] Matriz BoW y términos por categoría
- [ ] Demostración de que pierde el orden: vectores idénticos, comprobado en el código

### C4 Concordancias

- [ ] Concordancias y comparación de contextos de una misma palabra
- [ ] Efecto de la ventana con ±2, ±5 y ±10
- [ ] Conexión con la hipótesis distribucional

### C5 Word2Vec

- [ ] Modelos con ventanas 2, 5 y 10 y 3 semillas
- [ ] Vecinos por similitud coseno y solapamiento entre ventanas
- [ ] Estabilidad según la frecuencia de la palabra
- [ ] Análisis crítico: cercanía no es sinonimia ni verdad, con vecinos reales

### Cierre

- [ ] Borrador de conclusiones con cifras del notebook
- [ ] Ejecución doble desde kernel limpio, con resultados iguales
- [ ] Revisión contra la rúbrica y los requisitos de entrega
- [ ] Alejandro reescribe las conclusiones y revisa la política de IA del curso
- [ ] Alejandro sube el `.ipynb` al Moodle

## Observaciones de Alejandro

Se registran aquí a medida que llegan, con fecha y lo que cambió.

## Bitácora

### 2026-10-31

- Rúbrica oficial recibida: manda sobre el plan inicial. Se descarta descargar el corpus de `mlg.ucd.ie` o Hugging Face; solo vale el dataset del Moodle.
- Alejandro dio el visto bueno y pidió diagramar y documentar el proceso.
- Creados `CLAUDE.md`, `SEGUIMIENTO.md` y el diagrama del proceso.
- El notebook base y el dataset aún no están en la carpeta. El notebook y el entorno quedan a la espera.

## Dudas abiertas

- Descriptores de los niveles de la rúbrica (0 / 0,5 / 0,7 / 0,8 / 1): no los tenemos; se apunta al nivel máximo.
- Política de IA del curso: no consultada.
