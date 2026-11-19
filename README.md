# 🎓 Alerta temprana de deserción estudiantil

> **📌 Proyecto de ejemplo.** Este repositorio muestra cómo debe quedar el repositorio de su proyecto al entregar los productos 1 y 2. Úsenlo como **referencia**: copien la estructura y el estilo, no el contenido.
>
> **Machine Learning · Maestría en Ciencia de Datos e Inteligencia Artificial · EPG UNAJ**
> Docente: Dr. Alain Paul Herrera Urtiaga

**Equipo:** [Integrante 1] · [Integrante 2] · [Integrante 3]

🔗 **Demo:** [enlace a la app publicada en Streamlit Community Cloud] · 📄 **Informes:** [Producto 1](informe/Producto1_ejemplo.md) · [Producto 2](informe/Producto2_ejemplo.md)

---

## 1. El problema

Uno de cada tres estudiantes universitarios abandona su carrera. Si la universidad pudiera identificarlos **al terminar el primer semestre**, podría ofrecerles tutoría a tiempo.

**Pregunta:** al terminar el primer semestre, ¿qué estudiantes abandonarán la carrera?

- **Tipo de problema:** clasificación binaria (abandona / no abandona)
- **Métrica principal:** **recall**, porque no detectar a un estudiante que abandonará cuesta más que ofrecer una tutoría innecesaria. Reportamos también el **ROC-AUC**.

## 2. Los datos

| Campo | Detalle |
|---|---|
| Fuente | [Predict Students' Dropout and Academic Success](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success) (UCI Machine Learning Repository) |
| Tamaño | 4 424 estudiantes |
| Variables usadas | 12: datos de ingreso, situación económica y resultados del 1.er semestre |
| Variable objetivo | `abandona` (1 = abandonó la carrera): **32 %** de los casos |

Solo usamos variables que existen **al terminar el 1.er semestre**. Las del 2.º semestre se excluyeron para evitar fuga de datos.

## 3. Resultados principales

| Modelo | Recall (CV) | ROC-AUC (CV) |
|---|---|---|
| Baseline (clase mayoritaria) | 0,000 | 0,500 |
| k-NN (k = 15) | 0,591 ± 0,032 | 0,867 ± 0,008 |
| Random Forest | 0,739 ± 0,017 | 0,887 ± 0,012 |
| LightGBM | 0,748 ± 0,029 | 0,886 ± 0,011 |
| **Regresión logística (L2) · modelo final** | **0,784 ± 0,021** | **0,895 ± 0,010** |
| LightGBM optimizado con Optuna | — | 0,894 ± 0,012 |
| Red neuronal (MLP) | — | 0,885 ± 0,010 |

**En el test**, el modelo final detecta **79 de cada 100** estudiantes que abandonarán (recall = 0,785; ROC-AUC = 0,905).

**Hallazgos clave:**
- La señal más fuerte son los **cursos aprobados en el 1.er semestre**: quienes no aprueban ninguno abandonan en un **79 %**.
- LightGBM optimizado **empata** con la regresión logística (p = 0,58), así que elegimos la logística por ser más simple.
- k-means encontró, sin conocer la respuesta, un perfil de **764 estudiantes con 80 % de abandono**.
- ⚠️ El modelo detecta menos abandonos en **mujeres (73 %)** que en **hombres (84 %)**: es una limitación a corregir.

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

[Ejemplo: "Usamos un asistente de IA para depurar errores de código y revisar la redacción. Todo el código fue revisado y puede ser explicado por el equipo."]

---

📘 **Guías del curso:** [Producto 1](docs/Producto1_guia.md) · [Producto 2](docs/Producto2_guia.md) · [GitHub con Colab](docs/Guia_GitHub_Colab.md)
"# Proy12_Unaj_Bikes" 
