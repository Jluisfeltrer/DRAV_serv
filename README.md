# 📘 DRA API – Data Retrieval Agent

**Versión:** 1.0.0  
**Descripción:** API desarrollada con FastAPI que expone un agente inteligente de recuperación de datos (DRA), impulsado por modelos de lenguaje Cohere. Permite realizar consultas analíticas mediante endpoints accesibles para integraciones web o backend.

---

## 🚀 Características

- 🔍 Procesamiento de consultas vía LLM (Cohere)
- 🧠 Endpoints para DRA y AIVA (interfaz alternativa)
- ⚙️ Modularidad con integración de `bot.py` y `bot_direct.py`
- 🌐 Interfaz RESTful con documentación automática vía Swagger

---

## 📦 Estructura del proyecto



├── main.py               # Archivo principal con definición de endpoints 
├── bot.py                # Lógica de respuesta del agente DRA 
├── bot_direct.py         # Funciones auxiliares o directas del bot 
├── .env                  # Variables de entorno (API keys, configuración) 
├── requirements.txt      # Dependencias del proyecto


---

## 🧩 Endpoints disponibles

| Método | Ruta             | Descripción                                                                 |
|--------|------------------|------------------------------------------------------------------------------|
| GET    | `/`              | Mensaje de bienvenida y guía básica                                         |
| POST   | `/dra_response`  | Procesa una consulta usando el agente DRA                                   |
| POST   | `/aiva_response` | Alternativa al endpoint anterior (puede usarse para variantes o interfaces) |


### 📥 Ejemplo de solicitud POST

```json
POST /dra_response
Content-Type: application/json

{
  "query": "¿Cuál es el PIB de Venezuela en 2023?"
}


📤 Ejemplo de respuesta

{
  "response": "El PIB estimado de Venezuela en 2023 fue de..."
}


---

## ⚙️ Instalación y ejecución

# Clona el repositorio
git clone https//github.com/Jluisfeltrer/DRAV3.git
cd dra-api

# Instala dependencias
pip install -r requirements.txt

# Carga variables de entorno
cp .env.example .env  # y edita con tus claves Cohere, etc.

# Ejecuta el servidor
uvicorn main:app --reload


---

📚 Requisitos

• Python 3.9+
• FastAPI
• Cohere SDK
• python-dotenv


---

🛠️ Notas de desarrollo

• El endpoint `/aiva_response` puede adaptarse para interfaces personalizadas (e.g. AVA).
• Se recomienda modularizar `UserQuery` y los endpoints en un archivo `routers/` para escalabilidad.
• La lógica de `get_dra_response()` puede extenderse con validaciones, logging o contexto conversacional.


---

📄 Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más detalles.

---

🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar la API, abrir issues o proponer nuevas funcionalidades, ¡no dudes en participar!

---

📬 Contacto

Para dudas o soporte, puedes contactar a [jluisfeltrer.pm@gmail.com].
