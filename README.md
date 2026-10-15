# VisualNotes AI

Plataforma web universitaria que convierte **audios de clase**, **fotos de pizarra/apuntes** y **texto** en un kit de estudio completo generado con IA: transcripción, contenido limpio, apuntes, palabras clave, mapa conceptual, resumen, quiz y documentos **Markdown** exportables a **PDF**.

> Proyecto académico del **Grupo 4 — Universidad Cenfotec**.
> Repositorio oficial: https://github.com/nexusdigitalsolutionspa-maker/visualnotesia

---

## 📚 Qué genera

A partir de una sola fuente (audio, imagen o texto):

- 📄 **Transcripción completa** (literal, sin omitir contenido)
- 🧹 **Contenido limpio y ordenado** por temas
- 📝 **Apuntes estructurados** en Markdown
- 🔑 **Palabras clave** para repaso y búsqueda
- 🗺️ **Mapa conceptual** en Mermaid (editable y exportable a SVG/PNG)
- 📌 **Resumen ejecutivo** y conceptos fundamentales
- ❓ **Quiz de autoevaluación** con respuestas
- 🔗 **Recursos recomendados** (videos, sitios y blogs)
- 📥 **Documento `.md`** listo para Obsidian/Notion y **exportación a PDF**

---

## 🧱 Stack tecnológico

| Capa | Tecnología |
|------|------------|
| Backend | **Python 3.12**, **FastAPI**, **Uvicorn** |
| Base de datos | **SQLite** + **SQLAlchemy** (almacenamiento local) |
| IA | **Google Gemini** vía `google-genai` |
| Frontend | HTML5, CSS3 y **JavaScript** vanilla |
| Diagramas | **Mermaid.js** |
| Markdown | **marked.js** |
| 3D (landing) | **Three.js** |
| Contenedores | **Docker** / **docker-compose** |
| Seguridad | `bcrypt` (hash), cabeceras HTTP, rate limiting, CSP |

---

## 📁 Estructura del proyecto

```
.
├── app.py                     # API FastAPI (rutas y seguridad)
├── database.py                # Modelos SQLAlchemy y conexión SQLite
├── gemini_service.py          # Integración con Google Gemini
├── requirements.txt           # Dependencias de Python
├── templates/
│   ├── index.html             # Aplicación principal
│   └── landing.html           # Página informativa / marketing
├── static/
│   ├── css/style.css
│   └── js/ (app.js, audio.js, diagram.js, auth.js)
├── marketing/                 # Scripts de capturas para el video
├── Dockerfile
├── docker-compose.yml
├── render.yaml
├── .env.example
└── README.md
```

---

## 🔑 Cómo conseguir la API key de Gemini

La aplicación usa **Google Gemini** para el análisis de contenido. Necesitas una clave de API (hay un **plan gratuito**).

1. Entra a **Google AI Studio**: https://aistudio.google.com/app/apikey
2. Inicia sesión con tu cuenta de Google.
3. Pulsa **“Create API key”** (Crear clave de API).
4. Elige un proyecto de Google Cloud (o deja que se cree uno nuevo) y copia la clave generada.
5. Guarda esa clave como variable de entorno `GEMINI_API_KEY` (ver más abajo). **Nunca** la escribas en el código ni la subas al repositorio.

> 💡 Documentación oficial: https://ai.google.dev/gemini-api/docs

---

## ⚙️ Configuración

Copia el archivo de ejemplo y completa tus valores:

```bash
cp .env.example .env
```

Edita `.env`:

```env
GEMINI_API_KEY=tu_clave_de_gemini
ENABLE_AUTH=false
RATE_LIMIT_PER_MINUTE=20
MAX_UPLOAD_MB=25
```

### Variables de entorno

| Variable | Descripción | Default |
|----------|-------------|---------|
| `GEMINI_API_KEY` | Clave de la API de Gemini (**requerida** para la IA) | — |
| `GEMINI_MODELS` | Modelos separados por coma, con fallback | `gemini-flash-latest,...` |
| `ENABLE_AUTH` | Activa el inicio de sesión (futuro) | `false` |
| `ALLOWED_ORIGINS` | Orígenes CORS permitidos (coma). Vacío = mismo origen | — |
| `RATE_LIMIT_PER_MINUTE` | Límite de peticiones a la IA por IP | `20` |
| `MAX_UPLOAD_MB` | Tamaño máximo de archivo subido | `25` |
| `VISUALNOTES_DB` | Ruta de la base de datos SQLite | `./visualnotes.db` |

---

## 💻 Ejecución local (sin Docker)

```bash
# 1. Crear entorno virtual (recomendado)
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/macOS:
source .venv/bin/activate

# 2. Instalar dependencias
pip install -r requirements.txt

# 3. Configurar variables de entorno
cp .env.example .env   # y edita GEMINI_API_KEY

# 4. Iniciar el servidor
python -m uvicorn app:app --host 127.0.0.1 --port 8000
```

Abre:
- Landing (página de inicio): http://127.0.0.1:8000
- Aplicación: http://127.0.0.1:8000/app

---

## 🐳 Ejecución con Docker

```bash
# Construir y levantar
docker compose up --build

# Abrir en: http://localhost:8000
```

O manualmente:

```bash
docker build -t visualnotes-ai .
docker run --rm -p 8000:8000 --env-file .env \
  -v "$(pwd)/data:/app/data" visualnotes-ai
```

> El volumen `./data` conserva la base de datos SQLite entre reinicios.

---

## 🚀 Despliegue

### Render (recomendado, incluye `render.yaml`)

1. Sube el repositorio a GitHub.
2. En [Render](https://render.com) crea un **New → Web Service** y conecta el repo.
3. Render detecta el `Dockerfile` automáticamente.
4. En **Environment**, agrega `GEMINI_API_KEY` con tu clave.
5. Deploy. El healthcheck está en `/api/health`.

> ⚠️ En planes gratuitos el sistema de archivos es efímero: la base SQLite se reinicia con cada deploy. Para persistir, monta un disco persistente o usa un plan con volumen.

### Railway / Fly.io / VPS

- **Railway:** “Deploy from GitHub repo” → detecta el Dockerfile → añade `GEMINI_API_KEY`.
- **Fly.io:** `fly launch` (usa el Dockerfile) y `fly volumes create data` para persistencia; monta el volumen en `/app/data`.
- **VPS con Docker:** clona el repo, crea `.env` y ejecuta `docker compose up -d --build`.

---

## 🔒 Seguridad

- La **API key de Gemini** se lee **solo** de variables de entorno; nunca está en el código.
- El archivo `.env` está en `.gitignore` (no se sube).
- Cabeceras de seguridad: `CSP`, `X-Frame-Options`, `X-Content-Type-Options`, `Referrer-Policy` y `Permissions-Policy`.
- **Rate limiting** por IP en el endpoint de IA.
- **Límite de tamaño** de archivos subidos.
- Los errores internos no se exponen al cliente.
- El **inicio de sesión está deshabilitado** por defecto (modo local). Los endpoints de cuentas solo se activan con `ENABLE_AUTH=true`.

¿Encontraste un problema de seguridad? Revisa [SECURITY.md](SECURITY.md) antes de publicarlo.

---

## 🐞 Reportar problemas

Usa la pestaña **[Issues](https://github.com/nexusdigitalsolutionspa-maker/visualnotesia/issues)** del repositorio:

- 🐛 **Bug report** — algo no funciona.
- ✨ **Feature request** — ideas y mejoras.

---

## 🤝 Contribuir

Las contribuciones son bienvenidas. Lee [CONTRIBUTING.md](CONTRIBUTING.md) para saber cómo proponer cambios.

---

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Ver [LICENSE](LICENSE).
