# 📐 Figuras Geométricas — POO en Python

**Autor:** Elian Andrade  
**Fecha de ejecución:** 06/05/2026 — 16:11:53  
**Lenguaje:** Python 3  
**Paradigma:** Programación Orientada a Objetos (POO)

---

## 📋 Descripción

Este proyecto implementa un sistema de figuras geométricas usando los pilares de la POO en Python: **encapsulamiento**, **herencia** y **polimorfismo**. Se definen cuatro clases que calculan área y perímetro de distintas figuras, con validación de datos a través de `getters` y `setters`.

---

## 🗂️ Estructura del proyecto

```
figuras_geometricas.py
│
├── class FigurasGeometricas     ← Clase base (encapsulamiento)
│   ├── @property alto / ancho   ← Getters
│   ├── @alto.setter / @ancho.setter  ← Setters con validación
│   ├── area()
│   └── perimetro()
│
├── class Rectangulo(FigurasGeometricas)   ← Herencia
├── class Triangulo(FigurasGeometricas)    ← Herencia
└── class Elipse(FigurasGeometricas)       ← Herencia
```

---

## ▶️ Ejecución

```bash
python figuras_geometricas.py
```

---

## 🖥️ Salida del programa

### Bloque 1 — Instancia de la clase base

```
=================================================================
      Programación Orientada a Objetos — Python
=================================================================

--- Instancia creada:
    alto  (getter) → 12 cm
    ancho (getter) → 20 cm
```

> Se crea un objeto `FigurasGeometricas(12, 20)` y se accede a sus atributos
> privados mediante los **getters** `alto` y `ancho`.

---

### Bloque 2 — Modificación con setters y cálculos

```
--- Modificación de atributos:
    alto  (setter) → 18 cm
    ancho (setter) → 25 cm
    Área base      → 450.00 cm²
    Perímetro base → 86.00 cm
```

> Los atributos se actualizan usando los **setters**, que validan que el valor
> sea positivo antes de asignarlo. Luego se calculan:
>
> - **Área** = alto × ancho = 18 × 25 = **450.00 cm²**
> - **Perímetro** = 2 × (alto + ancho) = 2 × (18 + 25) = **86.00 cm**

---

### Bloque 3 — Validación de errores

```
--- Control de errores:
     Error capturado correctamente: El alto debe ser un valor positivo.
```

> Se intenta asignar `-5` al atributo `alto`. El **setter** detecta el valor
> negativo y lanza un `ValueError`, que es capturado con `try/except`.  
> Esto demuestra el **encapsulamiento** y la protección de los datos.

---

### Bloque 4 — Herencia y polimorfismo

```
=================================================================
        Clases Derivadas y Métodos Sobrescritos
=================================================================

  Rectángulo       | Alto: 14 cm | Ancho: 8 cm  | Área: 112.00 cm² | Perímetro: 44.00 cm
  Triángulo        | Alto: 6 cm  | Base: 11 cm  | Área: 33.00 cm²  | Perímetro: 29.53 cm
  Elipse           | Semi-eje a: 5 cm | Semi-eje b: 9 cm | Área: 141.37 cm² | Perímetro: 44.88 cm
```

Cada clase hija **sobrescribe** los métodos `area()` y `perimetro()` con su propia fórmula:

| Figura      | Fórmula Área                        | Fórmula Perímetro                          |
|-------------|-------------------------------------|--------------------------------------------|
| Rectángulo  | `alto × ancho`                      | `2 × (alto + ancho)`                       |
| Triángulo   | `(base × alto) / 2`                 | `alto + base + hipotenusa`                 |
| Elipse      | `π × semi-eje_a × semi-eje_b`       | Aproximación de Ramanujan                  |

#### Verificación de cálculos:

**Rectángulo** `(14 × 8)`
```
Área      = 14 × 8               = 112.00 cm²
Perímetro = 2 × (14 + 8)         = 44.00 cm
```

**Triángulo** `(base=11, alto=6)`
```
Área      = (11 × 6) / 2         = 33.00 cm²
Hipotenusa = √(6² + 11²)         = √157 ≈ 12.53 cm
Perímetro = 6 + 11 + 12.53       = 29.53 cm
```

**Elipse** `(a=5, b=9)`
```
Área      = π × 5 × 9            = 141.37 cm²
Perímetro ≈ π(a+b)(1 + 3h/(10+√(4-3h)))
          donde h = ((a-b)²)/((a+b)²)
                  = 44.88 cm
```

---

### Bloque 5 — Setter sobre objeto heredado

```
--- Actualización con setter:
  Rectángulo       | Alto: 30 cm | Ancho: 10 cm | Área: 300.00 cm² | Perímetro: 80.00 cm
```

> El rectángulo se redimensiona usando los setters heredados de la clase base.
> Los métodos sobrescritos recalculan automáticamente:
>
> - **Área** = 30 × 10 = **300.00 cm²**
> - **Perímetro** = 2 × (30 + 10) = **80.00 cm**

---

### Bloque 6 — Fin de ejecución

```
=================================================================
      Programa finalizado sin errores
=================================================================
```

---

## 🧠 Conceptos de POO aplicados

| Concepto         | Dónde se aplica                                                      |
|------------------|----------------------------------------------------------------------|
| Encapsulamiento  | Atributos privados `__alto`, `__ancho` con getters y setters         |
| Herencia         | `Rectangulo`, `Triangulo`, `Elipse` extienden `FigurasGeometricas`   |
| Polimorfismo     | Cada clase redefine `area()`, `perimetro()` y `__str__()`            |
| Abstracción      | La clase base define la interfaz común para todas las figuras        |

---

## ✅ Estado

```
Fecha:   06/05/2026
Hora:    16:11:53
Estado:  Programa finalizado sin errores
```
