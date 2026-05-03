Module5_FacultyPagesGroupProject - SPC - COP 4504 - DEV TEAM 2 - 2026
This is a Dev Team 2 Group project that was based on a prior forked one.
This project adds a Python/Flask backend with MySQL database support for dynamic faculty data management.
Contributors: Matthew W., Dannielle M., Jacob G., and LeEric R.

## Project Structure
```
/
├── app.py                  - Flask application and API routes
├── requirements.txt        - Python dependencies
├── templates/
│   ├── index.html          - Faculty profile page (dynamic, API-driven)
│   └── edit.html           - Faculty edit form (loads/saves via API)
├── static/
│   ├── style.css           - Shared styles
│   ├── spc.css             - SPC brand styles
│   └── images/             - Profile pictures and image assets
├── images/                 - Legacy image assets (root-level)
└── Faculty Info Pages Wireframes.pdf - Design mockups
```

## Project Purpose
This application demonstrates:
- Full-stack Flask + MySQL architecture
- Dynamic faculty data loaded from a MySQL database
- REST API (`/api/faculty`) for reading and updating faculty information
- Interactive edit form that persists changes to the database
- Separation of frontend templates and backend API concerns

## How to Run Locally

### Prerequisites
- Python 3.8+
- MySQL database

### Setup
1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file with your database credentials:
   ```
   MYSQL_HOST=localhost
   MYSQL_USER=root
   MYSQL_PASSWORD=yourpassword
   MYSQL_DATABASE=faculty_portal
   ```
4. Run the application:
   ```bash
   python app.py
   ```
5. Open `http://localhost:5000` in your browser

## Deployment (Railway)
The app auto-detects Python via Railpack. Connect a MySQL database service and Railway will automatically inject the following environment variables:
- `MYSQL_HOST`
- `MYSQL_USER`
- `MYSQL_PASSWORD`
- `MYSQL_DATABASE`

The database table is created automatically on first run.

## API Endpoints
| Method | Path          | Description                        |
|--------|---------------|------------------------------------|
| GET    | `/`           | Faculty profile page               |
| GET    | `/edit`       | Faculty edit page                  |
| GET    | `/api/faculty`| Fetch current faculty data (JSON)  |
| POST   | `/api/faculty`| Save updated faculty data (JSON)   |

## Notes
- If no faculty record exists in the database, the API returns default placeholder data
- Static assets are served from the `static/` folder
- Place profile images in `static/images/` for Flask to serve them correctly

## Setup Instructions

### Prerequisites
- Python 3.8+
- MySQL 8.0

### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Environment Variables
Create a `.env` file in the project root with the following variables:
```
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=yourpassword
MYSQL_DATABASE=faculty_portal
```

| Variable         | Description                        |
|------------------|------------------------------------|
| `MYSQL_HOST`     | Hostname of your MySQL server      |
| `MYSQL_USER`     | MySQL username                     |
| `MYSQL_PASSWORD` | MySQL password                     |
| `MYSQL_DATABASE` | Name of the database to connect to |

### Running Locally
Start the Flask development server:
```bash
python app.py
```

Once running, open your browser and navigate to:
```
http://localhost:5000
```

---

## Technologies Used

| Technology                    | Version  | Purpose                                      |
|-------------------------------|----------|----------------------------------------------|
| Python                        | 3.8+     | Backend runtime                              |
| Flask                         | 2.3.3    | Web framework and API routing                |
| Flask-CORS                    | 4.0.0    | Cross-origin resource sharing support        |
| MySQL                         | 8.0      | Relational database for faculty data storage |
| mysql-connector-python        | 8.0.33   | Python driver for MySQL connectivity         |
| HTML5 / CSS3                  | —        | Frontend markup and styling                  |
| JavaScript (Fetch API)        | —        | Async API calls from the browser             |
| Bootstrap                     | 5.3.8    | Responsive UI components and layout          |

---

## How to Test CRUD Functionality

### CREATE — Add Faculty Data
1. Navigate to `http://localhost:5000/edit`
2. Fill out all fields in the faculty edit form
3. Click **"Save Changes"**
4. Return to the home page (`http://localhost:5000`) and verify the new data appears

**API equivalent:**
```http
POST /api/faculty
Content-Type: application/json

{
  "name": "Dr. Jane Smith",
  "title": "Professor",
  "department": "Computer Science",
  ...
}
```

### READ — View Faculty Data
1. Visit the home page at `http://localhost:5000`
2. Faculty data is dynamically loaded from the MySQL database via the API
3. If no record exists yet, default placeholder data is displayed

**API equivalent:**
```http
GET /api/faculty
```
Returns the current faculty record as a JSON object.

### UPDATE — Modify Existing Faculty Data
1. Navigate to `http://localhost:5000/edit`
2. The form will pre-populate with the current faculty data from the database
3. Modify any fields as needed
4. Click **"Save Changes"**
5. Return to the home page (`http://localhost:5000`) and verify the updated data appears

**API equivalent:**
```http
POST /api/faculty
Content-Type: application/json

{
  "name": "Dr. Jane Smith",
  "title": "Associate Professor",
  ...
}
```

### DELETE — Remove Faculty Data
> **Note:** Delete functionality is not yet implemented. This is planned as an optional future enhancement. A `DELETE /api/faculty/<id>` endpoint can be added in a future iteration to support record removal.
