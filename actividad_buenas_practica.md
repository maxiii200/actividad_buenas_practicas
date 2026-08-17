# actividad_buenas_practicas

## Parte 1: Organizacion y nomenclatura

## Problema que presenta: Es un nombre demasiado generico y con muy poca informacion de datos o de algun tipo de entidad.
## Propuesta: articulos
## Por que es mejor: Es un nombre sencillo de identificar para cualquier integrante del equipo y se identifica claramente la entidad 

## Problema que presenta: Es un nombre con caracteres ambiguos por ejemplo la 'x' no aporta contexto del contenido de la tabla 
## Propuesta: parametros_sistema
## Por que es mejor: Especifica claramente la naturaleza y utilidad de los datos 

## Problema que presenta: El nombre presenta especifico en el nombre de la tabla, lo que vuelve la estructura obsoleta y difícil de mantener al cambiar de año
## Propuesta: clientes 
## Por que es mejor: Porque la separación por años o fechas de registro debe manejarse mediante una columna tipo DATE dentro de la misma tabla, no creando tablas nuevas

## Problema que presenta: El nombre no describe el rol, los permisos o el área a la que pertenece el usuario de base de datos
## Propuesta: usr_admin
## Por que es mejor: Identifica rápidamente el nivel de acceso y el departamento al que pertenece el usuario

## Problema que presenta: Es un objeto temporal o experimental que fue dejado por error en un entorno de producción
## Propuesta: test_nueva_prueba
## Por que es mejor: Evita la basura digital, previene confusiones en el entorno de producción y mantiene el esquema limpio

## Problema que presenta: Este tambien es un nombre generico que no indica sobre qué tabla o columnas está aplicado el índice
## Propuesta: idx_clientes_email
## Por que es mejor: Sigue una convención estandar que facilita la administración y optimización de consultas

## Parte 2: Estrategia de respaldo

## Estrategia Propuesta:
## Respaldo Completo: Diario, ejecutado en horario de bajo tráfico de la tienda online
## Respaldo Diferencial: Cada 4 horas durante la jornada laboral

## Donde se almacenan los datos: 
## Principio 3-2-1: Tres copias de los datos, en dos medios distintos, con al menos una copia fuera de la sede
## Lugar propuesto: Almacenamiento seguro en la nube en una región geográficamente distinta al servidor principal, con cifrado en reposo y políticas de acceso restringido. Nunca en el mismo disco ni servidor donde corre la base de datos de producción

## Como se identifica cada archivo: 
## Formato: `bkp_<nombre_bd>_<tipo>_<AAAAMMDD_HHMMSS>.<ext>`

## Importancia de las pruebas periódicas de restauración:
## Un respaldo que no ha sido probado no es un respaldo válido.
  ## Probar periódicamente la restauración en un entorno de pruebas garantiza:
  ##  1. Que los archivos de backup no estén corruptos.
  ##  2. Que el procedimiento de recuperación funcione correctamente.
  ##  3. Medir el tiempo real de recuperación (RTO - *Recovery Time Objective*) y la cantidad máxima de datos que se podrían perder 

## Parte 3: Registro de Cambios

### Bitácora de Registro

| Campo | Información |
| :--- | :--- |
| **Fecha y hora** | 2026-08-17 14:30:00 UTC |
| **Responsable** | Administrador DBA (`dba_admin`) |
| **Cambio realizado** | Creación de usuario de base de datos con permisos restringidos de lectura para el equipo de ventas. |
| **Script/comando utilizado** | *Ver bloque de código adjunto abajo* |
| **Motivo del cambio** | Proveer acceso seguro al área de ventas para consultar catálogos e historial de ventas sin riesgo de modificación o borrado accidental de datos. |

### Script / Comando Utilizado
  
