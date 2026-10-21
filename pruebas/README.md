# Pruebas

Evidencias en `fotos/`, `videos/` y tablas en `resultados/`.
Nombrar archivos así: `P01-precision-nivel-50pct.jpg`, `P03-valvula-histeresis.mp4`.

| ID | Prueba | Cómo se hace | Resultado esperado | Valida | Resultado obtenido | Evidencia |
|----|--------|--------------|--------------------|--------|--------------------|-----------|
| P01 | Precisión del nivel | Comparar con la regla en 6 niveles | Error < ±1 cm | RF-01, RNF-01 | | |
| P02 | Indicadores por estado | Nivel alto, medio y bajo | RGB y LCD cambian según umbral | RF-02, RF-03 | | |
| P03 | Válvula con histéresis | Vaciar bajo 20 % y llenar sobre 90 % | Abre y cierra una sola vez por umbral | RF-06 | | |
| P04 | Detección de fuga | Mojar el sensor de agua | Buzzer suena y se registra el evento | RF-04, RF-05 | | |
| P05 | Silenciar alarma | Presionar el pulsador con alarma activa | Buzzer se apaga | RF-07 | | |
| P06 | Envío y registro | Revisar la BD tras 5 minutos | Una lectura cada 5–10 s, sin pérdidas | RF-08, RF-09 | | |
| P07 | Dashboard | Cambiar nivel y mirar la web | Gráfico y estado se actualizan solos | RF-10, RNF-06 | | |
| P08 | Caída de WiFi | Apagar router/hotspot | Sigue operando localmente | RNF-02 | | |

## Limitaciones encontradas

- Error del ultrasónico con agua en movimiento
- Distancia mínima del sensor (~2 cm)
- El sensor de agua solo indica presencia
- Dependencia de la red local

## Mejoras posibles

- Notificaciones al celular
- Sensor de nivel sumergible
- Alimentación solar
- Servidor en la nube
