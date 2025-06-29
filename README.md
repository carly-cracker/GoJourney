
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
bash
Copy
Edit
nano .env
Paste this:

env
Copy
Edit
DATABASE_URL=postgresql://<username>:<password>@localhost:5432/<db_name>
JWT_SECRET_KEY=your_jwt_secret
SECRET_KEY=your_flask_secret
3. Load environment variables
bash
Copy
Edit
# From the /GoJourney directory
set -a && source .env && set +a
Verify:

bash
Copy
Edit
echo $DATABASE_URL
4. Set Flask app and environment
bash
Copy
Edit
export FLASK_APP=server.app
export FLASK_ENV=development
###You must be inside /GoJourney when running this.

5. Install dependencies
bash
Copy
Edit
pip install -r server/requirements.txt
pip install flask_cors  # if not already installed
6. Create DB in Postgres (psql CLI)
bash
Copy
Edit
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

Features
JWT Auth (sign up, login, logout)

Trip CRUD with like/unlike

Admin dashboard

Search trips

Flag & manage content




Cliff, Deborah, ***Maxwell*** & Carlos – built with love 💖







