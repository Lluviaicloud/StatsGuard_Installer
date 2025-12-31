# 🚀 QUICK START - StatsGuard M4 PRO 2.0

## ⚡ Inicio Rápido (5 minutos)

### Paso 1: Preparar el Directorio
```bash
# Coloca estos 3 archivos en un directorio:
# 1. build-statsguard.sh       (script de construcción)
# 2. distribution.xml          (configuración)
# 3. Tus 4 ejecutables:
#    - sg-status
#    - sg-watch
#    - force_pause
#    - force_resume

# Estructura:
# my-project/
# ├── build-statsguard.sh
# ├── distribution.xml
# ├── sg-status
# ├── sg-watch
# ├── force_pause
# └── force_resume
```

### Paso 2: Ejecutar la Construcción
```bash
# Navega al directorio
cd my-project/

# Dale permisos al script
chmod +x build-statsguard.sh

# Ejecuta la construcción
./build-statsguard.sh
```

### Paso 3: ¡Listo!
```
✅ StatsGuard-M4PRO-2.0-Installer.pkg

Tu instalador está listo para distribuir
```

---

## 📋 Checklist Pre-Construcción

- [ ] `build-statsguard.sh` presente en el directorio
- [ ] `distribution.xml` presente en el directorio
- [ ] Archivo `sg-status` presente
- [ ] Archivo `sg-watch` presente
- [ ] Archivo `force_pause` presente
- [ ] Archivo `force_resume` presente
- [ ] Tienes Xcode Command Line Tools (`xcode-select --install`)

---

## 🔧 Instalación (Usuario Final)

### Opción 1: Interfaz Gráfica (Recomendado)
```bash
# Descargar el instalador
# Hacer doble clic en StatsGuard-M4PRO-2.0-Installer.pkg
# Seguir las instrucciones en pantalla
```

### Opción 2: Terminal
```bash
open ~/Downloads/StatsGuard-M4PRO-2.0-Installer.pkg
```

### Verificar Instalación
```bash
# Los archivos deben estar en:
ls -la /usr/local/statsguard/

# Output esperado:
# sg-status
# sg-watch
# force_pause
# force_resume
```

---

## 🗑️ Desinstalación

```bash
# Descargar uninstall-statsguard.sh al mismo directorio
chmod +x uninstall-statsguard.sh

# Ejecutar como administrador
sudo ./uninstall-statsguard.sh

# Seguir las instrucciones
```

---

## 📊 Lo Que Hace el Script

```
✅ Verifica Xcode Command Line Tools
✅ Valida los 4 archivos ejecutables
✅ Crea estructura de directorios
✅ Copia archivos
✅ Asigna permisos (755)
✅ Genera componente .pkg base
✅ Crea instalador final
✅ Verifica integridad
✅ Limpia archivos temporales
✅ Genera resumen completo
```

---

## 🎯 Archivos Generados

| Archivo | Tamaño | Uso |
|---------|--------|-----|
| **StatsGuard-M4PRO-2.0-Installer.pkg** | ~2.5 MB | Distribuir a usuarios |
| statsguard-component.pkg | ~2.5 MB | Temporal (se elimina) |
| payload/ | ~2.4 MB | Temporal (se elimina) |

---

## 🔑 Información Importante

### Identificador del Paquete
```
com.statsguard.m4pro
```

### Versión
```
2.0
```

### Ruta de Instalación
```
/usr/local/statsguard/
```

### Requisito Principal
```
Stats.app debe estar instalada en /Applications
```

---

## ❓ Problemas Comunes

### "Command not found: pkgbuild"
```bash
# Solución:
xcode-select --install
```

### "No such file or directory"
```bash
# Solución: Asegúrate de que los 4 ejecutables estén en el directorio actual
ls -la sg-*
```

### "Stats.app no está instalada"
```bash
# Solución (para el usuario):
# 1. Instalar Stats.app desde App Store
# 2. Luego ejecutar el instalador de StatsGuard
```

---

## 📞 Soporte Rápido

| Problema | Solución |
|----------|----------|
| Script no ejecutable | `chmod +x build-statsguard.sh` |
| Permisos insuficientes | `sudo` no es necesario para compilar |
| Archivos faltantes | `ls -la` para verificar |
| XML incorrecto | Usar el archivo `distribution.xml` proporcionado |

---

## 💾 Archivos Necesarios (Resumen)

**Para la Construcción:**
1. ✅ build-statsguard.sh
2. ✅ distribution.xml
3. ✅ sg-status
4. ✅ sg-watch
5. ✅ force_pause
6. ✅ force_resume

**Para la Desinstalación:**
1. ✅ uninstall-statsguard.sh

**Para la Documentación:**
1. ✅ GUIA-INSTALACION.md (este archivo)

---

## 🎉 ¡Listo!

Tu instalador `.pkg` está listo para distribuir. Los usuarios pueden instalarlo haciendo doble clic en:

```
StatsGuard-M4PRO-2.0-Installer.pkg
```

---

**Versión**: 2.0  
**Última actualización**: 2025-12-31  
**Estado**: ✅ LISTO PARA PRODUCCIÓN
