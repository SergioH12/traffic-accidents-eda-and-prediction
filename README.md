# TP1 — Análisis del dataset "Accidente"

Resumen
-------
Este repositorio contiene el trabajo práctico TP1: análisis exploratorio y modelado del dataset "Accidente" (accidents). El análisis principal está en el notebook `TP1_Accidente.ipynb`. El objetivo es explorar las características del dataset, realizar limpieza y transformaciones relevantes, y construir modelos de clasificación para predecir la severidad (`Severity`) del accidente.

Enlaces relevantes
------------------
- Notebook principal: https://github.com/SergioH12/Analisis1/blob/f2a8da17c66b8c7827baeb070bf43edb0296e52b/TP1_Accidente.ipynb
- Archivo de datos esperado: `Accidente.csv` (debe estar en la raíz del repo o la ruta especificada en el notebook)

Descripción del dataset
-----------------------
Cada fila representa un evento de accidente vial y las columnas contienen atributos del evento. Algunas columnas clave:
- Source, TMC, Severity (1–4), Start_Time, End_Time, Start_Lat, Start_Lng
- Weather_Timestamp, Temperature(F), Wind_Chill(F), Humidity(%), Pressure(in), Visibility(mi)
- Wind_Direction, Wind_Speed(mph), Precipitation(in), Weather_Condition
- Variables booleanas de POIs (Amenity, Bump, Crossing, ...), y columnas sobre crepúsculo / amanecer ('Sunrise_Sunset', 'Civil_Twilight', ...)

Cantidad de datos (aprox.)
- ~2.97M filas y 49 columnas en el dataset original.

Contenido del repositorio
-------------------------
- TP1_Accidente.ipynb — Notebook con todo el flujo de análisis: carga de datos, limpieza, EDA y modelado (PyCaret).
- Accidente.csv — CSV con los datos (si está presente en el repo).
- README.md — (este archivo).

Requisitos / Dependencias
-------------------------
El notebook se desarrolló usando Python 3.x y las siguientes librerías (no exhaustiva):
- pandas
- numpy
- matplotlib
- scikit-learn
- pycaret
- jupyter

Puedes crear un entorno virtual e instalar dependencias con pip:
```text
pandas
numpy
matplotlib
scikit-learn
pycaret
jupyter
```

Instalación rápida (ejemplo usando virtualenv + pip)
```bash
# crear y activar entorno (Linux / macOS)
python3 -m venv .venv
source .venv/bin/activate

# Windows (PowerShell)
# python -m venv .venv
# .\.venv\Scripts\Activate.ps1

pip install --upgrade pip
pip install -r requirements.txt
```

Cómo ejecutar
-------------
1. Asegúrate de tener `Accidente.csv` en la ruta correcta (la ruta por defecto utilizada en el notebook es `./Accidente.csv`).
2. Inicia Jupyter Notebook:
```bash
jupyter notebook
```
3. Abre `TP1_Accidente.ipynb` y ejecuta las celdas en orden.

Si prefieres ejecutar en Google Colab:
- Sube `Accidente.csv` al entorno de Colab o monta Google Drive y ajusta la ruta en el notebook.

Resumen del flujo del notebook
------------------------------
1. Carga de datos con pandas y examen inicial (`.info()`, `.head()`, `.describe()`).
2. Eliminación de columnas irrelevantes y manejo de nulos/duplicados.
3. Conversión de columnas de fecha/hora, extracción de variables temporales (hora, día, etc.).
4. Análisis exploratorio (distribuciones, correlaciones, conteos por `Severity`, visualizaciones).
5. Preprocesamiento: codificación de variables categóricas, escalado si corresponde, tratamiento de outliers.
6. Modelado: uso de PyCaret para experimentación con clasificadores y selección de modelos.
7. Evaluación y conclusiones.

Buenas prácticas y notas
------------------------
- El dataset es grande (~3M filas): ten en cuenta memoria al cargarlo en máquinas con recursos limitados. Considera muestrear o trabajar por lotes si hace falta.
- Guarda versiones del notebook y usa checkpoints al experimentar con modelos pesados.
- Cuando uses PyCaret, revisa la configuración del `setup()` para controlar imputación, codificación y muestreo.

Resultados y conclusiones (resumen)
-----------------------------------
Dentro del notebook se documentan los hallazgos principales (distribución de severidad, relaciones con condiciones climáticas, hora del día, y otras variables). Las conclusiones sobre la capacidad predictiva de las características y el desempeño de los modelos están en la sección final del notebook.


Contacto
--------
Autor: SergioH12  
Repositorio: https://github.com/SergioH12/Analisis1

```
