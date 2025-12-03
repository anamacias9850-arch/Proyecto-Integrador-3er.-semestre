# 📊 Proyecto AEMA: Modelo de Inclusión Laboral para Adultos Mayores

## 📝 Descripción del Proyecto
Este proyecto tiene como objetivo determinar la probabilidad de **inclusión laboral formal** en adultos mayores que buscan reincorporarse al mercado de trabajo. [cite_start]Se fundamenta en un análisis de **Regresión Logística Binaria**, modelando el resultado dicotómico entre Empleo Formal (con prestaciones) vs. Informal[cite: 1049, 1050].

[cite_start]El estudio identifica qué factores (Edad, Escolaridad, Género, Discapacidad) actúan como barreras o facilitadores para el acceso a empleos dignos[cite: 1051].

## 📂 Estructura del Repositorio
* `3.0 BASE DATOS EN PROYECTO _AEMA.csv`: Base de datos anonimizada utilizada para el entrenamiento y pruebas.
* `REGRESION_LOGISTICA.pdf`: Informe detallado con el marco teórico y análisis inferencial completo.
* `notebook_analisis.ipynb`: Código fuente del entrenamiento y optimización del modelo.

## ⚙️ Metodología y Evaluación del Modelo
Se entrenó un modelo de clasificación binaria. A continuación se presenta el rendimiento inicial y la estrategia de optimización aplicada para maximizar el impacto social del proyecto.

### 1. Rendimiento Inicial (Umbral 0.5)
| Métrica | Valor | Interpretación |
| :--- | :---: | :--- |
| **Accuracy** | 85.2% | El modelo clasifica correctamente el 85% de los casos globales. |
| **Precision** | 82.3% | Alta confiabilidad cuando predice una oportunidad formal. |
| **Recall** | **80.1%** | Detecta a 8 de cada 10 candidatos aptos, pero pierde un 20%. |

> **Diagnóstico:** Aunque la exactitud es alta, un Recall del 80% implica que 52 personas vulnerables (Falsos Negativos) no fueron detectadas correctamente por el modelo estándar.

### 2. Optimización Estratégica (Threshold Tuning)
Para reducir el riesgo de exclusión social, ajustamos el **Umbral de Decisión** del modelo.

![Curva Precision-Recall](curva_optimizacion_python.png)
*(Gráfica generada en Python mostrando el cruce óptimo)*

**Ajuste:** Se redujo el umbral de `0.50` a `0.35`.
* ✅ **Nuevo Recall: ~92%** (Se rescatan la mayoría de los casos que antes eran ignorados).
* 🔻 **Nueva Precisión:** Disminuye levemente, aceptando un mayor número de validaciones manuales a cambio de no dejar a nadie atrás.

### 3. Matriz de Confusión Final
La matriz resultante tras la optimización:

![Matriz de Confusión](Confusion_del_modelo.png)

---

## 🔍 Hallazgos Clave (Insights del Negocio)
[cite_start]Basado en los *Odds Ratios* (OR) extraídos del análisis inferencial[cite: 1154], se identificaron los siguientes determinantes:

### ✅ Facilitadores (Lo que ayuda)
* [cite_start]**Habilidades Digitales (OR 2.21):** Saber computación es el predictor más potente, aumentando la probabilidad de empleo formal en un **121%**[cite: 1159, 1160].
* [cite_start]**Escolaridad (OR 1.67):** Cada nivel educativo adicional incrementa la probabilidad de éxito en un **66.6%**[cite: 1161, 1162].

### ⚠️ Barreras (Lo que frena)
* [cite_start]**Discapacidad (OR 0.51):** Tener una discapacidad reduce la probabilidad de empleo formal en un **49.1%**, evidenciando la necesidad de políticas inclusivas[cite: 1165].
* [cite_start]**Brecha de Género (OR 0.52):** Ser mujer disminuye las probabilidades de contratación formal en un **48.5%** comparado con los hombres[cite: 1166].
* [cite_start]**Edadismo (OR 0.94):** Por cada año adicional de edad, la probabilidad de éxito cae un **5.6%**[cite: 1167, 1168].

## 💡 Recomendaciones de Política
1.  [cite_start]**Priorización Digital:** Reenfocar presupuestos hacia la alfabetización digital funcional, dado su alto retorno de inversión social[cite: 1191, 1192].
2.  [cite_start]**Perspectiva de Género:** Implementar programas de mentoría y cuotas de vinculación para mitigar la brecha del 48% que afecta a las mujeres[cite: 1194, 1195].
3.  [cite_start]**Certificación de Experiencia:** Combatir el edadismo mediante certificaciones que validen la experiencia acumulada ("soft skills") como activo tangible[cite: 1198, 1199].

---
*Desarrollado como parte de la iniciativa de Vinculación Productiva 2024-2025.*
