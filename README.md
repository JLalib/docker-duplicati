# 🧩 Duplicati — Backup Automation via Docker

Implementación de **Duplicati** con Docker Compose. Backup de contenedores en NAS Synology
Duplicati es una solución de copia de seguridad cifrada y automatizada con interfaz web, ideal para entornos domésticos o de servidor.

---

## 🧱 Servicios

| Servicio   | Imagen                              | Puerto | Descripción                                   |
|-------------|-------------------------------------|---------|-----------------------------------------------|
| duplicati   | `ghcr.io/linuxserver/duplicati:latest` | 8200    | Interfaz web de administración y motor de copias de seguridad |

---

## ⚙️ Estructura del Proyecto

```bash
duplicati/
├── docker-compose.yml
├── .env
├── config/               # Configuración y base de datos interna
├── /mnt/nas_backups/     # Carpeta de destino para las copias de seguridad
└── /home/genbyte/        # Carpeta de origen para respaldar
```

---

## 🚀 Despliegue

1. **Clona el repositorio:**
   ```bash
   git clone https://github.com/tu_usuario/duplicati-docker.git
   cd duplicati-docker
   ```

2. **Configura variables de entorno en el archivo `.env`:**
   ```bash
   SETTINGS_ENCRYPTION_KEY=eob7MGtKE6OuYEjaRD3adRfPMPcUhf768PpTkw5M40Yt0egBIaVbx5Bm9THrzqWJ
   DUPLICATI__WEBSERVICE_PASSWORD=pass@word
   ```

3. **Levanta el servicio:**
   ```bash
   docker compose up -d
   ```

4. **Accede a la interfaz web:**
   - URL: [http://localhost:8200](http://localhost:8200)
   - Usuario y contraseña definidos en las variables de entorno.

---

## 🧩 Variables de Entorno

| Variable | Descripción |
|-----------|--------------|
| `PUID` | ID del usuario local (1000 recomendado) |
| `PGID` | ID del grupo local (1000 recomendado) |
| `TZ` | Zona horaria |
| `SETTINGS_ENCRYPTION_KEY` | Clave de cifrado para la configuración |
| `DUPLICATI__WEBSERVICE_PASSWORD` | Contraseña de acceso web |

---

## 🔐 Seguridad

- Se recomienda cambiar las claves de entorno antes del despliegue en producción.
- Usa certificados HTTPS si se expone fuera de la red local.

---

## 🧠 Recursos

- [Duplicati.org](https://www.duplicati.com/)  
- [Documentación Docker de LinuxServer.io](https://docs.linuxserver.io/images/docker-duplicati)

