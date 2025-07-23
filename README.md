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

##  Arquitectura del sistema 

#### Parent Workflow: Comienza con un trigger al recibir un mensaje por el bot de telegram, el cual es enviado al nodo del Agente de IA, este agente contiene un prompt en el cual se le pide que actúe como un asesor de ventas, que conteste preguntas de clientes, intente agendar una visita para que lo vean,, y que cree un contacto de ellos en el CRM (HubSpot).

Como tools tiene el MCP Client tool "Inventario" y "Calendario" y "Create or Update contact" para HubSpot

EL último nodo es de Telegram "Send a text message" el cual envía la indicación de contestar a cada mensaje del cliente.

<img width="1147" height="463" alt="image" src="https://github.com/user-attachments/assets/a31ed9a7-fc0b-42a1-ac07-4c2da9d5c019" />

#### Execution Workflows 

MCP Google Sheets: Utilicé Google Sheets ára crear el inventario del lote, en él puse columnas para detallar los vehículos de la mejor manera posible, tomando en cuenta las preguntas que los clientes pudieran hacer. Incluí año del vehículo, KMs, tipo de factura, cantidad de dueños, etc. 

Para las fotos, subí todas a un Google Drive, cada carro tiene su carpeta y dentro sus respectivas imagenes, el URL compartido lo incluí en el inventario para que el agente conteste con éste cuando un cliente pida imagenes.
<img width="539" height="558" alt="image" src="https://github.com/user-attachments/assets/91a35c96-7627-457e-9481-0eb3c7d22297" />

MCP Calendar: Creé el nodo de Execution, con la herramienta de Google calendar de "Crear Evento", para los parametros dejé que la IA los escogiera según el request; Start, End, Summary y Description. 

<img width="547" height="555" alt="image" src="https://github.com/user-attachments/assets/373c9e73-027b-41b9-a90b-12b25a5ba8f4" />


## 📸 Vista previa
