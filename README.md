<div align="center">
  <h1>🚗 Django CarShop Platform</h1>
  <p>A fully-featured e-commerce platform for a car dealership, built with Python and Django. Features advanced filtering, shopping cart, PDF invoicing, custom middleware, and automated background tasks.</p>
</div>

---

## 📌 Short Description
This repository contains the backend and core business logic for an online auto dealership platform. Built with the **Django** framework, the application handles complex relationships between car brands, categories, and inventory. It goes beyond a simple web app by implementing enterprise-level features such as background job scheduling, custom HTTP middleware logging, dynamic PDF generation for order invoices, and a highly customized Admin dashboard.

<img width="1894" height="866" alt="image" src="https://github.com/user-attachments/assets/e0b0a24b-2f7d-4be1-8b87-0ff1ccfa24ba" />

## 💻 Tech Stack & Tools
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)

* **Backend Framework:** Django (Python)
* **Document Generation:** `reportlab` (PDF Invoices)
* **Background Tasks/Cron:** Custom tasks logic (`tasks.py`) for automated mailing and DB cleanup.
* **Security & Auth:** Built-in Django Auth, Email Validation, CSRF protections.

## ✨ Key Features & Technical Highlights

### 🛒 E-Commerce & Inventory Management
* **Advanced Filtering:** Custom form validation (`forms.py`) preventing logic errors (e.g., negative mileage, future manufacturing years) and filtering by brand, category, price bounds, and fuel type.
* **Shopping Cart & Checkout:** Full cart logic ending with order registration (`Comanda` and `ItemComanda`) and automated email confirmation.
* **Dynamic PDF Invoices:** Uses `reportlab` to automatically generate and attach detailed PDF invoices to order confirmation emails.

### ⚙️ Advanced Django Engineering
* **Custom Middleware (`middleware.py`):** Intercepts incoming HTTP requests to log traffic data (Path, Method, IP, Timestamp) for internal analytics and security monitoring.
* **Automated Background Tasks (`tasks.py`):**
  * Auto-deletes unconfirmed user accounts to save DB space.
  * Generates and sends weekly activity reports to administrators.
  * Dispatches automated newsletters highlighting newly added cars.
* **SEO Optimization:** Dynamic and Static Sitemaps (`sitemaps.py`) configured for web crawlers.
* **Customized Admin Panel (`admin.py`):** Overridden ModelAdmins with custom `list_display`, `list_filter`, and `inlines` to allow seamless management of cars, locations, and user orders directly from the dashboard.

<img width="1903" height="869" alt="image" src="https://github.com/user-attachments/assets/d293eea5-57cd-4cd2-983e-fc2c8ad544f1" />


## 🗄️ Core Database Models
* `CustomUser`, `IncercareLogare` (Authentication & Security)
* `Masina`, `Marca`, `CategorieMasina`, `Accesoriu`, `Serviciu` (Product Catalog)
* `Comanda`, `ItemComanda` (Sales & Invoicing)

## 🚀 Setup & Execution

To run this project locally, ensure you have Python installed.

**1. Clone the repository:**
```bash
git clone https://github.com/MihneaG17/Django-CarShop-Platform.git
cd Django-CarShop-Platform
```

**2. Create a virtual environment & install dependencies:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

**3. Apply database migrations:**
```bash
python manage.py makemigrations
python manage.py migrate
```
**4. Create a superuser (for Admin panel access):**
```bash
python manage.py createsuperuser
```
**5. Run the development server:**
```bash
python manage.py runserver
```
(Navigate to http://127.0.0.1:8000/ to view the site, or http://127.0.0.1:8000/admin/ for the dashboard).
