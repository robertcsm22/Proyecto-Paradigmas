# Monitor IoT de tanque de agua

Proyecto Integrador · Paradigmas de Programación · UNA · Prof. Eddier López
Entrega: 11 de noviembre de 2026, 1:00 pm

Monitor de nivel de agua basado en ESP32 que avisa cuando el agua baja, detecta fugas,
controla una válvula de llenado simulada (servo) y guarda un histórico consultable desde
un dashboard web en red local.

## Integrantes y roles

| Integrante | Usuario GitHub | Módulo que lidera |
|------------|----------------|-------------------|
| _Nombre_   | @usuario       | Sensores y LCD |
| _Nombre_   | @usuario       | Control: servo, LED RGB, buzzer, pulsador |
| _Nombre_   | @usuario       | Backend Flask + SQLite |
| _Nombre_   | @usuario       | Dashboard y pruebas |

## Estructura del repositorio

```
tanque-iot/
├── firmware/            # código C++ del ESP32 (Arduino IDE)
│   └── tanque_iot/      # sketch: tanque_iot.ino + clases (.h/.cpp)
├── backend/             # Flask + SQLite (Python)
│   └── tests/           # pruebas de las funciones puras
├── dashboard/           # HTML + JS + Chart.js
├── docs/                # arquitectura, diagramas, paradigmas, manual
│   ├── diagramas/       # archivos .drawio y exportados .png
│   └── paradigmas/      # justificación de OO, eventos y funcional
├── pruebas/             # evidencias: fotos, videos, tablas de resultados
└── bitacoras/
    └── <nombre>/bitacora.md   # una carpeta por integrante
```

## Paradigmas aplicados

| Paradigma | Dónde | Evidencia |
|-----------|-------|-----------|
| Orientado a objetos | Firmware ESP32 | Clases `SensorNivel`, `SensorFuga`, `Valvula`, `Indicador`, `Alarma` |
| Orientado a eventos | Control y comunicación | Reacciones a nivel bajo, fuga, botón presionado, lectura recibida |
| Funcional | Backend | Funciones puras con `map`, `filter`, `reduce` (promedios, alarmas, consumo) |

Detalle en [docs/paradigmas/](docs/paradigmas/).

## Cómo ejecutar

_Completar en la semana final._

1. Firmware: ver [firmware/README.md](firmware/README.md)
2. Backend: ver [backend/README.md](backend/README.md)
3. Dashboard: ver [dashboard/README.md](dashboard/README.md)

## Pruebas

Plan y resultados en [pruebas/README.md](pruebas/README.md).
