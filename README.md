# Smart ToDo Manager

Smart ToDo Manager este o aplicație web fullstack pentru gestionarea sarcinilor zilnice, realizată cu FastAPI, SQLite și un frontend bazat pe HTML, JavaScript și Bootstrap.

Aplicația permite utilizatorilor să se înregistreze, să se autentifice și să gestioneze propriile sarcini într-un mod simplu și eficient.

---

## Demo

Aplicația este disponibilă online la adresa:

https://your-app.onrender.com

---

## Funcționalități

* Înregistrare utilizator
* Autentificare folosind JWT
* Creare sarcini
* Vizualizare listă de sarcini
* Editare titlu și descriere
* Marcare sarcină ca finalizată
* Ștergere sarcini
* Filtrare sarcini nefinalizate
* Dashboard cu statistici (total, active, finalizate)
* Interfață responsive

---

## Tehnologii utilizate

### Backend

* Python 3
* FastAPI
* SQLite3
* Pydantic
* PyJWT
* Passlib (bcrypt)

### Frontend

* HTML5
* JavaScript
* Bootstrap 5

### Deployment

* Render.com
* GitHub

---

## Structura proiectului

```text
fastapi-lab5/
├── main.py
├── requirements.txt
├── README.md
├── .gitignore
└── static/
    └── index.html
```

---

## Rulare locală

1. Clonare repository:

```bash
git clone https://github.com/VasyaSuperr/Aplica-ie-practic-folosind-Python-i-FastAPI
cd fastapi-lab5
```

2. Creare mediu virtual:

```bash
python3 -m venv venv
source venv/bin/activate
```

3. Instalare dependențe:

```bash
pip install -r requirements.txt
```

4. Pornire server:

```bash
uvicorn main:app --reload
```

5. Acces aplicație:

http://127.0.0.1:8000

---

## Configurare pe Render

Pentru rularea aplicației pe Render:

1. Se creează un Web Service din repository-ul GitHub
2. Se setează comenzile:

```text
Build Command: pip install -r requirements.txt
Start Command: uvicorn main:app --host 0.0.0.0 --port $PORT
```

3. Se definesc variabilele de mediu în Render:

```text
SECRET_KEY = valoare securizată
ALGORITHM = HS256
EXPIRARE_TOKEN_MINUTE = 30
DATABASE_PATH = /tmp/sarcini.db
```

---

## Endpoint-uri principale

| Metodă | Endpoint                  | Descriere                       |
| ------ | ------------------------- | ------------------------------- |
| POST   | /inregistrare             | Creare cont utilizator          |
| POST   | /autentificare            | Autentificare și generare token |
| GET    | /sarcini                  | Listare sarcini                 |
| POST   | /sarcini                  | Creare sarcină                  |
| PUT    | /sarcini/{id}             | Editare sarcină                 |
| PATCH  | /sarcini/{id}/finalizeaza | Marcare ca finalizată           |
| DELETE | /sarcini/{id}             | Ștergere sarcină                |
| GET    | /healthz                  | Verificare stare aplicație      |

---

## Securitate

* Parolele sunt stocate sub formă de hash folosind bcrypt
* Autentificarea se realizează prin JWT
* Fiecare utilizator poate accesa doar propriile date

---

## Limitări

* Baza de date SQLite nu este persistentă în mediul Render gratuit
* Datele pot fi pierdute la redeploy

---

## Concluzie

Aplicația demonstrează implementarea completă a unui sistem web modern folosind FastAPI, incluzând backend REST, autentificare securizată, frontend interactiv și deployment în cloud.

---

## Autor

Proiect realizat pentru laboratorul de servicii web.
