---
layout: post
date: 2016-06-01 15:30
title: Funcionalidades Comunes
category: Funcionalidades Comunes
permalink: commons/
---

**Seguridad del sistema**

1. Autenticación (De usuarios y de Aplicaciones),
2. Autorización/Role Based Access Control,
3. Restricción de ejecución de métodos basados en roles,
4. Funcionalidades de bitácora que muestre información auditable (ingresos, uso de entradas del menú, definición de tablas auditables),
5. Registro de errores/excepciones del sistema para resúmenes estadísticos,
6. Solicitud de recuperación de contraseña (generación aleatoria, envío por correo).

**Ejecuciónn de procesos asíncronos**

1. Tareas programadas/procesos en batch:

	* De aplicación (tipo cron daemon),
	* Alerta por correo basadas en lógicas de negocios (por email o en sesiones de usuarios),
	* Alertas basadas en condiciones. Se poblan datos provenientes de la BD.

**API REST**

1. Definición de estándares y convenciones para los RESTful API