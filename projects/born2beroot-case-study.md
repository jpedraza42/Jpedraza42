# Born2beroot — Caso de estudio de administración de sistemas

**Contexto:** proyecto formativo completado en **42 Málaga Fundación Telefónica**.  
**Tipo de trabajo:** configuración, administración y defensa de una máquina virtual; no es un repositorio de aplicación.  
**Fuente:** documento personal de preparación de la defensa (6 páginas), elaborado por el autor.  
**Evidencia disponible:** guion de comprobaciones, comandos y explicaciones. No se adjuntan registros reales de ejecución, imágenes de la VM, capturas ni una certificación de evaluación.

## Objetivo

Preparar y explicar la configuración de una máquina virtual basada en Debian, abordando virtualización, almacenamiento, usuarios, permisos, acceso remoto, privilegios, monitorización y tareas programadas.

## Alcance documentado en el guion de defensa

| Área | Comprobación o explicación preparada |
| --- | --- |
| Integridad | Verificación de la firma de la VM con `sha1sum` y comparación con `signature.txt`. |
| Virtualización y distribución | Qué es un hipervisor, por qué Debian y diferencias con Rocky Linux; comparación entre `apt` y `aptitude`. |
| Configuración mínima | Verificar ausencia de entorno gráfico, distribución Debian y usuario no-root. |
| Acceso y servicios | Estado de UFW y SSH, conexión por el puerto 4242 y comprobación de restricciones de acceso de root. |
| Identidades | Grupos `sudo` y `user42`, creación de usuario de prueba y grupo `evaluating`. |
| Política de contraseñas | Lectura de parámetros de `pwquality.conf` y `login.defs`. |
| Almacenamiento y sistema | Cambios de hostname, inspección de particiones con `lsblk` y explicación de LVM (PV, VG, LV). |
| Privilegios y trazabilidad | Revisión de `sudo`, sus directivas y los registros de operaciones. |
| Monitorización | Explicación de `monitoring.sh` y de sus fuentes para CPU, RAM, disco, red y actividad de usuarios. |
| Planificación | Consulta de `cron` cada diez minutos, prueba a un minuto y comprobaciones tras reinicio. |

## Cómo preparé la defensa

Mi documento organiza los puntos por fases de evaluación: firma, explicación general, instalación mínima, usuarios y grupos, hostname y LVM, sudo, SSH, y monitorización. En cada apartado combina un **comando de comprobación** con una **explicación de lo que debía observarse**. Esta estructura permite comunicar decisiones técnicas y justificar el trabajo ante otra persona.

Algunos ejemplos de las verificaciones preparadas:

```bash
cat /etc/os-release
lsblk
id <usuario_de_prueba>
sudo ufw status verbose
sudo systemctl status ssh
sudo crontab -u root -l
```

Los comandos son ejemplos documentales: **no se ejecutan automáticamente** y algunos requieren privilegios o un entorno de pruebas. El documento original también contempla acciones que modifican el sistema; por eso aquí solo se muestran verificaciones no destructivas.

## Lo que demuestra este proyecto

- Capacidad para estudiar y explicar componentes básicos de una máquina Linux.
- Organización de un procedimiento técnico verificable y comprensible.
- Preparación de una defensa estructurada, combinando evidencia técnica y comunicación.
- Comprensión práctica de que configurar un sistema requiere comprobar su estado, no solo enumerar comandos.

Estas competencias complementan mi objetivo profesional de **seleccionar, formar, acompañar y motivar equipos tecnológicos**. No convierten por sí solas este ejercicio en experiencia laboral de administración de sistemas o dirección de ingeniería.

## Límites y atribución

- El proyecto fue completado según la experiencia declarada por su autor. Este caso de estudio se basa en su **documento de preparación de la defensa**, no en una auditoría independiente de la VM.
- No se publica la imagen de disco, su firma, contraseñas, direcciones IP, identificadores de acceso, historiales de comandos ni registros reales.
- La documentación del ejercicio no prueba por sí misma que todos los controles se ejecutaran con éxito durante la defensa. Para acreditarlo serían necesarias pruebas o resultados verificables.
- Es un proyecto educativo de **42 Málaga Fundación Telefónica**; esta publicación personal no supone respaldo institucional.

## Próximas mejoras documentales

Añadir, si se conservan y pueden compartirse sin datos sensibles, la fecha de evaluación, el resultado obtenido y un breve resumen personal de los problemas resueltos durante la instalación y la defensa.
