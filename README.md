# Lote-automatizado

#  Sistema Automatizado para Lote de Autos

Este proyecto es un sistema inteligente que conecta un bot conversacional (Telegram) con un inventario de autos (Google Sheets), Google Calendar, HubSpot CRM y documentos informativos. Fue diseñado para automatizar la atención al cliente en un lote de seminuevos, generar leads calificados y gestionar tareas operativas desde una sola plataforma.

Este proyecto lo hice para un cliente dueño de un lote de autos que buscaba digitalizar su negocio en el area comercial. La solución que le presenté fue enfocda al registro de clientes potenciales y a la atención/ventas por medios digitales. Para esto, construí un bot de IA automatizado y conectado con MCP, dándole conocimiento sobre el inventario del lote, la habilidad de agedar citas y que lograra conversar con los clientes para registrarlos en un CRM.

<img width="1255" height="513" alt="image" src="https://github.com/user-attachments/assets/3a282c06-ddf2-455e-bdaf-b9aefa8e0cb0" />

## Tabla de contenido




##  Funcionalidades principales

- Chatbot inteligente con IA (OpenAI) entrenado para actuar como asesor de ventas.
- Consulta en tiempo real del inventario (vía Google Sheets).
- Consulta documentos para responder sobre créditos, ubicación, horarios, etc.
- Registro automático de leads en HubSpot desde la conversación.
- Envío de recordatorios y eventos al calendario de Google.

##  Tecnologías utilizadas

- [n8n (cloud)](https://n8n.io/)
- [OpenAI](https://platform.openai.com/)
- [Telegram Bot API](https://core.telegram.org/bots)
- [HubSpot Developer Portal](https://developers.hubspot.com/)
- [Google Cloud Console](https://console.cloud.google.com/)
- Google Sheets / Docs / Calendar
- Docker y n8n local-para testing


##  Estructura

- `/workflows`: JSONs exportados desde n8n para importar rápidamente todos los flujos.
- `/docs`: Guías de configuración, credenciales, estructura del bot.
- `/data`: Inventarios, documentos de info general y ejemplos de uso.
- `/assets`: Imágenes, capturas o videos demostrativos.
- `/scripts`: Notas técnicas o comandos útiles.

##  Estado actual

✅ Integraciones funcionales:
- Sheets (Inventario)
- Telegram (Chat dinámico)
- OpenAI (Agente IA)
- HubSpot (CRM)
- Google Calendar (Eventos desde conversación)


## 📸 Vista previa

![Demo Conversación](assets/demo-conversacion-telegram.mp4)

---


