📚 PostgreSQL Connectivity using SQLAlchemy + FastAPI
This project demonstrates how to connect a PostgreSQL database using SQLAlchemy ORM in a FastAPI-based Python project. It includes:

Database engine setup

Session management

Table creation logic

A sample Book model

PostgreSQL connection configuration

🔧 Project Structure
bash
Copy
Edit
project-root/
│
├── Connectivity/
│   ├── db.py          # Database connection, session, table creation
│   └── models.py      # Book model with SQLAlchemy ORM
│
├── requirements.txt   # Project dependencies
├── main.py            # (Your app entry point - optional)
└── README.md          # Project documentation
🛠️ Setup Instructions
1. Clone the repository
bash
Copy
Edit
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
2. Create a virtual environment
bash
Copy
Edit
python -m venv venv
source venv/bin/activate   # For Linux/Mac
venv\Scripts\activate      # For Windows
3. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
🗃️ PostgreSQL Database Configuration
Ensure you have PostgreSQL running locally and a database created (e.g., test1).

Your connection string (in db.py) should be updated like this:

python
Copy
Edit
SQLALCHEMY_DATABASE_URL = "postgresql://postgres:<your_password>@localhost:5432/<your_db>"
For example:

python
Copy
Edit
SQLALCHEMY_DATABASE_URL = "postgresql://postgres:Rashmeet0099@localhost:5432/test1"
✅ Creating Tables
You can create all tables using:

python
Copy
Edit
from Connectivity.db import create_table
create_table()
Or call create_table() inside your main.py before starting the FastAPI app.

🧾 Sample Model (models.py)
python
Copy
Edit
class Book(Base):
    __tablename__ = 'books'
    id = Column(Integer, primary_key=True, index=True)
    title = Column(String, index=True)
    description = Column(String, index=True)
    author = Column(String, index=True)
    year = Column(Integer)
▶️ Running FastAPI (if used)
If you're using FastAPI:

bash
Copy
Edit
uvicorn main:app --reload
📦 Dependencies
Listed in requirements.txt:

txt
Copy
Edit
fastapi
uvicorn
sqlalchemy
psycopg2-binary
pydantic
🧑‍💻 Author
Rashmeet Singh
B.Tech CSE | CGC Jhanjeri

