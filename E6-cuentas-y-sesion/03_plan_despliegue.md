ARTEFACTO 19 - PLAN DE DESPLIEGUE
Modulo: Cuentas de jugador y sesion | Duenos: Integrante 2 | Fase: Transicion | Insumo: SAD (E4)

1. AMBIENTES
Ambiente | Proposito | Quien accede
Desarrollo | Programar y probar localmente | Equipo
Pruebas | Ejecutar los casos de 01_plan_y_casos_de_prueba.md | Equipo y profesor
Produccion | Uso real por los jugadores | Jugadores

2. REQUISITOS DE INSTALACION
- Java 21 en el servidor de aplicacion.
- MariaDB 10.x con la base rpgmanager y un usuario con permisos solo sobre esa base.
- Acceso a un servidor SMTP (puerto 587) para el correo de recuperacion (RF-CUE-04).
- Puertos: 443 (HTTPS) al servidor de aplicacion, 3306 solo entre aplicacion y base de datos.

3. PASOS DE DESPLIEGUE
1) Hacer respaldo de la base de datos actual (mysqldump rpgmanager).
2) Ejecutar el script SQL de tablas jugador y sesion (viene del modelo de datos de E5).
3) Configurar variables de entorno: URL de la base, usuario, clave, servidor SMTP.
4) Copiar rpgmanager-cuentas.jar al servidor y arrancarlo.
5) Prueba de humo: abrir la pantalla Iniciar sesion y ejecutar CP-LOG-01.
6) Si pasa, anunciar la liberacion; si falla, ir al plan de reversion.

4. PLAN DE REVERSION
- Disparador: la prueba de humo falla o aparece un defecto critico en la primera hora.
- Pasos: 1) detener el servicio nuevo 2) restaurar el respaldo del paso 1 3) arrancar el jar de la version anterior 4) repetir la prueba de humo 5) registrar el motivo en 02_registro_defectos.md.
- Responsable: desplegador. Tiempo maximo: 30 minutos.

5. DIAGRAMA DE DESPLIEGUE
Ver 03_diagrama_despliegue.puml (exportar tambien como 03_diagrama_despliegue.png).
