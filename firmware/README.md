# Firmware (ESP32 · C++ · Arduino IDE)

Paradigmas: **orientado a objetos** (una clase por componente físico) y
**orientado a eventos** (reacciones a nivel bajo, fuga, botón, lectura enviada).

## Archivos previstos en `tanque_iot/`

| Archivo | Contenido |
|---------|-----------|
| `tanque_iot.ino` | `setup()` y `loop()`: crea los objetos y despacha eventos |
| `SensorNivel.h/.cpp` | HC-SR04 → distancia → % de llenado (RF-01) |
| `SensorFuga.h/.cpp` | Sensor de agua en la base (RF-05) |
| `Valvula.h/.cpp` | Servo con histéresis 20 % / 90 % (RF-06) |
| `Indicador.h/.cpp` | LCD 16x2 + LED RGB (RF-02, RF-03) |
| `Alarma.h/.cpp` | Buzzer + pulsador para silenciar (RF-04, RF-07) |
| `Comunicacion.h/.cpp` | WiFi + HTTP POST cada 5–10 s (RF-08) |
| `config.h` | Pines, umbrales, altura del tanque |
| `secrets.example.h` | Plantilla de SSID/clave/IP del servidor |

`secrets.h` (con la clave real del WiFi) **no se sube**: está en `.gitignore`.
Cada quien copia `secrets.example.h` como `secrets.h` y pone sus datos.

## Pines

| Componente | GPIO |
|------------|------|
| HC-SR04 Trig | 5 |
| HC-SR04 Echo (con divisor 1 kΩ / 2 kΩ) | 18 |
| Sensor de agua | 34 |
| LCD SDA / SCL | 21 / 22 |
| LED RGB R / G / B | 25 / 26 / 27 |
| Buzzer | 14 |
| Servo | 13 |
| Pulsador (INPUT_PULLUP) | 4 |

## Librerías

- `LiquidCrystal_I2C`
- `ESP32Servo`
- `WiFi.h`, `HTTPClient.h` (incluidas con el soporte ESP32)
