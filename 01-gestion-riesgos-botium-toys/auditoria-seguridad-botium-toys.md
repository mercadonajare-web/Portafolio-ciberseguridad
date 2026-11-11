
# 🔍 Auditoría de Seguridad e Informe de Riesgos - Botium Toys

**Analista de Ciberseguridad:** Emmanuel Mercado Najar  
**Programa:** Certificado Profesional de Ciberseguridad de Google  
**Puntuación de Riesgo:** 8 / 10 (Alto)  

---

## 🎯 1. Alcance y Objetivos de la Auditoría
* **Alcance:** Revisa la totalidad del programa de seguridad de Botium Toys (equipos de empleados, red interna, sistemas y procesos de cumplimiento).
* **Objetivo:** Evaluar activos existentes y completar la lista de verificación de controles y cumplimiento para determinar las mejoras necesarias en la postura de seguridad según el marco **NIST CSF**.

---

## 📊 2. Lista de Verificación de Controles y Cumplimiento

### Evaluación de Controles Existentes
* ❌ **Principio de Menor Privilegio:** NO
* ❌ **Planes de Recuperación ante Desastres:** NO
* ✅ **Políticas de Contraseñas:** SÍ (Básicas)
* ❌ **Separación de Funciones:** NO
* ✅ **Cortafuegos (Firewall):** SÍ
* ❌ **Sistema de Detección de Intrusiones (IDS):** NO
* ❌ **Copias de Seguridad (Backups):** NO
* ✅ **Software Antivirus:** SÍ
* ✅ **Monitoreo Manual de Sistemas Heredados:** SÍ
* ❌ **Cifrado de Datos (En reposo y tránsito):** NO
* ❌ **Sistema de Gestión de Contraseñas:** NO
* ✅ **Cerraduras Físicas y Videovigilancia (CCTV):** SÍ
* ✅ **Detección / Prevención de Incendios:** SÍ

### Cumplimiento Normativo (PCI DSS, GDPR, SOC)
* ❌ **PCI DSS:** Incumplimiento por falta de cifrado y acceso generalizado a datos de tarjetas de crédito.
* ⚠️ **GDPR:** Cumple con la notificación de brechas en 72 horas, pero incumple en la clasificación/protección de PII/SPII de clientes de la UE.
* ⚠️ **SOC (1 y 2):** Mantiene disponibilidad e integridad, pero falla en la confidencialidad de datos sensibles.

---

## 💡 3. Recomendaciones para la Dirección de TI

1. **Urgente - Aplicar el Principio de Menor Privilegio (IAM):** Restringir el acceso generalizado para asegurar que los datos sensibles (PII/SPII) y de tarjetas de crédito solo sean accesibles por personal autorizado.
2. **Implementación de Cifrado Robusto:** Cifrar los datos en reposo y en tránsito (especialmente información de pago) para cumplir con las normativas PCI DSS.
3. **Gestión de Contraseñas y MFA:** Implementar un gestor centralizado de contraseñas, actualizar la complejidad mínima e implementar Autenticación de Múltiples Factores (MFA).
4. **Respaldos Automatizados (Backups) y Plan de Recuperación:** Establecer un sistema automático de copias de seguridad en un entorno de nube seguro y cifrado, junto con un plan de recuperación ante desastres.
