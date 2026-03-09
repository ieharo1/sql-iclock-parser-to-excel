# 📊 SQL Iclock Parser to Excel

Herramienta profesional para procesar archivos SQL de respaldo del sistema de control de asistencia iClock y exportar a Excel con formato profesional. Desarrollado por **Isaac Esteban Haro Torres**.

---

## 📝 Descripción

Sistema especializado para extraer, transformar y cargar datos de asistencia desde respaldos SQL del sistema iClock (biométricos y tarjetas) a formatos analíticos.

### ¿Qué hace este proyecto?

- **Parseo de SQL**: Procesa archivos SQL de respaldo de iClock
- **Extracción de transacciones**: Extrae check-in/check-out de empleados
- **Transformación de datos**: Limpia, normaliza y enriquece datos
- **Exportación Excel**: Múltiples hojas con formato profesional
- **Reportes automatizados**: Genera reportes de asistencia listos para HR
- **Detección de anomalías**: Encuentra registros duplicados o inconsistentes

---

## ✨ Características Principales

| Característica | Descripción |
|----------------|-------------|
| 📂 **Multi-formato SQL** | INSERT statements, dumps completos |
| 👥 **Gestión de empleados** | Crea/actualiza roster de empleados |
| ⏰ **Procesamiento de horario** | Calcula horas trabajadas, tardanzas |
| 📅 **Reportes por periodo** | Diario, semanal, quincenal, mensual |
| 🎯 **Detección de anomalías** | Registros duplicados, horarios atípicos |
| 📊 **Excel profesional** | Múltiples hojas, formatos, gráficos |

---

## 🛠️ Stack Tecnológico

- **Lenguaje**: Python 3.10+
- **Procesamiento SQL**: sqlparse, regex
- **Datos**: Pandas, NumPy
- **Excel**: openpyxl, xlsxwriter
- **Fechas**: dateutil, datetime
- **Entorno**: Jupyter / CLI

---

## 🚀 Instalación y Uso

### Instalación

```bash
pip install pandas openpyxl xlsxwriter sqlparse
```

### Uso básico

```python
from iclock_parser import IclockParser

# Inicializar parser
parser = IclockParser()

# Cargar archivo SQL
parser.cargar_sql("respaldo_iclock.sql")

# Procesar transacciones
transacciones = parser.procesar_transacciones()

# Generar reporte Excel
parser.generar_excel(
    "reporte_asistencia.xlsx",
    periodo="Enero 2026",
    incluir_graficos=True
)
```

### Procesamiento avanzado

```python
# Con configuración personalizada
parser = IclockParser(
    timezone="America/Guayaquil",
    hora_entrada="08:00",
    hora_salida="18:00",
    tolerancia_minutos=15,
    empresa="Mi Empresa"
)

# Agregar empleados desde otro fuente
parser.agregar_empleados("empleados.xlsx")

# Generar múltiples reportes
reportes = parser.generar_reportes(
    tipo=["diario", "semanal", "mensual"],
    formato="excel"
)
```

---

## 📊 Estructura del Reporte Excel

```
reporte_asistencia.xlsx
├── 📋 Resumen          - KPIs generales
├── 👥 Empleados        - Lista completa de empleados
├── 📅 Diario           - Asistencia por día
├── ⏱️ Semanal         - Horas por semana
├── 📆 Mensual         - Resumen mensual
├── ⚠️ Anomalías       - Registros problemáticos
└── 📈 Gráficos        - Visualizaciones
```

---

## 📁 Estructura del Proyecto

```
sql-iclock-parser-to-excel/
├── Extraer_Datos_SQL_con_Python.ipynb
├── iclock_parser/
│   ├── __init__.py
│   ├── sql_parser.py
│   ├── processor.py
│   ├── excel_generator.py
│   └── reports.py
├── config/
│   └── settings.json
├── output/
│   └── reportes_generados/
└── README.md
```

---

## 💡 Casos de Uso

1. **RRHH**: Reportes de asistencia para nómina
2. **Control de horario**: Verificación de entradas/salidas
3. **Productividad**: Análisis de horas trabajadas
4. **Cumplimiento**: Registros para auditorías
5. **Biometría**: Procesamiento de datos de terminales

---

## 📈 Métricas Calculadas

| Métrica | Descripción |
|---------|-------------|
| Horas trabajadas | Total de horas en el período |
| Tardanzas | Días que llegó después de hora |
| Salidas temprano | Días que salió antes de hora |
| Faltas | Días sin registro |
| Extras | Horas después del horario |
| Puntualidad | % de días puntuales |

---

## 🔧 Formato de Salida

```python
# Configurar formato Excel
formato = {
    'header': {'bold': True, 'bg_color': '#2563eb', 'font_color': 'white'},
    'currency': {'num_format': '$#,##0.00'},
    'date': {'num_format': 'yyyy-mm-dd'},
    'conditional': True  # Resaltar anomalías
}

parser.generar_excel("reporte.xlsx", **formato)
```

---

## 📋 Ejemplo de Datos Extraídos

```python
# Transacciones procesadas
  timestamp            employee_id  nombre          tipo      verifica
0 2026-01-15 08:05:00  001          Juan Pérez      IN        Huella
1 2026-01-15 18:02:00  001          Juan Pérez      OUT       Huella
2 2026-01-16 08:12:00  001          Juan Pérez      IN        Tarjeta
3 2026-01-16 17:45:00  001          Juan Pérez      OUT       Rostro
```

---

## ⚠️ Notas Importantes

- El archivo SQL debe contener las tablas: userinfo, checkinout
- Soporta formato de fecha: YYYY-MM-DD y DD/MM/YYYY
- Recomendable hacer backup antes de procesar archivos grandes

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
