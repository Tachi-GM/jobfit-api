# JobFit API

Backend separado para gestionar un perfil profesional, ofertas laborales,
análisis de compatibilidad y postulaciones.

## Fase 1

La primera fase practica Git, PowerShell, entornos virtuales y pytest. La API
solo expone `GET /health` como puente inicial hacia HTTP/REST.

## Preparación en PowerShell

```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
```

## Validaciones

```powershell
python -m pytest -q
python -m pytest --collect-only -q
python -m compileall app tests
git diff --check
```

## Ejecutar la API

```powershell
python -m uvicorn app.main:app --reload
```

Luego se puede consultar `http://127.0.0.1:8000/health`, que devuelve:

```json
{"status": "ok"}
```
