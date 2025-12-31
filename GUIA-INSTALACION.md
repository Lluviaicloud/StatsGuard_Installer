# StatsGuard M4 PRO 2.0 - Guía de Generación e Instalación

## 📋 Descripción General

Este conjunto de scripts automatiza completamente la creación del instalador `.pkg` para **StatsGuard M4 PRO 2.0**, incluyendo validación, empaquetamiento y desinstalación.

---

## 📦 Archivos Generados

### 1. `build-statsguard.sh` (Script de Construcción)
**Propósito**: Automatizar la generación del instalador `.pkg`

**Características**:
- ✅ Verifica dependencias (Xcode Command Line Tools)
- ✅ Valida que existan los 4 archivos ejecutables
- ✅ Crea estructura de directorios
- ✅ Asigna permisos automáticamente
- ✅ Genera el componente base (.pkg)
- ✅ Crea el instalador final con validaciones
- ✅ Verifica integridad del paquete
- ✅ Limpia archivos temporales
- ✅ Proporciona resumen detallado

**Uso**:
```bash
chmod +x build-statsguard.sh
./build-statsguard.sh
```

---

### 2. `distribution.xml` (Configuración del Instalador)
**Propósito**: Define el comportamiento y validaciones del instalador

**Características**:
- ✅ Validación de Stats.app en /Applications
- ✅ Mensaje de error personalizado
- ✅ Configuración de instalación silenciosa
- ✅ Información de tamaño de instalación
- ✅ Pantalla de conclusión con instrucciones
- ✅ Identificación de paquete única

**Contenido**:
```xml
- Validación pre-instalación
- Definición de paquete componente
- Estructura de selección
- Pantalla de finalización
```

---

### 3. `uninstall-statsguard.sh` (Script de Desinstalación)
**Propósito**: Desinstalar StatsGuard completamente

**Características**:
- ✅ Verifica instalación existente
- ✅ Pide confirmación del usuario
- ✅ Crea copia de seguridad automática
- ✅ Elimina todos los archivos
- ✅ Busca referencias residuales
- ✅ Proporciona resumen de desinstalación

**Uso**:
```bash
chmod +x uninstall-statsguard.sh
sudo ./uninstall-statsguard.sh
```

---

## 🚀 Flujo Completo de Uso

### Paso 1: Preparación
```bash
# 1. Asegúrate de tener los 4 archivos ejecutables en el directorio actual
ls -la
# Debe mostrar:
# sg-status
# sg-watch
# force_pause
# force_resume

# 2. Asegúrate de que los scripts tienen permisos de ejecución
chmod +x build-statsguard.sh
chmod +x uninstall-statsguard.sh
```

### Paso 2: Generar el Instalador
```bash
# Ejecutar el script de construcción
./build-statsguard.sh

# El script realizará automáticamente:
# 1. Verificación de dependencias
# 2. Validación de archivos ejecutables
# 3. Creación de estructura
# 4. Copia de archivos
# 5. Asignación de permisos
# 6. Generación del componente .pkg
# 7. Generación del instalador final
# 8. Verificación de integridad
# 9. Limpieza de archivos temporales
```

### Paso 3: Resultado Final
```
StatsGuard-M4PRO-2.0-Installer.pkg ← Archivo listo para distribuir
```

### Paso 4: Distribución y Instalación (Usuario Final)

El usuario puede instalar de dos formas:

**Opción A: Doble clic**
```bash
# El usuario descarga StatsGuard-M4PRO-2.0-Installer.pkg
# Hace doble clic en el archivo
# Se abre el instalador de macOS
```

**Opción B: Terminal**
```bash
# El usuario ejecuta:
open ~/Downloads/StatsGuard-M4PRO-2.0-Installer.pkg
```

### Paso 5: Desinstalación (si es necesario)
```bash
# El usuario ejecuta:
sudo /usr/local/statsguard/uninstall-statsguard.sh
# O si lo descargó:
sudo ./uninstall-statsguard.sh
```

---

## 📊 Estructura del Instalador Final

```
StatsGuard-M4PRO-2.0-Installer.pkg
├── Contents/
│   ├── distribution.xml          (Configuración)
│   ├── Packages/
│   │   └── statsguard-component.pkg
│   │       ├── Contents/
│   │       │   ├── PackageInfo
│   │       │   ├── Bom
│   │       │   └── Payload/
│   │       │       └── usr/local/statsguard/
│   │       │           ├── sg-status
│   │       │           ├── sg-watch
│   │       │           ├── force_pause
│   │       │           └── force_resume
│   └── Resources/
│       └── (recursos de interfaz)
```

---

## 🔍 Validaciones Incluidas

### Pre-Instalación
- ✅ Verifica que Stats.app exista en /Applications
- ✅ Muestra mensaje claro si falta Stats.app
- ✅ Impide instalación si Stats.app no está presente

### Durante la Construcción
- ✅ Verifica Xcode Command Line Tools
- ✅ Valida 4 archivos ejecutables
- ✅ Verifica estructura XML
- ✅ Comprueba integridad del paquete

### Después de la Instalación
- ✅ Archivos instalados en /usr/local/statsguard/
- ✅ Permisos correctos (755)
- ✅ Bundle ID único
- ✅ Versión registrada

---

## 📝 Detalles Técnicos

### Identificador de Paquete
```
com.statsguard.m4pro
```

### Ruta de Instalación
```
/usr/local/statsguard/
```

### Versión
```
2.0
```

### Archivos Instalados
```
sg-status      - Verificar estado de Stats
sg-watch       - Monitorizar proceso Stats
force_pause    - Pausar Stats de forma segura
force_resume   - Reanudar Stats
```

---

## ⚠️ Requisitos Previos

### Para la Construcción
- macOS 11+
- Xcode Command Line Tools (`xcode-select --install`)
- Los 4 archivos ejecutables (sg-status, sg-watch, force_pause, force_resume)
- Permisos de lectura/escritura en el directorio

### Para la Instalación (Usuario Final)
- macOS 10.15+
- Stats.app instalada en /Applications
- Acceso de administrador (para instalar en /usr/local/)

---

## 🛠️ Personalización

### Cambiar el Nombre de la App
En `build-statsguard.sh`, modifica:
```bash
APP_NAME="Tu App Name"
BUNDLE_ID="com.tu.appid"
```

### Cambiar la Ruta de Instalación
En `build-statsguard.sh`, modifica:
```bash
INSTALL_PATH="/ruta/deseada"
```

### Cambiar el Mensaje de Bienvenida
En `distribution.xml`, modifica:
```xml
<conclusion title="Tu Título">
Tu mensaje personalizado
</conclusion>
```

---

## 🐛 Troubleshooting

### Error: "No se encuentra pkgbuild"
```bash
# Solución: Instalar Xcode Command Line Tools
xcode-select --install
```

### Error: "Archivos ejecutables no encontrados"
```bash
# Solución: Asegúrate de que los 4 archivos estén en el directorio actual
ls -la sg-status sg-watch force_pause force_resume
```

### Error: "El instalador no encuentra Stats.app"
```bash
# Solución: Usuario final debe instalar Stats.app primero
# Desde App Store o desde https://www.icloud.com/shortcuts/
```

### Error: "Permission denied" al ejecutar scripts
```bash
# Solución: Asignar permisos de ejecución
chmod +x build-statsguard.sh
chmod +x uninstall-statsguard.sh
```

---

## 📊 Ejemplo de Salida

```
════════════════════════════════════════════════════════════════
GENERADOR DE INSTALADOR: StatsGuard M4 PRO
════════════════════════════════════════════════════════════════

ℹ️  Iniciando proceso de generación...

📍 Verificando dependencias del sistema
✅ pkgbuild encontrado
✅ productbuild encontrado

📍 Verificando archivos ejecutables
✅ Encontrado: sg-status
✅ Encontrado: sg-watch
✅ Encontrado: force_pause
✅ Encontrado: force_resume

📍 Creando estructura del payload
✅ Directorio creado: payload/usr/local/statsguard/

📍 Copiando archivos ejecutables al payload
✅ Copiado: sg-status
✅ Copiado: sg-watch
✅ Copiado: force_pause
✅ Copiado: force_resume

📍 Asignando permisos (chmod -R 755)
✅ Permisos establecidos: 755

📍 Creando archivo distribution.xml
✅ Archivo distribution.xml creado
✅ XML validado correctamente

📍 Generando componente base con pkgbuild
✅ Componente generado: statsguard-component.pkg (2.45 MB)

📍 Generando instalador final con productbuild
✅ Instalador final generado: StatsGuard-M4PRO-2.0-Installer.pkg (2.48 MB)

📍 Verificando integridad del paquete
ℹ️  Contenido del paquete:
  usr/local/statsguard/sg-status
  usr/local/statsguard/sg-watch
  usr/local/statsguard/force_pause
  usr/local/statsguard/force_resume

════════════════════════════════════════════════════════════════
RESUMEN FINAL
════════════════════════════════════════════════════════════════

✅ Instalador generado correctamente

Detalles:
  • Nombre: StatsGuard M4 PRO
  • Versión: 2.0
  • Bundle ID: com.statsguard.m4pro
  • Ubicación: /Users/usuario/StatsGuard-M4PRO-2.0-Installer.pkg
  • Tamaño: 2.48 MB

Archivo de instalación:
  StatsGuard-M4PRO-2.0-Installer.pkg

════════════════════════════════════════════════════════════════
```

---

## 📞 Soporte

Para problemas o preguntas:
1. Verifica que tienes Xcode Command Line Tools instalado
2. Asegúrate de que los 4 archivos ejecutables estén presentes
3. Revisa los permisos del directorio
4. Ejecuta nuevamente el script de construcción

---

## 📄 Licencia

StatsGuard M4 PRO 2.0
Copyright © 2025. Todos los derechos reservados.
