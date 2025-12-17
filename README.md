# 📊 Automatización de Reportes Diarios para Comerciantes

Este proyecto consiste en un flujo de trabajo desarrollado en **n8n** diseñado para automatizar el procesamiento y envío de reportes financieros diarios a través de correo electrónico.

## 🚀 Funcionalidades
- **Lectura de Datos:** Conecta con Google Sheets para obtener transacciones y configuraciones de comerciantes.
- **Procesamiento Inteligente:** Calcula ingresos, egresos y saldos netos automáticamente.
- **Generación de HTML:** Crea un reporte visualmente atractivo y personalizado para cada comerciante.
- **Envío Automatizado:** Envía el reporte vía Gmail al destinatario correspondiente.
- **Confirmación:** Actualiza la "Fecha de Último Reporte" en la base de datos maestra tras cada envío exitoso.

## 🛠️ Tecnologías Utilizadas
- [n8n](https://n8n.io/) - Orquestador de la automatización.
- [Google Sheets](https://www.google.com/sheets/about/) - Base de datos para configuración y registros.
- [Gmail API](https://developers.google.com/gmail/api) - Servicio de mensajería.
- [JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript) - Nodos de código para lógica personalizada y formato de moneda.

## 📋 Estructura de la Base de Datos
Para que el flujo funcione, la hoja de Google Sheets debe contener las siguientes columnas:
- `ID_Comerciante`: Identificador único (ej. C001).
- `Nombre_Local`: Nombre comercial del negocio.
- `Email_Destino`: Correo donde se enviará el reporte.
- `Fecha_Ultimo_Reporte`: Fecha que se actualiza automáticamente al finalizar el flujo.

## 📦 Cómo usar
1. Descarga el archivo `Reportes Diarios CORREGIDO.json`.
2. Importa el archivo en tu instancia de n8n.
3. Configura tus credenciales de **Google Sheets** y **Gmail**.
4. ¡Ejecuta el flujo!
