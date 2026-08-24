# Licencia Fantasma

MVP para encontrar señales de aumentos, duplicaciones, suscripciones sospechosas y renovaciones próximas en gastos de software/SaaS.

## Ejecutar localmente

```bash
python -m venv .venv
pip install -r requirements.txt
streamlit run app.py
```

Creá `.streamlit/secrets.toml` con tu clave de Groq:

```toml
GROQ_API_KEY = "tu_clave"
```

También podés definir la variable de entorno `GROQ_API_KEY`.

## Alcance

- Entrada por texto, CSV, PDF o imagen/factura.
- Extracción de texto y OCR visual mediante Groq.
- Normalización, recurrencias, señales y explicaciones en español.
- Acciones sugeridas y recordatorios preparados para WhatsApp o email.
- Proyección mensual y anual con aumentos calculados sobre la diferencia.
- Historial por períodos con comparación equivalente de los mismos servicios.
- Campos opcionales para confirmar periodicidad, próxima renovación, último uso, estado de uso y proyecto.
- Separación visible entre evidencia declarada e inferencias de IA, con nivel de confianza.
- Stack actual sin duplicar cobros históricos y ranking por impacto, urgencia y confianza.
- Resumen de licencias activas/inactivas declaradas y renovaciones dentro de 30 días.
- Agrupación por función para detectar posibles solapamientos entre licencias similares y ver su costo mensual conjunto.
- Carga simultánea de múltiples CSV, PDF o imágenes y comparación histórica entre facturas, incluso con encabezados CSV repetidos.
- Normalización y compresión de imágenes antes del OCR para mejorar la lectura de capturas grandes.
- Continuación parcial: si un archivo no se puede leer, analiza las demás fuentes válidas y avisa cuál fue omitido.
- Potencial conservador: renovaciones y señales para revisar no se cuentan como ahorro; solo aumentos comprobados, falta de uso con evidencia y el menor costo de una duplicación explícita.

## CSV con evidencia opcional

El formato mínimo sigue siendo `servicio,monto,fecha`. Para confirmar señales en lugar de inferirlas:

```csv
servicio,monto,fecha,periodicidad,proxima_renovacion,ultimo_uso,estado_uso,proyecto
ELEMENTOR PRO,99,2026-08-10,anual,2026-09-03,2026-08-01,activo,Web cliente
ENVATO ELEMENTS,16.50,2026-08-07,mensual,2026-09-07,2026-05-10,inactivo,Assets
```

Sin esos campos, las duplicaciones y el uso probable se muestran explícitamente como inferencias, no como hechos confirmados.
- Sin base de datos, conexión bancaria ni credenciales financieras.
- Datos conservados únicamente durante la sesión de Streamlit.

