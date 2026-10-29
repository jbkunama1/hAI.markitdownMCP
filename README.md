# hAI.markitdownMCP

**MarkItDown MCP Server** als Portainer Stack für das `highfishNetwork`.  
Konvertiert PDFs, Office-Dokumente, Bilder, Audio und Webseiten in Markdown für KI-Clients.

Basiert auf Microsofts [`markitdown-mcp`](https://github.com/microsoft/markitdown).

## Portainer Stack

1. Portainer → **Stacks** → **Add Stack** → **Git Repository**
2. Repository: `https://github.com/jbkunama1/hAI.markitdownMCP.git`
3. Reference: `refs/heads/main`
4. Compose path: `docker-compose.yml`
5. **Deploy the stack**

## Zugriff

| Dienst | URL |
|---|---|
| MCP Streamable HTTP | `http://<host>:3333/mcp` |

## Netzwerk

```yaml
networks:
  highfishNetwork:
    external: true
```

Falls nicht vorhanden:

```bash
docker network create highfishNetwork
```

## Sicherheit

Der MarkItDown MCP Server hat **keine eingebaute Authentifizierung**.  
Nur im LAN betreiben oder ausschließlich über einen authentifizierten Reverse Proxy / Cloudflare Access freigeben.

## GHCR

```bash
docker pull ghcr.io/jbkunama1/hai-markitdownmcp:latest
```

## Update-Check

Ein GitHub Actions Workflow prüft täglich um 05:00 Uhr deutscher Zeit, ob eine neue `markitdown-mcp`-Version auf PyPI verfügbar ist. Bei einem Update wird automatisch ein Issue mit dem Label `upstream-update` erstellt oder aktualisiert.
