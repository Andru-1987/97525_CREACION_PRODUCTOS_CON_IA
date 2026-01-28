## MCP --> Firebase Studio AI

Este módulo introduce **MCP (Model Copilot)**, una herramienta que permite integrar modelos de IA en tus aplicaciones mediante Supabase. A continuación se muestra cómo configurar el servidor MCP usando Supabase y los pasos básicos para su uso.

- [Documentacion oficial](https://supabase.com/blog/mcp-server)

```json
{
  "mcpServers": {
    "supabase": {
      "command": "npx",
      "args": [
        "-y",
        "@supabase/mcp-server-supabase@latest",
        "--access-token",
        "sbp_12a6e878d08cab62651903f8e0f6337f006c9810"
      ]
    }
  }
}
```

## Antigravity --> SupaBase MCP

- **Objetivo**: Facilitar la interacción con el servidor MCP directamente desde el entorno de desarrollo.
- **Ventajas**: Simplifica la configuración y permite pruebas rápidas de los modelos de IA.
- **Requisitos**: Tener una cuenta en Supabase y el token de acceso configurado.
- Steps directamente en el entorno


## VSCode --> SupaBase MCP

- **Configuración**: Añade el archivo `.vscode/mcp.json` para que VSCode reconozca el servidor.
- **Uso**: Permite lanzar prompts a tu modelo directamente desde el editor.
- **Ejemplo**: Ver el bloque JSON a continuación para la configuración básica.

- .vscode/mcp.json`

```json
{
  "servers": {
    "supabase": {
      "type": "http",
      "url": "https://mcp.supabase.com/mcp"
    }
  }
}
```

## Github --> MCP

- **Integración**: Conecta tu repositorio de GitHub con el servidor MCP para obtener sugerencias de código basadas en IA.
- **Pasos**: Sigue la guía oficial de GitHub Copilot para habilitar el MCP.
- **Beneficio**: Mejora la productividad al recibir recomendaciones contextuales mientras codificas.
[MCP GITHUB](https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp/set-up-the-github-mcp-server)


