# ?? Sistema de Control de Acceso Empresarial

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/jesm2025/access-control-system)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

Sistema integral de gesti�n de control de acceso y asistencias con integraci�n a dispositivos **Hikvision DS-K1T804AMF**, reportes avanzados y gesti�n remota de dispositivos.

## ?? Caracter�sticas Principales

### ?? Control de Acceso
- **Integraci�n completa** con dispositivos Hikvision biom�tricos
- **M�ltiples m�todos** de verificaci�n: huella dactilar, tarjeta RFID, PIN
- **Eventos en tiempo real** de entrada y salida
- **Control de horarios** y restricciones por empleado

### ?? Gesti�n de Empleados
- **CRUD completo** de empleados con validaciones
- **Registro biom�trico** directamente desde la interfaz web
- **Asignaci�n de tarjetas** RFID autom�tica
- **Estados y permisos** por empleado

### ?? Reportes Avanzados
- **Exportaci�n m�ltiple**: Excel, CSV, PDF
- **Campos personalizables** para cada reporte
- **Filtros avanzados** por fecha, departamento, empleado
- **An�lisis de productividad** y horas extra

### ?? Gesti�n de Dispositivos
- **Configuraci�n remota** de dispositivos Hikvision
- **Cambio de IP y configuraci�n de red**
- **Backup y restauraci�n** de configuraciones
- **Monitoreo en tiempo real** de estado y m�tricas
- **Actualizaci�n de firmware** remota

## ??? Stack Tecnol�gico

- **Frontend**: React 18, Tailwind CSS, Lucide React
- **Backend**: Node.js 18, Express.js, PostgreSQL 15
- **DevOps**: Docker, Docker Compose, Nginx
- **Integraci�n**: Hikvision ISAPI, WebSocket

## ?? Inicio R�pido

### Prerrequisitos
- Node.js 18.x o superior
- Docker y Docker Compose
- Git

### Instalaci�n

```bash
# 1. Clonar repositorio
git clone https://github.com/jesm2025/access-control-system.git
cd access-control-system

# 2. Configurar variables de entorno
cp .env.example .env.local
# En Windows: copy .env.example .env.local
nano .env.local

# 3. Instalar dependencias
npm run install:all

# 4. Iniciar servicios con Docker
npm run docker:dev

# 5. Acceder a la aplicaci�n
# Frontend: http://localhost:3000
# Backend: http://localhost:3001
```

### Credenciales por Defecto
- **Usuario**: `admin`
- **Contrase�a**: `admin123`

## ?? Deployment a Producci�n

```bash
# Ejecutar script de deployment
chmod +x scripts/deploy.sh
./scripts/deploy.sh
```

## ?? Configuraci�n de Dispositivos Hikvision

1. Conectar dispositivo a la red local
2. Configurar IP est�tica en el dispositivo
3. Actualizar variables de entorno HIKVISION_*
4. Usar el m�dulo de "Gesti�n de Dispositivos" para configuraci�n remota

## ?? Documentaci�n

- [Gu�a de Instalaci�n](docs/installation.md)
- [Configuraci�n de Hikvision](docs/hikvision-setup.md)
- [API Reference](docs/api.md)

## ?? Contribuci�n

1. Fork del repositorio
2. Crear branch: `git checkout -b feature/nueva-funcionalidad`
3. Commit: `git commit -am 'Agregar nueva funcionalidad'`
4. Push: `git push origin feature/nueva-funcionalidad`
5. Crear Pull Request

## ?? Licencia

Este proyecto est� bajo la Licencia MIT. Ver [LICENSE](LICENSE) para m�s detalles.

---

**Construido con ?? por [Tu Empresa](https://jesm2025.com)**
