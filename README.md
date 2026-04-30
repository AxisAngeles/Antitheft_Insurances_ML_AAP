# 📋 Venta de Seguros Antirrobos mediante Machine Learning

## 🎯 Contexto y Propuesta

En el sector financiero, la protección contra robo es una necesidad crítica. Este proyecto desarrolla un **modelo predictivo de aprendizaje automático** para identificar candidatos óptimos a asegurar en un producto de protección antirrobo. El sistema analiza el perfil crediticio de clientes existentes para pronosticar la viabilidad de nuevas colocaciones, optimizando el riesgo y maximizando la cobertura.

## 📊 Dataset Utilizado

- **Volumen**: 27,694 registros de clientes
- **Dimensionalidad**: 13 características (territoriales, demográficas y financieras)
- **Variable Objetivo**: FLAG_SS (binaria: contratación de seguro)
- **Desequilibrio de Clases**: 97.9% clase negativa / 2.1% clase positiva

## 📁 Estructura del Proyecto
1. Carga y Exploración de Datos
2. Análisis Exploratorio (EDA)
3. Limpieza y Tratamiento de datos
4. Balanceo de Datos (Undersampling, Oversampling, SMOTE)
5. Entrenamiento de Modelos
6. Evaluación Comparativa
7. Selección del Modelo Óptimo (XGBoost)

## 🔧 Proceso de Preparación de Datos

### Limpieza y Transformación
- **Imputación de valores nulos**: Utilización de valores centrales (ANTIGUEDAD_MES, SUELDO_ESTIMADO) y K-vecinos para variables categóricas
- **Codificación**: Transformación de variables categóricas (MARCA, REGIÓN, SEXO, SEGMENTO) a representación numérica
- **Selección de variables**: Aplicación de SelectKBest para identificar 7 características más relevantes

## 🤖 Modelos de Aprendizaje Automático Evaluados

Se entrenaron y evaluaron cuatro algoritmos distintos:

| Algoritmo | F1-Score | Precision | Recall | Fortaleza Principal |
|-----------|----------|-----------|--------|-------------------|
| **Decision Tree** | 0.07 | 0.04 | 0.52 | Interpretabilidad alta |
| **Random Forest** | 0.02 | 0.04 | 0.67 | Estabilidad y reducción de overfitting |
| **XGBoost** | **0.3976** | **0.40** | **0.40** | Capacidad predictiva superior |
| **RNA (MLP)** | 0.08 | 0.04 | 0.58 | Flexibilidad en patrones complejos |

### 📊 Comparativa Visual: Matrices de Confusión
<img width="993" height="248" alt="ConfussionMatrix" src="https://github.com/user-attachments/assets/96447316-9a27-452f-a79d-bad79d4501fd" />

## 🏆 Técnica Seleccionada: XGBoost

**Justificación**: XGBoost demostró el mejor equilibrio entre precisión y generalización en el conjunto de prueba, con un **F1-Score de 0.3976** en la configuración con balanceo SMOTE. El modelo captura patrones complejos en el comportamiento crediticio de clientes con riesgo bajo de sobreajuste.

## 💡 Impacto Empresarial

1. **Segmentación Inteligente**: Identificación automatizada de perfiles de alto valor para seguros antirrobos
2. **Reducción de Costos**: Optimización del gasto en campañas comerciales enfocadas
3. **Mitigación de Riesgo**: Selección data-driven de clientes con mayor capacidad de pago
4. **Escalabilidad**: Modelo entrenado listo para producción en pipeline automatizado

