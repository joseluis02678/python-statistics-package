<p align="center">
  <img src="https://raw.githubusercontent.com/joseluis02678/Parcial---LP2/main/images/logo.jpg" alt="Logo UNALM" width="160">
</p>

<div align="center">
  <h1>📊 Estadística Lib</h1>
  <p><b>Professional Statistics Library in Python</b></p>
  <p>Librería de análisis estadístico implementando principios de Programación Orientada a Objetos</p>
  <p>
    <img src="https://img.shields.io/badge/Python-3.12-blue?logo=python&style=flat-square">
    <img src="https://img.shields.io/badge/OOP-Design%20Patterns-green?style=flat-square">
    <img src="https://img.shields.io/badge/License-MIT-orange?style=flat-square">
    <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square">
  </p>
</div>

---

## 📋 Tabla de Contenidos

- [Descripción](#descripción)
- [Características](#características)
- [Instalación](#instalación)
- [Uso Rápido](#uso-rápido)
- [Módulos](#módulos)
- [Conceptos OOP](#conceptos-oop)
- [Ejemplos Prácticos](#ejemplos-prácticos)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Testing](#testing)
- [Autores](#autores)

---

## 📖 Descripción

**Estadística Lib** es una librería Python profesional para análisis estadístico que demuestra la aplicación de principios SOLID y diseño orientado a objetos. Proporciona herramientas para:

- 📊 **Análisis Descriptivo:** Media, mediana, moda, varianza, desviación estándar
- 📈 **Variables Cualitativas:** Frecuencias, distribuciones categóricas
- 🔬 **Inferencia Estadística:** Distribuciones muestrales, pruebas de hipótesis
- 🏗️ **Arquitectura Escalable:** Diseñada con herencia y polimorfismo

---

## ✨ Características Principales

| Característica | Descripción |
|---|---|
| 🎯 **Modular** | Código organizado en módulos independientes |
| 🔐 **Encapsulado** | Atributos privados protegidos |
| 📚 **Bien Documentado** | Docstrings y ejemplos incluidos |
| ✅ **Testeado** | Suite de tests completa |
| 🚀 **Escalable** | Arquitectura extensible |

---

## 🛠️ Instalación

### Requisitos previos
- Python 3.8+
- pip

### Pasos

```bash
# Clonar el repositorio
git clone https://github.com/joseluis02678/estadistica-lib.git

# Entrar al directorio
cd estadistica-lib

# Instalar dependencias
pip install -r requirements.txt
```

---

## ⚡ Uso Rápido

```python
from estadistica import MedidasCuantitativas

# Análisis de datos
datos = [10, 20, 30, 40, 50, 60]
estadistica = MedidasCuantitativas(datos)

# Obtener métricas
print(f"Media: {estadistica.media()}")           # 35.0
print(f"Mediana: {estadistica.mediana()}")       # 35.0
print(f"Varianza: {estadistica.varianza()}")     # 191.67
print(f"Desv. Estándar: {estadistica.desv_estandar()}")  # 13.84
```

---

## 📦 Módulos

### 1. `cuantitativos.py`
Análisis de variables numéricas continuas

```python
from estadistica import MedidasCuantitativas

datos = [15, 25, 35, 45, 55]
m = MedidasCuantitativas(datos)

# Medidas de centralización
media = m.media()
mediana = m.mediana()
moda = m.moda()

# Medidas de dispersión
varianza = m.varianza()
rango = m.rango()
```

### 2. `cualitativos.py`
Análisis de variables categóricas

```python
from estadistica import ResumenCualitativo
import pandas as pd

# Análisis de datos categóricos
df = pd.DataFrame({
    'color': ['rojo', 'azul', 'rojo', 'verde', 'azul', 'rojo']
})

cualitativo = ResumenCualitativo(df, columna='color')
frecuencias = cualitativo.frecuencias()
moda = cualitativo.moda()
```

### 3. `inferencia.py`
Distribuciones muestrales y pruebas de hipótesis

```python
from estadistica import DistribucionesMuestrales

datos = [valores de una muestra]
dist = DistribucionesMuestrales(datos)

# Cálculos de inferencia
media_muestral = dist.media()
error_estandar = dist.error_estandar()
```

---

## 🎓 Conceptos OOP Implementados

### 1. **Herencia** 
Todas las clases heredan de `EstadisticaBase`

```python
class EstadisticaBase:
    def __init__(self, datos):
        self.datos = np.array(datos)

class MedidasCuantitativas(EstadisticaBase):
    # Hereda todos los métodos de la base
    pass
```

**Ventaja:** Código reutilizable y consistente

---

### 2. **Polimorfismo**
Métodos redefinidos en subclases

```python
# En EstadisticaBase
def moda(self):
    """Calcula la moda de datos numéricos"""
    # Implementación base
    pass

# En ResumenCualitativo (redefine moda)
def moda(self):
    """Calcula la moda de variables categóricas"""
    # Implementación especializada
    pass
```

**Ventaja:** Cada clase implementa métodos según su naturaleza

---

### 3. **Encapsulamiento**
Atributos privados protegidos

```python
class EstadisticaBase:
    def __init__(self, datos):
        self._datos = np.array(datos)  # Privado
    
    @property
    def datos(self):
        return self._datos
```

**Ventaja:** Control de acceso y integridad de datos

---

### 4. **Abstracción**
Interfaz simple para el usuario

```python
# Usuario solo ve esto
resultado = estadistica.media()

# Internamente puede haber cálculos complejos
# pero todo está abstraído
```

**Ventaja:** Código limpio y fácil de usar

---

## 💡 Ejemplos Prácticos

### Ejemplo 1: Análisis de Calificaciones

```python
from estadistica import MedidasCuantitativas

# Calificaciones de estudiantes
calificaciones = [15, 18, 16, 20, 14, 19, 17, 18]

analisis = MedidasCuantitativas(calificaciones)

print(f"Promedio: {analisis.media():.2f}")
print(f"Nota más frecuente: {analisis.moda()}")
print(f"Dispersión (varianza): {analisis.varianza():.2f}")
```

### Ejemplo 2: Análisis Categórico

```python
from estadistica import ResumenCualitativo
import pandas as pd

# Encuesta de satisfacción
datos = pd.DataFrame({
    'satisfaccion': ['Muy Bien', 'Bien', 'Muy Bien', 'Regular', 'Bien', 'Muy Bien']
})

encuesta = ResumenCualitativo(datos, columna='satisfaccion')
print(encuesta.frecuencias())
```

---

## 📂 Estructura del Proyecto

```
estadistica-lib/
├── estadistica/
│   ├── __init__.py
│   ├── base.py              # Clase base EstadisticaBase
│   ├── cuantitativos.py     # Análisis variables numéricas
│   ├── cualitativos.py      # Análisis variables categóricas
│   ├── inferencia.py        # Distribuciones muestrales
│   ├── otros/
│   │   └── op_matriz.py     # Operaciones matriciales
│   └── tests/
│       ├── test_cuantitativos.py
│       ├── test_cualitativos.py
│       ├── test_inferencia.py
│       └── test_matrices.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ✅ Testing

Ejecutar todos los tests:

```bash
pytest estadistica/tests/
```

Ejecutar tests de un módulo específico:

```bash
pytest estadistica/tests/test_cuantitativos.py -v
```

---

## 🎯 Use Cases

Esta librería es ideal para:

- ✅ Cursos de estadística y programación
- ✅ Análisis exploratorio de datos (EDA)
- ✅ Proyectos de data science
- ✅ Aprender diseño de software con OOP
- ✅ Prototipado rápido de análisis estadísticos

---

## 👥 Autores

| Nombre | GitHub |
|--------|--------|
| Jose Luis Garay Ramos | [@joseluis02678](https://github.com/joseluis02678) |
| Omar Sebastián Castillo Torres | [@Sebas20050700](https://github.com/Sebas20050700) |
| Ayrton Sánchez Gómez | [@ayrtonsg752294](https://github.com/ayrtonsg752294) |

---

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Ver archivo [LICENSE](LICENSE) para más detalles.

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Para cambios importantes:

1. Fork el repositorio
2. Crea una rama (`git checkout -b feature/mejora`)
3. Commit tus cambios (`git commit -m 'Agrega mejora'`)
4. Push a la rama (`git push origin feature/mejora`)
5. Abre un Pull Request

---

## 📞 Contacto

Para preguntas o sugerencias, contacta a los autores a través de GitHub.

---

**⭐ Si te fue útil, dale una estrella!**
