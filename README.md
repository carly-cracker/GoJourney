
GoJourney Adventures

Gojourney is a fullstack travel experience sharing platform where users can:
- Share their travel adventures
- Discover hidden gems from around the world
- Like posts and interact with the travel community
- Securely sign up and log in
- Admins can manage and moderate content

---

## Tech Stack

### Frontend
- React 19 + Vite + Tailwind CSS
- Axios, Formik + Yup, Lucide Icons
- JWT Decode for auth

### Backend
- Flask
- PostgreSQL
- SQLAlchemy + Flask-Migrate
- Flask-JWT-Extended
- Flask-CORS
- Marshmallow

---

##  Installation & Setup

### 1. Clone the repo

```bash
git clone https://github.com/carly-cracker/GoJourney.git
cd GoJourney
 Backend Setup (/GoJourney root directory)
2. Create .env in project root

nano .env
Paste this:

env
Copy
Edit
DATABASE_URL=postgresql://<username>:<password>@localhost:5432/<db_name>
JWT_SECRET_KEY=your_jwt_secret
SECRET_KEY=your_flask_secret
3. Load environment variables

# From the /GoJourney directory
set -a && source .env && set +a
Verify:


echo $DATABASE_URL
4. Set Flask app and environment

export FLASK_APP=server.app
export FLASK_ENV=development
###You must be inside /GoJourney when running this.

5. Install dependencies

pip install -r server/requirements.txt
pip install flask_cors  # if not already installed
6. Create DB in Postgres (psql CLI)

psql -U postgres
CREATE DATABASE <db_name>;
7. Run DB migrations

# Still inside /GoJourney
flask db init          # Only once
flask db migrate -m "Initial migration"
flask db upgrade

8. Run Flask server

flask run --port=5555

Should be live at: http://localhost:5555

Frontend Setup (/GoJourney/client)

cd client

npm install
npm run dev
App will be live at: http://localhost:5173

Project Structure

GoJourney/
├── client/               # React frontend
├── server/               # Flask backend
│   ├── app.py
│   ├── config.py
│   ├── models/
│   ├── controllers/
│   ├── requirements.txt
│   └── migrations/
├── .env
├── .gitignore
└── README.md
#Admin Commands (inside psql)
bash
Copy
Edit
psql -h localhost -U postgres -d <db_name>
>>>> \c <db_name>
>>>> \dt --->shows the data in the db after migration.
SELECT * FROM users;
UPDATE users SET is_admin = true WHERE username = '<user_created from the app during signup>';
![Screenshot from 2025-06-29 19-21-06](https://github.com/user-attachments/assets/08c7655b-1b21-4691-92d6-5888fdd3d25f)


Features
JWT Auth (sign up, login, logout)

Trip CRUD with like/unlike

Admin dashboard

Search trips

Flag & manage content
```

PHOTOS 
![Screenshot from 2025-06-29 19-33-23](https://github.com/user-attachments/assets/a5dee33f-e9d1-4c8d-8dab-4a17550c646d)
![Screenshot from 2025-06-29 19-17-20](https://github.com/user-attachments/assets/72852d86-86a2-4f6b-849d-74223bf6d671)
![Screenshot from 2025-06-29 19-34-21](https://github.com/user-attachments/assets/576e1296-8988-4e65-846f-af580285f6c6)
![Screenshot from 2025-06-29 19-25-32](https://github.com/user-attachments/assets/7d8e7249-0a7c-41db-82b4-0c146da609f9)
![Screenshot from 2025-06-29 19-25-41](https://github.com/user-attachments/assets/25b967a7-fe42-4997-99fa-9c8fa834d4da)
![Screenshot from 2025-06-29 19-35-39](https://github.com/user-attachments/assets/424f636b-cae7-4db2-9639-4e921aaa156e)
![Screenshot from 2025-06-29 19-36-15](https://github.com/user-attachments/assets/068e4624-311e-4f6d-8a83-b8e6af3476d8)
![Screenshot from 2025-06-29 19-24-45](https://github.com/user-attachments/assets/971f1a3e-714f-47a3-8f99-3062b5dce32e)










Cliff, Deborah, ***Maxwell*** & Carlos – built with love 💖







