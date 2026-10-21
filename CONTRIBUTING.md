# Cómo trabajamos con Git

El enunciado evalúa la trazabilidad individual (req. 9): commits, bitácora y defensa
deben coincidir. Por eso:

- Cada integrante hace commits **desde su propia cuenta** de GitHub.
- Commits **pequeños y frecuentes**, no uno gigante al final.
- Lo que dice tu bitácora debe poder verse en tus commits.

## Ramas

| Rama | Uso |
|------|-----|
| `main` | Versión estable. Solo entra por Pull Request. |
| `develop` | Integración de lo que ya funciona de cada módulo. |
| `feature/<modulo>-<tarea>` | Trabajo de cada integrante. |

Ejemplos de ramas:

- `feature/firmware-sensor-nivel`
- `feature/firmware-lcd`
- `feature/firmware-valvula-histeresis`
- `feature/firmware-alarma-pulsador`
- `feature/firmware-wifi-envio`
- `feature/backend-api-lecturas`
- `feature/backend-funciones-puras`
- `feature/dashboard-grafico`
- `docs/arquitectura`
- `pruebas/precision-nivel`

Flujo:

```bash
git checkout develop
git pull
git checkout -b feature/firmware-sensor-nivel
# ...trabajar...
git add .
git commit -m "feat(firmware): lectura de distancia con HC-SR04"
git push -u origin feature/firmware-sensor-nivel
# abrir Pull Request hacia develop en GitHub
```

Al cierre de cada semana se hace un PR de `develop` a `main`.

## Mensajes de commit

Formato: `tipo(área): descripción corta en español`

| Tipo | Cuándo |
|------|--------|
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de un error |
| `refactor` | Reorganizar código sin cambiar comportamiento (ej. pasar a clases) |
| `docs` | Documentación, diagramas, README |
| `test` | Pruebas y evidencias |
| `bitacora` | Entrada de bitácora |
| `chore` | Configuración, .gitignore, etc. |

Áreas: `firmware`, `backend`, `dashboard`, `docs`, `pruebas`, `bitacora`.

Ejemplos:

```
feat(firmware): mostrar distancia en LCD I2C
feat(firmware): histéresis de válvula (abre <20 %, cierra >90 %)
refactor(firmware): separar SensorNivel en su propia clase
feat(backend): POST /lecturas guarda en SQLite
feat(backend): promedio diario con reduce
feat(dashboard): gráfico histórico con Chart.js
test(pruebas): tabla de precisión en 6 niveles
docs(docs): diagrama de arquitectura v1
bitacora(maria): entrada semana 2
```

## Hitos (tags)

| Tag | Fecha | Contenido |
|-----|-------|-----------|
| `v0.1-semana1` | 24 oct | Lectura del HC-SR04 en LCD, diagrama v1 |
| `v0.2-semana2` | 31 oct | Dispositivo completo en clases |
| `v0.3-semana3` | 7 nov | Backend + dashboard conectados |
| `v1.0-entrega` | 10 nov | Versión final con pruebas y README |

```bash
git tag -a v0.1-semana1 -m "Semana 1: primeras lecturas"
git push origin v0.1-semana1
```

## Configuración inicial (cada integrante, una vez)

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "el-correo-de-tu-cuenta@github.com"
git clone https://github.com/<organizacion-o-usuario>/tanque-iot.git
```

El correo debe ser el de tu cuenta de GitHub; si no, los commits no aparecen a tu nombre.
