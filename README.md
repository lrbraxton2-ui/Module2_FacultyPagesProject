Module6_FacultyPagesGroupProject - SPC- COP 4504 - DEV TEAM 2 - 2026 
This is a Dev Team 2 Group project that was based on a prior forked one. 
This Project expands the original design into a Flask-based web application with MySQL database integration.
Contributors: Matthew W., Dannielle M., Jacob G., and LeEric R.

## Files Included
- `app.py` - Flask backend application with routing and CRUD functionality  
- `facultydatabase_schema.sql` - SQL script to create database and tables  
- `templates/index.html` - faculty home/profile page  
- `templates/edit.html` - faculty edit page  
- `static/style.css` - main layout and styling  
- `static/spc.css` - SPC branding and color styling  
- `static/images/` - contains profile images and SPC logo assets  

## Project Purpose
This project demonstrates:
- page structure and layout using HTML and CSS  
- navigation between pages  
- placement of profile details and content sections  
- a faculty edit form connected to a backend  
- Flask integration for server-side logic  
- MySQL database connection and relational design  
- CRUD operations (Create, Read, Update, Delete)  
- handling many-to-many relationships (faculty and courses)  
- basic data formatting (phone number formatting)  

## How to Use
1. Download or clone the project folder  
2. Open the project in VS Code  
3. Run the SQL script (`facultydatabase_schema.sql`) in MySQL Workbench  
4. Create a `.env` file with your database credentials  
5. Run the Flask app:

```bash
python app.py

