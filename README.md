# Portafolio Técnico de Ciberseguridad — Analista SOC Nivel 1 en formación

**Autor:** Emmanuel Mercado Najar

**Perfil:** Analista de Ciberseguridad Defensiva (Blue Team) en formación

**Especialización:** Monitoreo y Detección de Amenazas, Triage en Linux, Análisis de Tráfico de Red y Auditoría de Seguridad.

**Certificación:** Google Cybersecurity Professional Certificate (en curso) | Estudiante de Ingeniería en Sistemas Computacionales.

---

## 🎯 Objetivo del Repositorio

Este repositorio documenta casos de estudio prácticos, análisis de tráfico y procedimientos de respuesta a incidentes orientados a la operación real de un **Centro de Operaciones de Seguridad (SOC)**. Cada proyecto aplica marcos de trabajo reconocidos en la industria como **NIST CSF**, **NIST SP 800-61** y **MITRE ATT&CK**.

---

## 📂 Estructura de Proyectos y Evidencias Técnicas

### 🛡️ [01. Gestión de Riesgos y Auditoría — Caso Botium Toys](./01-gestion-riesgos-botium-toys/)

* **Enfoque:** Auditoría de seguridad interna, evaluación de controles y brechas de cumplimiento normativo (**PCI DSS** y **GDPR**).
* **Entregables:** Matriz de clasificación de controles (preventivos, detectivos, correctivos) y plan formal de mitigación para activos críticos.

### 🌐 [02. Análisis de Tráfico de Red con `tcpdump`](./02-analisis-trafico-red-tcpdump/)

* **Enfoque:** Inspección de capturas de paquetes en línea de comandos para correlacionar resolución de dominios (**DNS**) y establecimiento de sesiones (**TCP Three-Way Handshake**).
* **Entregables:** Análisis de anomalías de red, lectura de banderas TCP e identificación de tráfico web no cifrado.

### 🚨 [03. Reportes de Respuesta a Incidentes (SOC)](./03-reportes-incidentes-soc/)

* **Enfoque:** Registro cronológico de incidentes (*Incident Handler's Journal*), delimitación de impacto y aplicación de fases de contención, erradicación y recuperación.
* **Entregables:** Informes de incidentes de seguridad y análisis forense post-evento.

### 🐧 [04. Triage e Investigación Forense en Linux](./04-investigacion-linux-forense/)

* **Enfoque:** Inspección del sistema operativo mediante CLI bajo entornos Ubuntu/Debian sin depender de interfaces gráficas.
* **Entregables:** Filtrado de registros con `grep` y expresiones regulares, búsqueda forense de archivos por atributos con `find`, redirección de descriptores de error (`2>/dev/null`) y auditoría de permisos.

### 🔐 [05. Fuga de Datos — Privilegio Mínimo (NIST SP 800-53: AC-6)](./fuga-de-datos/)

* **Enfoque:** Análisis de un incidente de exposición de información interna y aplicación del principio de privilegio mínimo.
* **Entregables:** Hoja de trabajo con análisis del incidente, controles, recomendaciones y justificación.

### 🏠 [06. Inventario de Activos Domésticos](./inventario-activos/)

* **Enfoque:** Identificación de dispositivos conectados a una red doméstica, nivel de acceso, propietario y clasificación de sensibilidad de datos.
* **Entregables:** Inventario de activos con niveles de sensibilidad aplicados (Restricted, Confidential, Internal-only, Public).

### 📄 Recursos adicionales

* [filtros-consultas-sql.md](./filtros-consultas-sql.md) — Consultas SQL para auditoría.
* [declaracion-profesional.md](./declaracion-profesional.md) — Declaración profesional.

---

## 🛠️ Stack Técnico y Herramientas

* **Sistemas Operativos:** Linux (Ubuntu / WSL2), Windows.
* **Herramientas de Red y Logs:** `tcpdump`, Wireshark, análisis de registros de autenticación (`auth.log`, `syslog`).
* **Línea de Comandos & Scripting:** Bash (`find`, `grep`, `awk`, `sed`, `chmod`, `chown`), SQL para consultas de auditoría.
* **Estándares y Marcos:** NIST Cybersecurity Framework (CSF), PCI DSS, GDPR, CIS Controls.

---

## 📬 Contacto

* **LinkedIn:** linkedin.com/in/emmanuel-mercado-najar-1225ba406
* **Credly:** credly.com/users/emmanuel-mercado-najar
* **Correo:** mercadonajare@gmail.com
