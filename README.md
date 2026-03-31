# Clasificador y Generador de Letras de Canciones por Artista

## Authors  
Yayeshi Flores  
Ana Beatriz Simán  

---

## Descripción  

Este proyecto combina dos objetivos principales dentro del análisis de texto:

1. **Clasificación**: identificar el artista a partir de un fragmento de letra.  
2. **Generación**: producir nuevas letras imitando el estilo de un artista concreto.  

Trabajamos con un subconjunto de artistas representativos del pop:

**Taylor Swift · Michael Jackson · One Direction · Drake · Justin Bieber**

La idea es ver hasta qué punto el estilo de cada artista se puede aprender y reproducir usando distintos modelos de NLP.

---

## Pipeline del proyecto  

El flujo general del trabajo sigue estos pasos:

- Carga, limpieza y análisis exploratorio (EDA) del corpus  
- Modelos de clasificación (discriminativos):  
  - TF-IDF + Logistic Regression  
  - RNN / BiLSTM  
  - SentenceTransformers + Logistic Regression  
- Modelos de generación (generativos):  
  - LSTM  
  - LSTM + Attention  
  - GPT-2 fine-tuned  
- Evaluación cruzada: los clasificadores actúan como “jueces” para evaluar el estilo de los textos generados  

---

## Metodología  

### Clasificación  

Se comparan distintos enfoques, desde modelos simples basados en frecuencia hasta modelos con embeddings preentrenados. Esto permite analizar qué tipo de representación captura mejor el estilo de cada artista.

---

### Generación  

Se generan letras condicionadas por artista usando distintos modelos. Se compara el rendimiento de modelos entrenados desde cero frente a modelos preentrenados como GPT-2.

---

### Evaluación  

Para los modelos generativos se usa una estrategia indirecta:

Si un clasificador es capaz de reconocer correctamente el artista de un texto generado, se considera que ese texto refleja bien su estilo.

También se incluyen ejemplos generados por ChatGPT como referencia externa.

---

## Resultados principales  

- **SentenceTransformer + Logistic Regression** es el mejor modelo de clasificación  
- **TF-IDF** funciona mejor de lo esperado, lo que indica que el vocabulario ya contiene mucha señal  
- Las **RNN entrenadas desde cero** tienden a overfitting  

En generación:

- **GPT-2 fine-tuned** genera el texto más coherente y reconocible  
- Las **LSTM** producen texto más repetitivo y menos natural  
- ChatGPT sirve como referencia alta, aunque no siempre es más fácil de clasificar por artista  

---

## Conclusiones  

- Los modelos preentrenados marcan una gran diferencia, sobre todo con datasets pequeños  
- El estilo de los artistas se puede capturar parcialmente, pero hay bastante solapamiento entre algunos (especialmente en pop)  
- Para clasificación, los embeddings preentrenados son clave  
- Para generación, el fine-tuning de modelos grandes como GPT-2 mejora mucho los resultados  

---

## Tecnologías  

- Python  
- TensorFlow / Keras  
- PyTorch (Hugging Face Transformers)  
- scikit-learn  
- SentenceTransformers  

---

## Uso  

Abrir el notebook principal y ejecutar las celdas en orden para reproducir el pipeline completo.

Dependencias principales:
- Python 3
- TensorFlow / Keras
- PyTorch (Hugging Face Transformers)
- scikit-learn
- SentenceTransformers

