# Predicción de calidad de vinos

Práctica 3 - Analítica de Datos

## Objetivo

Predecir si un vino es de calidad **Buena** (nota de los catadores ≥ 6) o **Mala** (nota < 6) a partir de 11 variables fisicoquímicas de laboratorio y el tipo de vino (blanco o tinto).

## Datos

`wine_data.csv`: 4.979 vinos Vinho Verde (3.961 blancos y 1.018 tintos), resultado de unir las tablas de vinos tintos y blancos y eliminar duplicados. El 63 % de los vinos son de calidad Buena.

## Notebooks

| Orden | Notebook | Contenido |
|---|---|---|
| 1 | `Seleccion_Factores_Vinos_DOA_FTM.ipynb` | Unión de las tablas, limpieza, variable objetivo y análisis de correlaciones |
| 2 | `Validación_Cruzada_Vinos_DOA_FTM.ipynb` | Comparación de 6 modelos con validación cruzada estratificada de 10 folds |
| 3 | `Hiperparametrizacion_GridSearch_Vinos_DOA_FTM.ipynb` | Hiperparametrización del mejor modelo (red neuronal) con GridSearch |
| 4 | `Despliegue_Streamlit_Vinos_DOA_FTM.ipynb` | Interfaz gráfica con Streamlit (exportada a `despliegue/despliegue_streamlit_vinos_doa_ftm.py`) |

## Resultados

F1 macro promedio en la validación cruzada:

| Modelo | F1 macro |
|---|---|
| **Red neuronal (GridSearch)** | **0.749** |
| Red neuronal | 0.739 |
| SVM | 0.736 |
| XGBoost | 0.734 |
| Random Forest | 0.721 |
| Knn | 0.718 |
| Árbol de decisión | 0.704 |

El modelo final es una red neuronal (MLP) con dos capas ocultas (100, 50), activación relu y regularización `alpha=0.01`. Obtiene un F1 macro de 0.749 en prueba y 0.768 en entrenamiento: una diferencia de 1.9 puntos, sin overfitting. La variable más asociada a la calidad es el alcohol.

```bash
pip install -r despliegue/requirements.txt
streamlit run despliegue/despliegue_streamlit_vinos_doa_ftm.py
```

---

### Desarrollado por

- Daniel Ortiz Aristizábal
- Felipe Torres Montoya

### Analítica de Datos - Universidad Pontificia Bolivariana
