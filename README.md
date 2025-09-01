# Análisis probabilístico de movilidad con redes bayesianas multinomiales

Proyecto académico que modela relaciones entre variables de transporte y **tiempos de viaje** mediante **redes bayesianas multinomiales** (bnlearn / R + Quarto). El **reporte principal** con la metodología, resultados y discusión está en la carpeta **`reports/`**.

## Integrantes

* **Luis Carlos Marrufo Padilla**
* **Gustavo Andrés Aguilar Torreblanca**
* **Joshua Alexander Chaidez Ochoa**
* **Ángel Esparza Enríquez**

## Estructura del repositorio

```
.
├─ data/
│  └─ tviaje_clean.csv              # Datos procesados exportados desde el notebook
├─ notebooks/
│  ├─ data_cleaning.ipynb           # Limpia datos externos y discretiza el tiempo
│  ├─ model.qmd                     # Script Quarto para ajustar/consultar la RBM
│  └─ model.html                    # Render del modelo (salida)
├─ reports/
│  └─ Artículo_1_RBM.pdf            # Reporte con métodos, resultados y conclusiones
├─ README.md
└─ .gitignore
```

## Datos

* Los **datos crudos** provienen de la **Encuesta Origen-Destino 2017** del INEGI:
  [https://www.inegi.org.mx/programas/eod/2017/#datos\_abiertos](https://www.inegi.org.mx/programas/eod/2017/#datos_abiertos)
* Dentro del paquete descargado, únicamente se usa el archivo:

  ```
  eod_2017_csv/
      tviaje_eod2017/
          conjunto_de_datos/
              tviaje.csv
  ```
* Este archivo no se incluye en el repositorio por su tamaño. En su lugar:

  * El notebook **`notebooks/data_cleaning.ipynb`** toma el `tviaje.csv`, lo limpia, **discretiza el tiempo** y genera el dataset procesado **`data/tviaje_clean.csv`**.
  * Este archivo procesado es el que se utiliza en **`notebooks/model.qmd`** para entrenar y consultar la red bayesiana.

## Resumen

1. Descargar `tviaje.csv` desde INEGI.
2. Ejecutar **`notebooks/data_cleaning.ipynb`** → produce **`data/tviaje_clean.csv`**.
3. Renderizar **`notebooks/model.qmd`** con Quarto → genera **`model.html`**.
4. Resultados en **`reports/Artículo_1_RBM.pdf`**.
