# Survans · web-borrador v1 — imagen estática servida con nginx (usuario no root)
FROM nginxinc/nginx-unprivileged:1.27-alpine

LABEL org.opencontainers.image.title="survans-web" \
      org.opencontainers.image.description="Survans — web borrador v1 (prototipo para PRD)" \
      org.opencontainers.image.source="https://github.com/DevArtificialmente/Survans-pruebas"

COPY --chown=nginx:nginx nginx.conf /etc/nginx/conf.d/default.conf
COPY --chown=nginx:nginx index.html web-borrador-v1.html /usr/share/nginx/html/

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=3s --retries=3 \
  CMD wget -q -O /dev/null http://127.0.0.1:8080/ || exit 1
