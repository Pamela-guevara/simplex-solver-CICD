# Simplex Solver

Proyecto de Ingeniería y Calidad de Software
Aplicación web para resolver Programación Lineal con método Simplex


## Descripción

Aplicación Web que permite resolver problemas de programación lineal mediante el método simplex.

Permite ingresar datos del problema mediante interfaz gráfica. Puede seleccionarse si se trata de maximización o minimización. Se obtienen los resultados de variables, valor óptimo, iteraciones intermedias, precio sombra y gráfico (cuando tiene 2 variables)

Además, permite obtener los resultados en un documento PDF.

## Metodología

El desarrollo de este proyecto se basa en SCRUM, ejecutandose en sprints.
Se crea código backend, que incluyen sus respectivos tests unitarios realizados con PyTest.

## Tecnologías/Frameworks

- Backend: Python 3.X y FastAPI
- Fronted: React - Vite para desarrollo

---

## Estructura

- `backend/`: API FastAPI para resolver problemas y cachear últimas operaciones. Docker para containerizar el servicio. Fly.io para deploy.
- `frontend/`: Componentes para la interfaz de usuario realizadas en React. Nginx como proxy. Docker para containerizar el servicio. Fly.io para deploy.
- `docker-compose`: Para ejecutar ambos servicios de forma local con docker.

## Requisitos
Para despliegue local, es necesario que tenga instalado:

- Python 3.10 o superior
- Docker
- Node 20 o superior

Siga las instrucciones a continuación para el despliegue local.

## Backend

```bash
cd backend
python -m venv .venv
. .venv/Scripts/activate
pip install -r requirements.txt
uvicorn app.app:app --reload --host 0.0.0.0 --port 8000
```

- Docs: `http://localhost:8000/docs`
- Healt: `http://localhost:8000/healt`

## Frontend
```bash
cd frontend
npm install
npm run dev
```
- App: `http://localhost:5173`

## Tests

```bash
cd backend
pytest ./test_simplex_api.py

python -m tests.test_manual
```
## Aplicación web
`https://simplex-frontend.fly.dev/`