# Dashboard (HTML · JavaScript · Chart.js)

Muestra el nivel actual, el estado de la válvula, el gráfico histórico y la lista de
alarmas (RF-10). Se actualiza solo cada ≤10 s sin recargar la página (RNF-06).

## Archivos previstos

| Archivo | Contenido |
|---------|-----------|
| `index.html` | Estructura de la página |
| `css/estilos.css` | Estilos |
| `js/app.js` | `fetch` periódico a `/lecturas` y `/eventos`, actualiza la vista |
| `js/grafico.js` | Configuración de Chart.js |

Flask sirve esta carpeta; se abre en `http://<ip-de-la-laptop>:5000`.
