GUION DE LA EXPOSICION E6 (10 min, maximo 8 diapositivas). A = Julian, B = Integrante 2

D1 (A, 1 min) Portada y ubicacion en RUP
- Equipo E6, modulo Cuentas de jugador y sesion, fases Pruebas y Transicion
- Cadena E1 Inicio -> E2 Requisitos -> E3 Analisis -> E4 Diseno -> E5 Construccion -> E6 Pruebas y transicion
- Hito que cerramos: liberacion del producto, aceptacion del cliente
- Duenos: A = 17 y 18, B = 19 y 20

D2 (A, 1 min) Eslabon de trazabilidad
- Insumos minimos: RF/RNF del modulo, CU Iniciar sesion, 3 capas y despliegue, componente de autenticacion
- Decir: "esto, en un proyecto real, lo producirian el Especificador, el Arquitecto y el Implementador"
- Alimentamos: defectos -> plan de iteracion siguiente; manual y resultados -> acta -> cierre

D3 (A, 1.5 min) Artefacto 17 Plan y casos de prueba
- Que es / para que: definir que, como y resultado esperado antes de ejecutar
- Quien: Disenador de pruebas. Fase: Elaboracion -> Construccion
- Ejemplo: CP-LOG-01 a 06, negativos CP-LOG-02, 03, 05, 06; cada caso nombra su RF/RNF

D4 (A, 1.5 min) Artefacto 18 Registro de defectos
- Que es / para que: evidencia de lo ejecutado y seguimiento hasta cerrar
- Quien: Tester. Fase: Construccion
- Ejemplo: DEF-001 bloqueo al 4.o intento (Alta, verificado), DEF-002 mensaje revela usuario (Media, abierto), DEF-003 contador no se reinicia (Media, verificado)

D5 (B, 1.5 min) Artefacto 19 Plan de despliegue
- Que es / para que: pasar del computador del equipo al usuario sin romper nada
- Quien: Desplegador. Fase: Transicion. Insumo: SAD de E4
- Mostrar el diagrama de despliegue: navegador, servidor Java 21, MariaDB, SMTP; pasos y plan de reversion

D6 (B, 1.5 min) Artefacto 20 Manual y acta
- Que es / para que: ensenar a usar el sistema y formalizar la aceptacion
- Quien: Redactor tecnico + Jefe de proyecto. Fase: Transicion
- Mostrar pantallas del manual y la tabla del acta: aceptado con observaciones por DEF-002

D7 (B, 1.5 min) Trazabilidad completa
- RNF-CUE-02 -> CU Iniciar sesion (A2) -> CP-LOG-03 -> DEF-001 -> AC-02
- Reflexion: si el bloqueo pasa a 5 intentos cambian RNF, CU, CP-LOG-03/06, codigo, manual y acta

D8 (B, 0.5 min) Pasamos a la dinamica
- Presentar las 4 preguntas de preguntas_dinamica.md

SI TE LLAMAN A EXPLICAR UN ARTEFACTO QUE NO ES TUYO (una linea cada uno)
- 17: lista de casos con datos y resultado esperado, derivados de los requisitos
- 18: tabla de ejecucion + defectos con severidad, pasos y estado
- 19: ambientes, instalacion, pasos, reversion, diagrama UML
- 20: manual de uso + acta con criterios, resultado y firma del cliente
- Auditoria cruzada: nuestra pareja es E5; antes de la sesion 2 revisar su carpeta y preparar una pregunta que nombre artefacto y linea
