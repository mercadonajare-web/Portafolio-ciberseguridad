# Caso de Estudio: Auditoría de Seguridad y Cumplimiento — Botium Toys

**Rol:** Analista de Ciberseguridad / Auditor Interno  
**Marco de referencia:** NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)  
**Estándares normativos evaluados:** PCI DSS, GDPR, SOC Type 1 / Type 2  

---

## 1. Alcance y Objetivos de la Auditoría

### Alcance
La auditoría abarca la totalidad del programa de seguridad de **Botium Toys**, incluyendo dispositivos de usuarios finales (laptops, estaciones remotas, periféricos), infraestructura de red interna, sistemas de almacenamiento, bases de datos transaccionales de comercio electrónico y el almacén físico adyacente a la tienda minorista.

### Objetivos
1. Identificar activos críticos y clasificar su impacto en la continuidad del negocio.
2. Evaluar la postura actual de seguridad frente al marco **NIST CSF**.
3. Determinar el nivel de cumplimiento normativo frente a las regulaciones internacionales **PCI DSS** y **GDPR**.
4. Elaborar una matriz de mitigación para reducir la puntuación de riesgo global.

---

## 2. Evaluación de Riesgos y Postura Actual

* **Puntuación de Riesgo Actual:** **8 / 10** (Riesgo Alto).
* **Impacto potencial:** Medio-Alto debido a la falta de clasificación de datos confidenciales y la exposición de datos de tarjetahabientes.
* **Principales vulnerabilidades identificadas:**
  * **Ausencia de cifrado:** Los datos de tarjetas de crédito se procesan y almacenan internamente en texto claro sin mecanismos criptográficos.
  * **Acceso universal no restringido:** Todos los empleados tienen acceso irrestricto a bases de datos que contienen información de identificación personal (**PII**) y datos bancarios.
  * **Inexistencia de copias de seguridad y DRP:** La empresa no cuenta con respaldos automáticos ni plan de recuperación ante desastres.
  * **Visibilidad de red insuficiente:** No se cuenta con un sistema de detección de intrusiones (**IDS**).
  * **Políticas débiles de contraseñas:** Ausencia de requisitos de complejidad técnica y falta de un gestor de contraseñas centralizado.

---

## 3. Matriz de Evaluación de Controles

| Control de Seguridad | Tipo de Control | Estado Actual | Propósito / Justificación Técnica |
| :--- | :--- | :---: | :--- |
| **Principio de menor privilegio** | Preventivo | ❌ No | Restringir el acceso a datos sensibles solo al personal indispensable. |
| **Planes de recuperación ante desastres (DRP)** | Correctivo | ❌ No | Garantizar la resiliencia operativa y continuidad del negocio. |
| **Políticas de contraseñas robustas** | Preventivo | ❌ No | Mitigar ataques de fuerza bruta y pulverización de credenciales (*password spraying*). |
| **Separación de funciones (SoD)** | Preventivo | ❌ No | Evitar que un solo rol pueda comprometer un proceso crítico completo. |
| **Cortafuegos (Firewall)** | Preventivo | ✅ Sí | Filtrado de tráfico perimetral configurado con reglas estrictas. |
| **Sistema de detección de intrusiones (IDS)** | Detectivo | ❌ No | Identificar patrones y firmas de tráfico sospechoso en la red. |
| **Copias de seguridad (Backups)** | Correctivo | ❌ No | Restaurar información crítica frente a incidentes de ransomware o corrupción. |
| **Software Antivirus (AV)** | Preventivo | ✅ Sí | Solución de firmas desplegada y monitoreada periódicamente. |
| **Mantenimiento de sistemas heredados (*Legacy*)** | Preventivo | ❌ No | Requiere un calendario formal de parches e intervención programada. |
| **Cifrado de datos (en tránsito y reposo)** | Disuasorio / Preventivo | ❌ No | Salvaguardar la confidencialidad de la información transaccional. |
| **Gestión centralizada de contraseñas** | Preventivo | ❌ No | Reducir la fatiga de credenciales y forzar autenticación multifactor. |
| **Cerraduras físicas y control de acceso** | Disuasorio / Preventivo | ✅ Sí | Protección física de oficinas, almacén y equipos de red. |
| **Circuito Cerrado de Televisión (CCTV)** | Preventivo / Detectivo | ✅ Sí | Monitoreo visual de entradas, almacenes y áreas operativas. |
| **Detección y supresión de incendios** | Preventivo / Detectivo | ✅ Sí | Rociadores y alarmas operativas en instalaciones físicas. |

---

## 4. Evaluación de Cumplimiento Regulatorio

### PCI DSS (Payment Card Industry Data Security Standard)
* **Requisito 3 (Proteger datos de tarjetahabientes almacenados):** **No cumple.** Los números de tarjetas de crédito se guardan sin cifrado en bases de datos internas.
* **Requisito 7 (Restricción de acceso según necesidad de saber):** **No cumple.** No existe segregación por roles de usuario.
* **Requisito 8 (Identificación y autenticación de usuarios):** **No cumple.** Políticas de contraseñas básicas sin MFA ni rotación.

### GDPR (General Data Protection Regulation)
* **Privacidad y confidencialidad de datos:** **No cumple.** La falta de control de accesos expone PII/SPII de clientes europeos.
* **Notificación de brechas de seguridad (72 horas):** **Cumple.** Existe un procedimiento documentado para notificar a la autoridad y a los afectados dentro del plazo legal.
* **Políticas de gobernanza y privacidad:** **Cumple parcialmente.** Existen manuales internos pero carecen de aplicación técnica estricta.

---

## 5. Recomendaciones Estratégicas y Plan de Remediación

1. **Implementación Inmediata de RBAC y Menor Privilegio (Prioridad Crítica):**  
   Reestructurar los permisos en la base de datos de clientes para que únicamente el servicio de pagos y el personal auditado tengan acceso a información financiera.
2. **Cifrado Fuerte de Datos (Prioridad Crítica):**  
   Implementar cifrado AES-256 para bases de datos en reposo y forzar protocolos TLS 1.3 para todas las comunicaciones de comercio electrónico.
3. **Autenticación Multifactor (MFA) y Gestor de Identidades (Prioridad Alta):**  
   Desplegar un sistema centralizado de identidades (IAM) que exija contraseñas de al menos 12 caracteres y un segundo factor de autenticación para todos los empleados.
4. **Estrategia de Respaldos 3-2-1 y DRP (Prioridad Alta):**  
   Configurar copias de seguridad automatizadas y cifradas en almacenamiento en la nube, con pruebas periódicas de restauración de datos.
