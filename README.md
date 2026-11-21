# Alquileres de bicicletas (rentals)

> **Proyecto :** Regresión Lineal Múltiple para predecir la cantidad de alquileres de bicicletas (rentals)**referencia**
> 
>
> **Maestría en Ciencia de Datos e Inteligencia Artificial · EPG UNAJ**
> **Curso :** Machine Learning · 
> **Docente:** Dr. Alain Paul Herrera Urtiaga

**Equipo:** Jhonson R. Machaca Mamani · Antonio Alexei Colca Rojas

🔗 **Demo:** [enlace a la app publicada en Streamlit Community Cloud] · 📄 **Informes:** [Producto 1](informe/Producto1_ejemplo.md) · [Producto 2](informe/Producto2_ejemplo.md)

---

## 1. El problema

El problema consiste en predecir la cantidad de bicicletas alquiladas diariamente a partir de diferentes características climáticas y temporales.

Se busca determinar si variables como la temperatura, humedad, velocidad del viento, estación del año y día de la semana permiten estimar adecuadamente la demanda de alquiler de bicicletas.

**Pregunta:** ¿En qué medida las condiciones climáticas y las características temporales permiten predecir la cantidad de bicicletas alquiladas diariamente mediante modelos de Regresión Lineal Múltiple?

- **Tipo de problema:** Regresion Lineal Multiple
- **Métrica principal:** La métrica utilizada en el notebook es el **Error Porcentual Absoluto Medio (MAPE)**.

## 2. Los datos

| Campo | Detalle |
|---|---|
| Fuente |[Bike Sharing Dataset](https://github.com/robintux/Datasets4StackOverFlowQuestions/blob/master/bikes.csv) |
| Característica    |	Descripción |
| Total de registros	| 731 |
| Total de columnas	| 10 |
| Variables numéricas enteras	| 6 |
| Variables numéricas decimales	| 4 |
| Valores nulos	| 0 |
| Variable objetivo	| rentals |


## 3. Resultados principales


**Hallazgos clave:**
- 

## 4. Estructura del repositorio

```
├── README.md                          ← este archivo
├── data/README.md                     ← fuente y diccionario de variables
├── notebooks/
│   ├── 01_eda.ipynb                   ← análisis exploratorio (Producto 1)
│   ├── 02_modelos.ipynb               ← pipeline y comparación de 5 modelos (Producto 1)
│   ├── 03_optimizacion.ipynb          ← Optuna y comparación fold a fold (Producto 2)
│   ├── 04_no_supervisado_y_red.ipynb  ← perfiles con k-means y red neuronal (Producto 2)
│   └── 05_interpretacion.ipynb        ← variables importantes, sesgo y modelo final (Producto 2)
├── app/                               ← demo en Streamlit y modelo guardado
├── informe/                           ← informes de los productos 1 y 2
└── docs/                              ← guías del curso
```

## 5. Cómo reproducir

1. Abrir cada notebook en Google Colab: **Archivo → Abrir cuaderno → GitHub** y pegar el enlace de este repositorio.
2. Ejecutar en orden, de arriba hacia abajo (**Entorno de ejecución → Ejecutar todas**). Los datos se descargan solos.
3. Demo local: `pip install -r app/requirements.txt` y luego `streamlit run app/app.py`.

## 6. Uso de IA generativa

[Usamos un asistente de IA para depurar errores de código y revisar la redacción. Todo el código fue revisado y puede ser explicado por el equipo.]

## 7. Referencias

1. Libro Microsoft - Bishop https://www.microsoft.com/en-us/research/wp-content/uploads/2006/01/Bishop-Pattern-Recognition-and-Machine-Learning-2006.pdf


---

📘 **Guías del curso:** [Producto 1](docs/Producto1_guia.md) · [Producto 2](docs/Producto2_guia.md) · [GitHub con Colab](docs/Guia_GitHub_Colab.md)

