# Football Live Dashboard

Dashboard de partidos en directo conectado a API-Football.

## Setup

### 1. Sube a GitHub
Sube esta carpeta entera a un repositorio de GitHub.

### 2. Importa en Vercel
Importa el repositorio en [vercel.com](https://vercel.com).

### 3. Añade la API Key como variable de entorno (MUY IMPORTANTE)
En Vercel, ve a:
**Project → Settings → Environment Variables**

Añade esta variable:
| Name | Value |
|------|-------|
| `RAPIDAPI_KEY` | tu_api_key_aqui |

> ⚠️ NUNCA pongas la API key directamente en el código.
> Las variables de entorno en Vercel son privadas y seguras.

### 4. Redeploy
Después de añadir la variable, haz un nuevo deploy:
**Deployments → ··· → Redeploy**

## Cómo funciona

```
index.html  →  cada 60s llama a /api/live
/api/live   →  serverless function en Vercel
               usa RAPIDAPI_KEY (privada) para llamar a API-Football
               devuelve solo los datos necesarios al frontend
```

## Archivos
- `index.html` — el dashboard visual
- `api/live.js` — backend serverless (proxy seguro a API-Football)
- `vercel.json` — configuración de rutas
