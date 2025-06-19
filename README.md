# ?? Sistema de Control de Acceso Empresarial

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/jesm2025/access-control-system)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

Sistema integral de gestión de control de acceso y asistencias con integración a dispositivos **Hikvision DS-K1T804AMF**, reportes avanzados y gestión remota de dispositivos.

## ?? Características Principales

### ?? Control de Acceso
- **Integración completa** con dispositivos Hikvision biométricos
- **Múltiples métodos** de verificación: huella dactilar, tarjeta RFID, PIN
- **Eventos en tiempo real** de entrada y salida
- **Control de horarios** y restricciones por empleado

### ?? Gestión de Empleados
- **CRUD completo** de empleados con validaciones
- **Registro biométrico** directamente desde la interfaz web
- **Asignación de tarjetas** RFID automática
- **Estados y permisos** por empleado

### ?? Reportes Avanzados
- **Exportación múltiple**: Excel, CSV, PDF
- **Campos personalizables** para cada reporte
- **Filtros avanzados** por fecha, departamento, empleado
- **Análisis de productividad** y horas extra

### ?? Gestión de Dispositivos
- **Configuración remota** de dispositivos Hikvision
- **Cambio de IP y configuración de red**
- **Backup y restauración** de configuraciones
- **Monitoreo en tiempo real** de estado y métricas
- **Actualización de firmware** remota

## ??? Stack Tecnológico

- **Frontend**: React 18, Tailwind CSS, Lucide React
- **Backend**: Node.js 18, Express.js, PostgreSQL 15
- **DevOps**: Docker, Docker Compose, Nginx
- **Integración**: Hikvision ISAPI, WebSocket

## ?? Inicio Rápido

### Prerrequisitos
- Node.js 18.x o superior
- Docker y Docker Compose
- Git

### Instalación

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

# 5. Acceder a la aplicación
# Frontend: http://localhost:3000
# Backend: http://localhost:3001
```

### Credenciales por Defecto
- **Usuario**: `admin`
- **Contraseña**: `admin123`

## ?? Deployment a Producción

```bash
# Ejecutar script de deployment
chmod +x scripts/deploy.sh
./scripts/deploy.sh
```

## ?? Configuración de Dispositivos Hikvision

1. Conectar dispositivo a la red local
2. Configurar IP estática en el dispositivo
3. Actualizar variables de entorno HIKVISION_*
4. Usar el módulo de "Gestión de Dispositivos" para configuración remota

## ?? Documentación

- [Guía de Instalación](docs/installation.md)
- [Configuración de Hikvision](docs/hikvision-setup.md)
- [API Reference](docs/api.md)

## ?? Contribución

1. Fork del repositorio
2. Crear branch: `git checkout -b feature/nueva-funcionalidad`
3. Commit: `git commit -am 'Agregar nueva funcionalidad'`
4. Push: `git push origin feature/nueva-funcionalidad`
5. Crear Pull Request

## ?? Licencia

Este proyecto está bajo la Licencia MIT. Ver [LICENSE](LICENSE) para más detalles.

---

**Construido con ?? por [Tu Empresa](https://jesm2025.com)**
