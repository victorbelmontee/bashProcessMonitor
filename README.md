# 🔍 Bash Process Monitor

![License](https://img.shields.io/badge/license-MIT-blue.svg)  
![Bash Version](https://img.shields.io/badge/bash-4.0%2B-green.svg)  
![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS-lightgrey.svg)  
![Status](https://img.shields.io/badge/status-active-success.svg)  

Monitor de procesos en tiempo real desarrollado en Bash, ideal para supervisar cambios en la lista de procesos del sistema y detectar arranques o cierres inesperados.

---

## 📋 Tabla de Contenidos

- [🚀 Características Principales](#-características-principales)    
- [📦 Instalación](#-instalación)  
- [💡 Uso](#-uso)  
- [📚 Documentación](#-documentación)  
- [🔧 Configuración](#-configuración)  
- [📊 Ejemplos de Uso](#-ejemplos-de-uso)  
- [🤝 Contribución](#-contribución)  
- [📄 Licencia](#-licencia)  

---

## 🚀 Características Principales

- **Detección de Cambios**: Lista en tiempo real de procesos iniciados o terminados  
- **Filtrado Automático**: Excluye procesos del propio monitor o del sistema (`kworker`, etc.)  
- **Interfaz Limpia**: Salida por terminal sin dependencias externas  
- **Respaldo de Cursor**: Oculta/recupera el cursor para mejor experiencia visual  
- **Manejo de Señales**: Captura `Ctrl+C` para una salida limpia  

---

## 📦 Instalación

> **Requisitos**  
> - Linux o macOS  
> - Bash 4.0 o superior  
> - Permisos de lectura en `/proc` (Linux) o equivalentes  

### Clonado y Preparación

```bash
git clone https://github.com/victorbelmontee/bashProcessMonitor.git
cd bashProcessMonitor
chmod +x procmon.sh
```

---

## 💡 Uso

```bash
# Ejecutar el monitor
./procmon.sh

# Salir en cualquier momento con Ctrl+C
```

### Parámetros

Este script no requiere parámetros adicionales; excluye por defecto procesos de sistema y del monitor.

---

## 📚 Documentación

El flujo básico es:

1. **Inicialización**: Guarda el listado actual de procesos.
2. **Bucle Infinito**: Cada ciclo obtiene procesos nuevos y los compara.
3. **Salida de Cambios**: Muestra líneas con `>` para arranques y `<` para cierres.
4. **Actualización de Estado**: El estado actual se convierte en el "antiguo" para el siguiente ciclo.

---

## 🔧 Configuración

No requiere archivo de configuración. Opcionalmente, puedes modificar la lista de procesos excluidos editando la línea de `grep -vE` en el código.

---

## 📊 Ejemplos de Uso

```bash
# Abrir dos terminales:
# 1) Ejecuta el monitor
./procmon.sh

# 2) En la otra, lanza o detén procesos (p.ej., sleep o top) para ver las diferencias
sleep 60 &
kill <pid_de_sleep>
```

---

## 🤝 Contribución

1. **Fork** el repositorio
2. Crear rama feature: `git checkout -b feature/nueva-funcionalidad`
3. **Commit**: `git commit -am 'Descripción del cambio'`
4. **Push** y abrir Pull Request

---

## 📄 Licencia

Licenciado bajo MIT. Ver [`LICENSE`](LICENSE) para más detalles.
