# Pet Management Flask Application

## Overview
This is a Flask-based web application designed to manage pet information, users, and cart functionalities. The application is built using Flask, SQLAlchemy, and MySQL. It includes a modular architecture with blueprints for easier management of the admin, pet, user, and cart routes.

## Features
- Pet Management: View and manage pet details.
- User Management: User login, session handling, and role-based access control.
- Admin Panel: Admin functionalities like managing users and pets.
- Cart Functionality: Add and manage items in a cart.
- Modular Design: Uses Flask blueprints for scalability.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- MySQL database
- pip (Python package manager)

### Steps
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd FlaskApp
   ```

2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Configure the MySQL database:
   Update the `SQLALCHEMY_DATABASE_URI` in `app.py`:
   ```python
   app.config["SQLALCHEMY_DATABASE_URI"] = "mysql://<username>:<password>@<host>:<port>/<databasename>"
   ```

5. Set a secret key for the Flask app:
   ```python
   app.config["SECRET_KEY"] = "<anystring>"
   ```

6. Initialize the database:
   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```

7. Run the application:
   ```bash
   python app.py
   ```

---

## Project Structure
```
FlaskApp/
|-- app.py              # Main application file
|-- models.py           # Database models for Pet and User
|-- blueprints/         # Folder for blueprint modules
|   |-- admin_bp.py     # Admin routes
|   |-- pet_bp.py       # Pet routes
|   |-- user_bp.py      # User routes
|   |-- cart_bp.py      # Cart routes
|-- static/
|   |-- media/          # Folder for uploaded media files
|-- templates/          # HTML templates
|-- requirements.txt    # Python dependencies
```

---

## Configuration Details
1. **MySQL Database URI**
   ```python
   app.config["SQLALCHEMY_DATABASE_URI"] = "mysql://<username>:<password>@<host>:<port>/<databasename>"
   ```
   Replace `<username>`, `<password>`, `<host>`, `<port>`, and `<databasename>` with your MySQL credentials.

2. **Secret Key**
   ```python
   app.config["SECRET_KEY"] = "<anystring>"
   ```
   Replace `<anystring>` with a secure random string.

3. **Upload Folder**
   Uploaded media files are saved in:
   ```python
   app.config['UPLOAD_FOLDER'] = os.path.join(os.getcwd(), 'static', 'media')
   ```

4. **Allowed File Extensions**
   ```python
   app.config['ALLOWED_EXTENSIONS'] = {'png', 'jpg', 'jpeg', 'gif'}
   ```

---

## Context Processors
The app uses context processors to provide global variables:
- `is_admin`: Checks if the logged-in user is an admin.
- `is_loggedin`: Checks if a user is logged in.
- `admin_user_name`: Retrieves the name of the logged-in admin user.

---

## Dependencies
- Flask==3.0.0
- Flask-SQLAlchemy==3.1.1
- mysqlclient==2.2.0
- bcrypt==4.1.1
- blinker==1.7.0
- Jinja2==3.1.2
- SQLAlchemy==2.0.23
- Werkzeug==3.0.1

Install all dependencies with:
```bash
pip install -r requirements.txt
```

---

## Usage
1. Navigate to the application’s homepage by visiting `http://127.0.0.1:5000`.
2. Use the admin panel for pet and user management.
3. Explore cart functionalities and browse available pets.

---

## License
This project is licensed under the MIT License.

---

## Contributors
- [https://github.com/khairulanam23] - Developer
