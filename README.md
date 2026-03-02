<p align="center">
  <img src="repogithub.png" alt="Z.ai Windows Configuration Banner" width="100%">
</p>

# Z.ai Windows Configuration

Configura Claude Code en Windows para utilizar los modelos de Z.ai (GLM-5, GLM-4.7) mediante inyeccion de variables de entorno.

## Modelos Soportados

| Rol de Claude | Modelo Z.ai | Proposito |
| :--- | :--- | :--- |
| **Opus** (Reasoning) | `glm-5` | Tareas complejas de razonamiento y diseno. |
| **Sonnet** (Coding) | `glm-4.7` | Tareas de programacion y edicion de archivos. |
| **Haiku** (Fast) | `glm-4.7-flash` | Tareas rapidas y resumenes. |

## Instalacion

```powershell
# 1. Crea el directorio bin si no existe
New-Item -ItemType Directory -Path "$env:USERPROFILE\bin" -Force

# 2. Copia el template
Copy-Item resources/claude-zai.bat.template $env:USERPROFILE\bin\glm.bat

# 3. Edita el archivo y reemplaza {{API_KEY}} con tu API Key
notepad $env:USERPROFILE\bin\glm.bat

# 4. Asegurate de que bin este en tu PATH
$env:PATH += ";$env:USERPROFILE\bin"
```

## Uso

```cmd
glm
```

## Variables de Entorno

| Variable | Valor |
|----------|-------|
| `ANTHROPIC_BASE_URL` | `https://api.z.ai/api/anthropic` |
| `ANTHROPIC_AUTH_TOKEN` | Tu API Key de Z.ai |

## Obtener API Key

1. Ve a https://open.bigmodel.cn/
2. Crea una cuenta
3. Genera tu API Key

## Licencia

MIT License
