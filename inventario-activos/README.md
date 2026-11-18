# Inventario de Activos Domésticos (Home Asset Inventory)

Actividad práctica del **Certificado Profesional de Ciberseguridad de Google** enfocada en identificar dispositivos conectados a una red doméstica, su nivel de acceso, propietario y clasificación de sensibilidad de datos.

## Activos Inventariados

| # | Asset | Network access | Owner | Location | Notes | Sensitivity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Network router | Continuous | Internet service provider (ISP) | On-premises | Has a 2.4 GHz and 5 GHz connection. All devices on the home network connect to the 5 GHz frequency. | Confidential |
| 2 | Desktop | Occasional | Homeowner | On-premises | Contains private information, like photos. | Restricted |
| 3 | Guest smartphone | Occasional | Friend | On and Off-premises | Connects to my home network. | Internal-only |
| 4 | TV | Continuous | Homeowner | On-premises | Connects to my home network. | Public |
| 5 | Alexa | Continuous | Homeowner | On-premises | No contains personal information | Public |
| 6 | Laptop | Continuous | Homeowner | Sala de estar | Contiene información sensible | Confidential |

## Niveles de Sensibilidad Aplicados
* **Restricted:** Acceso estricto (*need-to-know*) para información privada crítica.
* **Confidential:** Acceso limitado a usuarios autorizados.
* **Internal-only:** Disponible únicamente para usuarios conectados dentro de la red local.
* **Public:** Activos sin datos personales sensibles almacenados.
