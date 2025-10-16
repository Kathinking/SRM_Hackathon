# Run instructions (backend + frontend)

Backend (Flask)
- Open terminal, cd to backend folder:
  - Windows (PowerShell):
    ```
    python -m venv venv
    .\venv\Scripts\Activate.ps1
    pip install flask flask-cors flask-jwt-extended werkzeug
    cd backend
    python app.py
    ```
  - Unix / macOS:
    ```
    python3 -m venv venv
    source venv/bin/activate
    pip install flask flask-cors flask-jwt-extended werkzeug
    cd backend
    python app.py
    ```
- By default app listens on port 5050 (set PORT env var to change).

Frontend (Vite + React)
- Open terminal, cd to frontend folder:
  ```
  cd frontend
  npm install
  npm run dev
  ```
- Dev server default: http://localhost:5173

Run both together
- Open two terminals (one backend, one frontend) and follow steps above.
- Or install "concurrently" in the project root and run both (example):
  ```
  npm i -D concurrently
  concurrently "cd backend && . ./venv/bin/activate && python app.py" "cd frontend && npm run dev"
  ```

Notes
- Ensure environment variables for backend (SECRET_KEY, JWT_SECRET_KEY) are set if not using defaults.
- If backend or frontend ports differ, update FRONTEND_ORIGIN in backend env so CORS allows the frontend origin.
