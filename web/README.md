# Survans · web borrador v1

Prototipo de la nueva web de Survans (survans.com.uy), hecho con Claude Design. Es la **web-borrador v1** que se usa como base para el PRD.

| Archivo | Qué es |
|---|---|
| `index.html` | Web-borrador v1 (copia idéntica de `web-borrador-v1.html`, para GitHub Pages y Docker) |
| `web-borrador-v1.html` | Web-borrador v1, versión de referencia |
| `Dockerfile` + `nginx.conf` | Imagen estática con nginx (no root, puerto 8080) |
| `.github/workflows/docker-publish.yml` | Publica la imagen en GitHub Container Registry en cada push a `main` |

## Docker

Imagen: `ghcr.io/devartificialmente/survans-web` (tags `latest`, `borrador-v1`, `sha-<commit>`).

```bash
# usar la imagen publicada
docker run --rm -p 8080:8080 ghcr.io/devartificialmente/survans-web:latest

# o construir local
docker build -t survans-web .
docker run --rm -p 8080:8080 survans-web
```

Abrir http://localhost:8080

Nota: la primera vez el paquete en GHCR queda privado; para que cualquiera pueda hacer `docker pull`, cambiar la visibilidad a pública en GitHub → Packages → survans-web → Package settings.

## Estado

Borrador: textos de marca, logo, colores y fotos son provisorios hasta que lleguen los materiales de Survans.
