---
name: z.ai configuration
description: Configura y lanza Claude Code utilizando los modelos de Z.ai (GLM-5, GLM-4.7) mediante inyección de variables de entorno.
---

# Z.ai Configuration Skill

Esta skill permite configurar la herramienta oficial `claude-code` de Anthropic para que utilice los modelos de Z.ai mediante una redirección de API.

## Requisitos Previos

- **Node.js**: Versión 18 o superior.
- **Claude Code**: Instalado globalmente (`npm install -g @anthropic-ai/claude-code`).

## Configuración de Modelos

Esta configuración mapea los roles predeterminados de Claude a los siguientes modelos de Z.ai:

| Rol de Claude | Modelo Z.ai | Propósito |
| :--- | :--- | :--- |
| **Opus** (Reasoning) | `glm-5` | Tareas complejas de razonamiento y diseño. |
| **Sonnet** (Coding) | `glm-4.7` | Tareas de programación y edición de archivos. |
| **Haiku** (Fast) | `glm-4.7-flash` | Tareas rápidas y resúmenes. |

## Instrucciones de Implementación

Para configurar un entorno con esta skill, se debe crear un script de lanzamiento (batch en Windows) que defina las siguientes variables de entorno:

### Variables de Entorno Clave

- `ANTHROPIC_BASE_URL`: `https://api.z.ai/api/anthropic`
- `ANTHROPIC_AUTH_TOKEN`: Tu API Key de Z.ai.
- `ANTHROPIC_DEFAULT_OPUS_MODEL`: `glm-5`
- `ANTHROPIC_DEFAULT_SONNET_MODEL`: `glm-4.7`
- `ANTHROPIC_DEFAULT_HAIKU_MODEL`: `glm-4.7-flash`

## Uso de Recursos

La skill incluye una plantilla de script en `resources/claude-zai.bat.template` que puede ser desplegada automáticamente en el directorio del usuario.

### Pasos de Configuración:
1. Instalar dependencias globales de npm.
2. Generar el script `.bat` con las credenciales del usuario.
3. Ejecutar el script para iniciar la interfaz de Claude Code.

> [!IMPORTANT]
> Esta configuración redirige todo el tráfico de la CLI de Claude Code a los servidores de Z.ai. Asegúrate de que tu API Key tenga saldo y permisos suficientes para los modelos GLM.
