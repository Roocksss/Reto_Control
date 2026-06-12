# Horno de Sostenimiento — Equipo 2

**MA2008B · ITESM Querétaro · RONAL GROUP**  
Kira Pantoja · Raúl Herrera · Patricio Lugo · Sergio Rock

---

## Qué hace este repo

Predicción de temperatura en horno industrial mediante una red TCN (Temporal Convolutional Network) y control PID clásico. El modelo aprende de 14 días de datos históricos y se usa para extraer una función de transferencia discreta G(z).

**Resultados TCN:** MAE = 3.28 °C · RMSE = 4.50 °C · R² = 0.56

---

## Archivos principales

| Archivo | Descripción |
|---------|-------------|
| `RonalAED_v2.ipynb` | EDA: distribuciones, correlaciones, ACF/PACF |
| `TCN_ronal_v2.ipynb` | Modelo TCN: entrenamiento, evaluación y extracción de G(z) |
| `dataset_horno_sostenimiento1.csv` | Dataset: 20,160 muestras, Ts = 1 min |

---

## Cómo correrlo

### TCN (Google Colab recomendado)

1. Subir `TCN_ronal_v2.ipynb` y `dataset_horno_sostenimiento1.csv` a Colab.
2. Ejecutar todas las celdas en orden.

Parámetros clave en la clase `Config`:

```python
SEQ_LEN = 90          # ventana de entrada: 90 minutos (justificado por ACF)
EPOCHS  = 100
LR      = 5e-4
```

### EDA

Abrir `RonalAED_v2.ipynb` en Jupyter o Colab y ejecutar en orden. No requiere GPU.

---

## Dependencias

```bash
pip install torch numpy pandas scikit-learn scipy matplotlib statsmodels
```

---

## Equipo

Raúl Herrera · Patricio Lugo · Sergio Rock · Kira Pantoja  
Profesores: Dr. Leonardo Ledesma · Dr. Fernando Gómez Salas
