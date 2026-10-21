# Backend (Python · Flask · SQLite)

Paradigma: **funcional** en el procesamiento de datos (funciones puras con
`map`, `filter`, `reduce`, sin efectos secundarios).

## Archivos previstos

| Archivo | Contenido |
|---------|-----------|
| `app.py` | Rutas Flask: `POST /lecturas`, `GET /lecturas`, `GET /eventos`, sirve el dashboard |
| `db.py` | Conexión a SQLite y creación de tablas `lecturas` y `eventos` (RF-09) |
| `procesamiento.py` | Funciones puras: promedio diario, conteo de alarmas, consumo estimado |
| `requirements.txt` | Dependencias (`flask`) |
| `tests/test_procesamiento.py` | Pruebas de las funciones puras |

## Ejecutar

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
python app.py
```

El archivo `.db` se crea al iniciar y no se sube al repositorio.
