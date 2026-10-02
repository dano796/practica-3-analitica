# Predicción de calidad de vinos

Práctica 3 - Analítica de Datos

## Objetivo

Predecir si un vino es de calidad **Buena** (nota de los catadores ≥ 6) o **Mala** (nota < 6) a partir de 11 variables fisicoquímicas de laboratorio y el tipo de vino (blanco o tinto).

## Datos

`wine_data.csv`: 4.979 vinos Vinho Verde (3.961 blancos y 1.018 tintos), resultado de unir las tablas de vinos tintos y blancos y eliminar duplicados. El 63 % de los vinos son de calidad Buena.

## Despliegue

La aplicación (Vinalia) está en la carpeta `despliegue/`, junto con el modelo `modelo-cla-vinos-hiper.pkl` generado por el notebook de hiperparametrización y sus dependencias.

```bash
pip install -r despliegue/requirements.txt
streamlit run despliegue/despliegue_streamlit_vinos_doa_ftm.py
```
