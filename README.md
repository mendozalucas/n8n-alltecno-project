# 🤖 Agente de Ventas Automatizado para WhatsApp – n8n

Este proyecto implementa un **agente de inteligencia artificial para atención al cliente y ventas automatizadas a través de WhatsApp**, desarrollado con **n8n** e integrado con múltiples servicios externos.

El sistema fue diseñado para responder consultas de clientes para el emprendimiento **AllTecno**. También, el sistema brinda información sobre productos, verifica stock y registra órdenes de compra automáticamente.

---

# Objetivo del Proyecto

El objetivo de este proyecto fue resolver un **caso real del negocio _AllTecno_ ubicado en Montevideo, Uruguay**, donde se buscaba **automatizar la atención de clientes en WhatsApp para la venta de hardware**.

Mediante esta automatización se logra:

- Reducir el tiempo de atención humana
- Responder consultas frecuentes de forma automática
- Verificar stock de productos en tiempo real
- Registrar órdenes de compra sin intervención manual
- Mejorar la experiencia del cliente

De esta forma, el personal del negocio no necesita estar pendiente constantemente del chat de atención al cliente.

---

# Tecnologías Utilizadas

El sistema integra múltiples servicios y tecnologías:

### 📱 WhatsApp API
Se utilizó **YCLOUD** para la integración con la API de WhatsApp, gestionando:

- Recepción de mensajes de clientes
- Envío de respuestas generadas por el agente

---

### Google APIs
Se integraron:

- **Google Sheets** para gestión de productos y órdenes de compra
- **Google Docs** para almacenamiento de información del negocio y envíos

La autenticación y gestión de permisos se realizó mediante **Service Accounts de Google**.

---

### Inteligencia Artificial

Se implementó un **Agente de IA utilizando el modelo Google Gemini 3.0**, encargado de:

- Interpretar los mensajes de los clientes
- Resolver dudas sobre productos
- Consultar herramientas externas
- Detectar intención de compra
- Agregar órdenes de compra

---

### Base de Datos

Se integró **Supabase** utilizando **PostgreSQL** para almacenar la **memoria del chat**, permitiendo mantener el contexto de la conversación entre mensajes.

---

### Procesamiento de Datos

Los datos provenientes de **Google Sheets** fueron formateados y procesados utilizando **JavaScript dentro de n8n**, facilitando su posterior análisis por parte del agente.

---

# Funcionamiento del Workflow

El flujo de automatización funciona de la siguiente manera:

1. **Recepción del mensaje**
   - El cliente envía un mensaje por WhatsApp.
   - YCLOUD envía el evento a n8n mediante un **Webhook**.

2. **Procesamiento por el agente IA**
   - El agente recibe:
     - El **mensaje del cliente**
     - La **información de productos almacenada en Google Sheets**

3. **Uso de herramientas del agente**

   El agente cuenta con dos fuentes principales de información:

   **Google Docs**
   - Información de la empresa
   - Métodos de envío
   - Políticas del negocio

   **Google Sheets**
   - Catálogo de productos
   - Descripción de hardware
   - Verificación de stock disponible

4. **Resolución de dudas**
   - El agente responde preguntas del cliente utilizando únicamente los datos disponibles.

5. **Detección de intención de compra**
   - Si el agente detecta que el cliente desea comprar un producto:
     - Solicita los datos necesarios al cliente.

6. **Registro de orden de compra**
   - El agente agrega automáticamente una nueva fila en el **Google Sheets de órdenes de compra** con la información proporcionada por el cliente y el producto.

---

# Demostración

En este repositorio se incluye un **video demostrativo** donde se muestra:

- La conversación entre el cliente y el agente en WhatsApp
- El comportamiento del agente IA
- El registro automático de la orden de compra en Google Sheets generado a partir de la interacción con el cliente

---
