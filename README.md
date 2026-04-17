# Prácticas 1–5 — SC504 Lenguajes de programación

Repositorio con scripts **Oracle SQL / PL-SQL** para el curso SC504: creación de esquema veterinario (prefijo `FIDE_`), usuarios (`TAREA1` … `TAREA4`), procedimientos, paquetes, secuencias y disparadores.

## Requisitos

- Oracle Database con privilegios suficientes para `CREATE USER`, `GRANT`, objetos en otros esquemas cuando el script lo requiera.
- Cliente SQL*Plus, SQL Developer u otro editor que ejecute scripts `.sql`.

## Convención de nombres de archivos

Los archivos usan prefijos por tarea y tipo de operación:

| Prefijo   | Significado                                      |
|-----------|--------------------------------------------------|
| `tareaN_` | Tarea o entrega asociada (1–4).                  |
| `ddl_`    | Definición de objetos (tablas, usuarios, etc.).  |
| `dml_`    | Consultas o pruebas de ejecución.                |

## Scripts SQL (renombrados)

### Tarea 1 — Esquema base y usuario

| Archivo | Contenido |
|---------|-----------|
| `tarea1_ddl_usuario_tarea1.sql` | Usuario `TAREA1` y privilegios básicos. |
| `tarea1_ddl_tablas_relaciones.sql` | Creación de tablas `FIDE_*` con relaciones (versión resumida). |
| `tarea1_ddl_esquema_fide_completo.sql` | Esquema `FIDE_*` con restricciones, claves y `TABLESPACE` (versión detallada). |

Ejecuta **un solo** script de tablas según el que use tu guía (`tablas_relaciones` o `esquema_fide_completo`), no ambos si se solapan.

### Tarea 2 — Usuario `TAREA2` y procedimientos

| Archivo | Contenido |
|---------|-----------|
| `tarea2_ddl_usuario_permisos.sql` | Usuario `TAREA2` y permisos sobre tablas de `TAREA1`. |
| `tarea2_ddl_usuario_y_procedimientos.sql` | Mismo usuario más procedimientos almacenados (entrega tipo práctica 2). |
| `tarea2_ddl_procedimientos_almacenados.sql` | Definición de procedimientos sobre `TAREA1`. |
| `tarea2_ddl_drop_procedimientos.sql` | Elimina procedimientos existentes antes de volver a crearlos. |
| `tarea2_dml_pruebas_procedimientos.sql` | Consultas a `user_objects` y llamadas de prueba (`DBMS_OUTPUT`). |

### Tarea 3 — Usuario `TAREA3` y paquete

| Archivo | Contenido |
|---------|-----------|
| `tarea3_ddl_usuario_permisos.sql` | Usuario `TAREA3` y permisos. |
| `tarea3_ddl_package_spec_fide_tarea3_pck.sql` | Especificación del paquete `FIDE_TAREA3_PCK`. |
| `tarea3_ddl_package_body_fide_tarea3_pck.sql` | Cuerpo del paquete `FIDE_TAREA3_PCK`. |
| `tarea3_dml_pruebas_package_funciones.sql` | Verificación del paquete y funciones del mismo. |

### Tarea 4 — Usuario `TAREA4`, auditoría, secuencias y disparadores

| Archivo | Contenido |
|---------|-----------|
| `tarea4_ddl_usuario_auditoria_triggers.sql` | Usuario `TAREA4`, columnas de auditoría tipo `AUDIT_*` y disparadores asociados. |
| `tarea4_ddl_usuario_secuencias_triggers.sql` | Usuario `TAREA4` con privilegios ampliados, columnas de control, secuencias y disparadores. |

Son **dos variantes** de la misma tarea: revisa cuál corresponde a tu entrega; no mezcles sin revisar duplicidad de objetos.

## Orden sugerido de ejecución (resumen)

1. Crear usuario y tablas de la tarea 1 (`tarea1_ddl_usuario_tarea1.sql` → script de tablas elegido).
2. Tarea 2: usuario → (opcional) `drop` → procedimientos → pruebas.
3. Tarea 3: usuario → spec del paquete → body → pruebas.
4. Tarea 4: elegir **un** script completo de tarea 4 según la variante requerida.

## Seguridad

Los scripts incluyen contraseñas en texto plano con fines académicos. En entornos reales hay que usar perfiles seguros, gestores de secretos o scripts parametrizados, y no versionar credenciales.

## Autoría

Incluye material de prácticas del curso SC504; parte de los nombres de archivo refleja entregas y convenciones del estudiante.
