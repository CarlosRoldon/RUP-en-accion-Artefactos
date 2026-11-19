DINAMICA DE PREGUNTAS - E6 (formato: tarjetas A/B/C a mano alzada, 5 min)

P1 (que artefacto usarias?)
El profesor pregunta: "Si la salida a produccion sale mal y la base de datos queda a medias, que hacemos?". En que artefacto debe estar la respuesta?
a) Registro de defectos  b) Plan de despliegue  c) Manual de usuario
Correcta: b. El plan de despliegue contiene el plan de reversion (restaurar respaldo, volver a la version anterior). El registro de defectos solo deja evidencia de lo que fallo, no dice como volver atras. El manual ensena a usar el sistema, no a instalarlo.

P2 (encuentra el error)
Fragmento de nuestro caso de prueba: "CP-LOG-03 | RF-CUE-03 | Repetir intento con contrasena incorrecta | Resultado esperado: la cuenta se bloquea al 4.o intento". Cual es el defecto?
a) Falta la precondicion  b) El resultado esperado contradice RNF-CUE-02, que dice 3 intentos  c) El RF esta mal escrito
Correcta: b. Un caso de prueba hereda su resultado esperado del requisito; si no coincide, el tester aprobaria justo el defecto que debia detectar. La precondicion aparece en la tabla completa y el RF-CUE-03 si corresponde a bloqueo.

P3 (que artefacto usarias?)
El tester descubre que el contador de intentos no se reinicia tras entrar con exito. Donde queda la evidencia hasta que se corrija y verifique?
a) Plan de pruebas  b) Registro de defectos  c) Acta de aceptacion
Correcta: b. El registro sigue cada defecto (abierto, corregido, verificado). El plan define que probar antes de ejecutar; el acta solo resume el resultado final al cierre.

P4 (encuentra el error)
Fragmento de acta: "AC-03 Mensaje de error generico: Cumple. Decision: ACEPTADO SIN OBSERVACIONES". Segun nuestro registro de defectos, cual es el error?
a) El acta no tiene fecha  b) DEF-002 sigue abierto, entonces AC-03 no cumple y debe haber observaciones  c) Falta el manual
Correcta: b. El acta debe ser coherente con el registro de defectos; un defecto abierto contradice "sin observaciones". Esto es el tipo de inconsistencia entre artefactos que mas cuesta en RUP.
