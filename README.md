# Licencia Fantasma

MVP para detectar aumentos, duplicaciones, suscripciones sospechosas y renovaciones próximas en gastos de software/SaaS.

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

- Entrada por texto o CSV.
- Análisis mediante un único llamado a Groq.
- Sin base de datos, conexión bancaria, PDF u OCR.
- Datos conservados únicamente durante la sesión de Streamlit.

