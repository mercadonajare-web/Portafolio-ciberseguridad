# Aplicar filtros a consultas SQL

## Descripción del proyecto
Como analista de seguridad en una organización, investigué posibles incidentes de acceso no autorizado y gestioné el inventario de equipos que requerían actualizaciones críticas de seguridad. Mediante el uso de consultas y filtros avanzados en SQL sobre las tablas `log_in_attempts` y `employees`, logré aislar registros sospechosos fuera del horario laboral, identificar conexiones de origen anómalo y segmentar dispositivos por departamento y ubicación física para mitigar vulnerabilidades de forma oportuna.

---

## Recuperar tras horas de intentos de inicio de sesión fallidos

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = 0;
```

**Explicación de la consulta:**
Esta consulta extrae todas las columnas de la tabla `log_in_attempts` aplicando dos condiciones simultáneas mediante el operador lógico `AND`. Primero, filtra las horas registradas en `login_time` posteriores a las `'18:00:00'` utilizando el operador de comparación mayor que (`>`). Segundo, exige que la columna `success` sea igual a `0` (valor booleano equivalente a `FALSE`), lo que garantiza recuperar únicamente los intentos de inicio de sesión que fallaron después del horario laboral.

---

## Recuperar intentos de inicio de sesión en fechas específicas

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

**Explicación de la consulta:**
Para investigar el incidente del 9 de mayo y su actividad previa, esta consulta filtra la columna `login_date` utilizando el operador lógico `OR`. Al combinar ambas fechas encerradas entre comillas simples (`'2022-05-09'` y `'2022-05-08'`), el motor de base de datos devuelve cualquier registro de inicio de sesión que haya ocurrido en cualquiera de esos dos días, permitiendo analizar el historial completo del evento sospechoso.

---

## Recuperar intentos de inicio de sesión fuera de México

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

**Explicación de la consulta:**
Esta consulta identifica los intentos de acceso originados fuera de México combinando el operador de negación `NOT` con el operador de coincidencia de patrones `LIKE`. Dado que la columna `country` almacena tanto `'MEX'` como `'MEXICO'`, el comodín `%` en `'MEX%'` abarca cualquier cadena de texto que comience con esas tres letras; al anteponer `NOT`, SQL excluye todas esas variantes y muestra exclusivamente el tráfico proveniente de otros países.

---

## Recuperar empleados en Marketing

```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East-%';
```

**Explicación de la consulta:**
Para localizar los equipos que requieren actualización de seguridad en un área específica, esta consulta examina la tabla `employees` uniendo dos criterios obligatorios con el operador `AND`. Filtra los registros donde la columna `department` coincide exactamente con `'Marketing'` y utiliza el operador `LIKE` junto con el comodín `'East-%'` en la columna `office` para incluir todas las oficinas ubicadas dentro del edificio Este (como `East-170` o `East-320`).

---

## Recuperar empleados en Finanzas o Ventas

```sql
SELECT *
FROM employees
WHERE department = 'Sales' OR department = 'Finance';
```

**Explicación de la consulta:**
Esta consulta recupera de la tabla `employees` al personal que pertenece a los departamentos de Ventas (`'Sales'`) o Finanzas (`'Finance'`) mediante el operador lógico `OR`. De este modo, basta con que el registro de un empleado cumpla con uno de los dos valores en la columna `department` para ser incluido en la lista de equipos pendientes por actualizar.

---

## Recuperar todos los empleados que no pertenecen a TI

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

**Explicación de la consulta:**
Dado que el equipo de Tecnología de la Información ya recibió el parche de seguridad, esta consulta utiliza el operador `NOT` frente a la condición `department = 'Information Technology'` en la tabla `employees`. Esto descarta a todo el personal de TI y devuelve únicamente los registros de los empleados del resto de departamentos que aún necesitan la actualización.

---

## Resumen
A lo largo de esta investigación utilicé operadores de comparación y lógicos en SQL (`AND`, `OR`, `NOT` y `LIKE`) para filtrar grandes volúmenes de registros de autenticación y activos corporativos con precisión. Estas consultas permitieron acotar incidentes de seguridad por fecha, hora y ubicación geográfica, así como identificar rápidamente los equipos de empleados que requerían parches críticos para mantener protegida la infraestructura de la organización.
