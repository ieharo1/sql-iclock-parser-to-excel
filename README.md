# sql-iclock-parser-to-excel

Script en Python diseñado para **procesar respaldos SQL (.sql)** que contienen sentencias `INSERT INTO iclock_transaction`, extraer los datos, estructurarlos en un DataFrame y **exportarlos a Excel** aplicando filtros personalizados.

Ideal para análisis de **marcaciones de asistencia**, auditorías de tiempo y reportes por empleado.

---

## 🚀 Características

- Carga archivos `.sql` directamente desde **Google Colab**
- Detecta automáticamente las columnas del `INSERT INTO`
- Extrae todas las filas de datos desde múltiples sentencias SQL
- Convierte los datos a un **DataFrame de pandas**
- Soporte para valores `NULL`
- Conversión automática de fechas (`punch_time`)
- Filtro por:
  - Código de empleado (`emp_code`)
  - Rango de fechas
- Exportación final a **Excel (.xlsx)**

---

## 📁 Flujo del proceso

1. Subir archivo `.sql`
2. Leer y analizar sentencias `INSERT INTO iclock_transaction`
3. Extraer columnas y registros
4. Convertir datos a formato estructurado
5. Aplicar filtros personalizados
6. Generar archivo Excel
7. Descargar el archivo filtrado

---

## ⚙️ Requisitos

- Google Colab
- Python 3
- Librerías:
  - `pandas`
  - `re`
  - `google.colab`

*(No requiere conexión a base de datos)*
