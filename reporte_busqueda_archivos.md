# Laboratorio: Búsqueda y Navegación de Archivos en Linux (Blue Team)

## Objetivo
Localizar artefactos y registros relevantes para la investigación de incidentes en el sistema de archivos de Linux mediante la consola Bash.

## Comandos Utilizados
* `pwd`: Verificación de la ruta de trabajo actual.
* `cd [directorio]`: Desplazamiento entre rutas relativas y absolutas.
* `ls -la`: Inspección de directorios mostrando metadatos y archivos ocultos (`.`).
* `ls *.log`: Filtrado rápido de archivos mediante patrones comodín.

## Hallazgos de Seguridad
* **Archivos Ocultos:** Se identificó que atacantes o procesos maliciosos pueden ocultar scripts o artefactos prefijando el nombre con un punto (`.`). El uso de `ls -a` es obligatorio en auditorías de endpoints.
* **Trazabilidad:** Localización rápida de registros de servidor en rutas específicas para análisis posterior de accesos no autorizados.
