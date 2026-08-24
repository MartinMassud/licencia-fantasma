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
- Sin base de datos, conexión bancaria ni credenciales financieras.
- Datos conservados únicamente durante la sesión de Streamlit.
