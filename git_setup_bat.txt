@echo off
echo.
echo ================================================================================
echo                    🔧 CONFIGURACION DE GIT Y GITHUB (Windows)
echo ================================================================================
echo.

REM Verificar Git
git --version >nul 2>&1
if %errorlevel% neq 0 (
    echo ❌ Git no esta instalado
    echo Por favor instala Git desde: https://git-scm.com/download/win
    pause
    exit /b 1
)

echo ✅ Git encontrado

echo.
echo 📝 Configuracion del repositorio:
echo.

REM Solicitar información
set /p PROJECT_NAME="Nombre del proyecto (access-control-system): "
if "%PROJECT_NAME%"=="" set PROJECT_NAME=access-control-system

set /p GITHUB_USER="Tu usuario de GitHub: "
if "%GITHUB_USER%"=="" (
    echo ❌ El usuario de GitHub es obligatorio
    pause
    exit /b 1
)

set /p PROJECT_DESC="Descripcion del proyecto: "
if "%PROJECT_DESC%"=="" set PROJECT_DESC=Sistema integral de control de acceso y asistencias con integración Hikvision

echo.
echo ℹ️  Configuracion:
echo    • Proyecto: %PROJECT_NAME%
echo    • Usuario: %GITHUB_USER%
echo    • Descripcion: %PROJECT_DESC%
echo.

set /p CONFIRM="¿Es correcta la informacion? (y/N): "
if /i not "%CONFIRM%"=="y" (
    echo ❌ Cancelado por el usuario
    pause
    exit /b 1
)

echo.
echo 🔧 Configurando Git...

REM Inicializar repositorio si no existe
if not exist .git (
    git init
    echo ✅ Repositorio Git inicializado
) else (
    echo ℹ️  Repositorio Git ya existe
)

REM Configurar rama principal
git branch -M main 2>nul

REM Actualizar package.json con la URL correcta del repositorio
powershell -Command "(Get-Content package.json) -replace 'YOUR_USERNAME', '%GITHUB_USER%' | Set-Content package.json"
powershell -Command "(Get-Content package.json) -replace 'access-control-system', '%PROJECT_NAME%' | Set-Content package.json"

REM Actualizar README.md
powershell -Command "(Get-Content README.md) -replace 'your-repo', '%GITHUB_USER%' | Set-Content README.md"
powershell -Command "(Get-Content README.md) -replace 'your-company', '%GITHUB_USER%' | Set-Content README.md"

echo ✅ Archivos actualizados con tu informacion

REM Agregar archivos
git add .
if %errorlevel% neq 0 (
    echo ❌ Error agregando archivos
    pause
    exit /b 1
)

REM Commit inicial
git commit -m "🎉 Initial commit: Complete access control system

✨ Features:
- Full-stack React + Node.js application
- Hikvision device integration
- Docker development environment  
- Complete project structure with backend/frontend
- PostgreSQL + Redis setup
- Authentication and authorization system
- Advanced reporting capabilities
- Device management module

🛠️ Tech Stack:
- Frontend: React 18, Tailwind CSS, Lucide React
- Backend: Node.js 18, Express.js, PostgreSQL 15
- DevOps: Docker, Docker Compose, Nginx
- Integration: Hikvision ISAPI, WebSocket

🚀 Ready for development and production deployment"

if %errorlevel% neq 0 (
    echo ❌ Error creando commit inicial
    pause
    exit /b 1
)

REM Agregar remoto
git remote add origin https://github.com/%GITHUB_USER%/%PROJECT_NAME%.git 2>nul

echo ✅ Git configurado correctamente

echo.
echo ================================================================================
echo                            🎉 GIT CONFIGURADO EXITOSAMENTE
echo ================================================================================
echo.
echo 📋 PROXIMOS PASOS:
echo.
echo 1️⃣  CREAR REPOSITORIO EN GITHUB:
echo    • Ve a: https://github.com/new
echo    • Nombre: %PROJECT_NAME%
echo    • Descripcion: %PROJECT_DESC%
echo    • ⚠️  NO inicialices con README, .gitignore o licencia
echo.
echo 2️⃣  SUBIR CODIGO A GITHUB:
echo    git push -u origin main
echo.
echo 🔗 Tu repositorio estara en:
echo    https://github.com/%GITHUB_USER%/%PROJECT_NAME%
echo.
echo ================================================================================
echo ¡Solo ejecuta 'git push -u origin main' despues de crear el repo en GitHub!
echo ================================================================================
echo.
pause