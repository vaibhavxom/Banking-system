# Online Banking System

This is an Online Banking Concept created using Django Web Framework.


## Features

* Create Bank Account.
* Deposit & Withdraw Money
* Bank Account Type Support (e.g. Current Account, Savings Account)
* Interest calculation depending on the Bank Account type
* Transaction report with a date range filter 
* See balance after every transaction in the Transaction Report
* Calculate Monthly Interest Using Celery Scheduled tasks
* More efficient and accurate interest calculation and balance update
* Ability to add Minimum and Maximum Transaction amount restriction
* Modern UI with Tailwind CSS


## Prerequisites

Make sure you have the following installed:

- Python (>= 3.6)
- pip (Python package installer)
- Django (>= 3.0)
- SQLite (or another database of your choice)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/vaibhavxom/Banking-system.git
    cd Banking-system
    ```
#
2. Create a virtual environment (optional but recommended):
    ```bash
    python -m venv venv
    ```
#
3. Activate the virtual environment:
    - On Windows:
      ```bash
      venv\Scripts\activate
      ```
    - On macOS/Linux:
      ```bash
      source venv/bin/activate
      ```
#
4. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
#
5. Apply migrations:
    ```bash
    python manage.py migrate
    ```
#
6. Create a superuser to access the Django admin panel:
    ```bash
    python manage.py createsuperuser
    ```
#
7. Create admin css file:
    ```bash
    python manage.py collectstatic
    ```
#
8. Run the development server:
    ```bash
    python manage.py runserver
    ```
#


Now, you can access the application at `http://127.0.0.1:8000/`.

## Usage

- **User Registration & Login**: Navigate to the registration or login page to create an account or sign in.
- **Create Account Types **: Create Account Types Such As Current,Savings, Set Intrest Rate & Period Of Intrest.
## Admin Panel

To manage products and view orders, log in to the Django admin panel at:
**`http://127.0.0.1:8000/admin`**
#

## Images:
![alt text](https://i.imgur.com/aWzj44Y.png)
#

## Deploying to PythonAnywhere

### Step 1: Create an Account on PythonAnywhere
- Go to [PythonAnywhere](https://www.pythonanywhere.com/) and sign up for a free or paid account.
- Once signed up, log in to your dashboard.

### Step 2: Set Up a New Web App on PythonAnywhere
1. In the PythonAnywhere dashboard, click on the **"Web"** tab.
2. Click on **"Add a new web app"**.
3. Choose the option **"Manual configuration"**.
4. Select **"Python 3.x"** for the Python version.
5. Select the option **"Django"** for the framework.
6. Click **"Next"** and PythonAnywhere will set up the necessary files for you.

### Step 3: Clone Your Django Project to PythonAnywhere
1. In the **"Files"** tab on PythonAnywhere, create a new directory to hold your Django project.
2. Open a **Bash console** from the dashboard (or the **"Consoles"** tab).
3. In the bash console, clone your repository:
    ```bash
    git clone https://github.com/vaibhavxom/Banking-system.git
    ```
4. Navigate to the project directory:
    ```bash
    cd Banking-system
    ```

### Step 4: Set Up a Virtual Environment
1. Create a virtual environment in your project folder:
    ```bash
    python3 -m venv myenv
    ```
2. Activate the virtual environment:
    ```bash
    source myenv/bin/activate
    ```
3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

### Step 5: Configure Database
1. In the bash console, run Django migrations to set up the database:
    ```bash
    python manage.py migrate
    ```

### Step 6: Configure Static and Media Files
1. Ensure that the static files and media files are configured correctly:
    - In `settings.py`, set up static and media directories:
    ```python
    STATIC_ROOT = os.path.join(BASE_DIR, 'static/')
    MEDIA_ROOT = os.path.join(BASE_DIR, 'media/')
    STATIC_URL = '/static/'
    MEDIA_URL = '/media/'
    ```
#2. Run the `collectstatic` command to gather static files:
    ```bash
    python manage.py collectstatic
    ```

### Step 7: Update PythonAnywhere Web App Settings
1. Go to the **"Web"** tab on PythonAnywhere and click on the web app you created.
2. Under **"Source code"**, set the path to your project folder (e.g., `/home/yourusername/Banking-system`).
3. Under **"Virtualenv"**, set the path to your virtual environment (e.g., `/home/yourusername/Banking-system/myenv`).
4. Set the **WSGI configuration file** to point to your Django app:
    - Open the **WSGI configuration file** by clicking on **"WSGI configuration file"** link.
    - Add the following code:
    ```python
    import os
    import sys
    path = '/home/yourusername/Banking-system'
    if path not in sys.path:
        sys.path.insert(0, path)

    os.environ['DJANGO_SETTINGS_MODULE'] = 'banking-system.settings'

    from django.core.wsgi import get_wsgi_application
    application = get_wsgi_application()
    ```
5. Set up static files handling:
    - In the **"Static files"** section, configure the static and media file paths as follows:
    ```text
    URL: /static/
    Directory: /home/yourusername/Banking-system/static/
    ```
    - Similarly for media files:
    ```text
    URL: /media/
    Directory: /home/yourusername/Banking-system/media/
    ```

### Step 8: Create a Superuser (Optional)
1. You can create a superuser to access the admin panel:
    ```bash
    python manage.py createsuperuser
    ```

### Step 9: Visit Your Site
1. Once everything is set up, go to your **PythonAnywhere web app URL** (e.g., `https://yourusername.pythonanywhere.com/`).
2. You should now see your Django E-Commerce application live!
