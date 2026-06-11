# 🛢️ Índice del Tanque Lleno
### Poder adquisitivo real en Argentina medido en litros de nafta (2017–2026)

---

## ¿De qué trata este proyecto?

El precio de la nafta en pesos no dice nada por sí solo.  
Este proyecto responde una pregunta más útil:

> **¿Cuántos litros de nafta súper podés comprar con un día de trabajo al salario mínimo?**

Ese número — el *índice del tanque lleno* — refleja el poder adquisitivo real de forma simple, concreta e inmediata.

---

## Hallazgos principales

| # | Hallazgo |
|---|---|
| 1 | El precio nominal se multiplicó por **83x**: de $20,71 (ene 2017) a $1.724 (ene 2026) |
| 2 | En términos reales, la nafta es **18,8% más barata** que en 2017 — la inflación (+10.150%) superó al aumento de la nafta (+8.227%) |
| 3 | El poder adquisitivo cayó **18,5%**: de 12,9 litros/día en 2017 a 10,6 litros/día en 2026 |
| 4 | El **peor momento** fue julio 2022: 5,2 litros/día |
| 5 | En dólares, el precio promedio fue **U$S 1,07** el litro durante 9 años — notablemente estable |

---

## Estructura del análisis

```
01 — Carga y exploración inicial
02 — Limpieza y preparación (filtrado, merge de 4 datasets)
03 — Evolución nominal del precio
04 — Deflactación: precio real vs. inflación
05 — Índice del tanque lleno ← núcleo del proyecto
06 — Precio en dólares
07 — Conclusiones
```

---

## Datasets utilizados

| Dataset | Fuente | Período |
|---|---|---|
| Precios en surtidor (nafta súper) | Secretaría de Energía de la Nación | Jun 2016 – Jun 2026 |
| IPC Nivel General Nacional | INDEC / datos.gob.ar | Dic 2016 – Abr 2026 |
| Salario Mínimo Vital y Móvil | CNEPySMVyM / datos.gob.ar | Ene 2016 – Ene 2026 |
| Tipo de cambio BNA vendedor | BCRA / apis.datos.gob.ar | Ene 2016 – Feb 2026 |

El rango efectivo del análisis es **enero 2017 → enero 2026** (intersección de los cuatro datasets).

---

## Tecnologías

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Pandas](https://img.shields.io/badge/Pandas-3.0-lightblue)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

---

## Cómo reproducirlo

```bash
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/indice-tanque-lleno
cd indice-tanque-lleno

# 2. Instalar dependencias
pip install pandas numpy matplotlib seaborn jupyter

# 3. Descargar los datasets en la carpeta data/
#    (ver enlaces en la sección Datasets)

# 4. Ejecutar el notebook
jupyter notebook tanque_lleno.ipynb
```

### Estructura de carpetas

```
indice-tanque-lleno/
├── tanque_lleno.ipynb     ← notebook principal
├── README.md
└── data/
    ├── nafta.csv
    ├── ipc.csv
    ├── smvm_historico.csv
    └── tipo_cambio.csv
```

---

## Limitaciones

- Se usó el precio **promedio nacional** de nafta súper. Los precios varían por provincia y empresa.
- El SMVM no representa el salario real de la mayoría de los trabajadores, sino el piso legal.
- El tipo de cambio usado es el **oficial BNA**. El dólar blue daría resultados distintos.
- El congelamiento de precios de combustibles en 2023 genera un pico artificial en el índice (nov 2023 = 14,1 L/día) que no refleja condiciones de mercado normales.

---

## Autor

**Martín** — Desarrollador backend con orientación a análisis de datos  
[GitHub](https://github.com/tu-usuario) · [LinkedIn](https://linkedin.com/in/tu-usuario)
