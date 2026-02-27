# ⏱️ CESAE Digital – Attendance Management System

A web-based Attendance Management System developed with Laravel 12, designed to manage student attendance, time tracking, and absence validation within CESAE Digital training programs. The system provides role-based access control and automates several administrative processes related to attendance management.

---

## 🏗️ Architecture & Roles

The application is structured around three main user roles:

### 👨‍💼 Administrator
- Full management of courses, classes, modules, instructors, and students
- System configuration and data control

### 👨‍🏫 Instructor
- PIN generation for attendance check-in
- Schedule (cronogram) visualization
- Attendance management
- Absence justification validation

### 👨‍🎓 Student
- Attendance check-in via PIN (manual and automatic)
- Class history access
- Absence justification submission
- Schedule consultation

---

## 🚀 Tech Stack

- **Laravel 12** – PHP framework  
- **MySQL (MariaDB)** – Relational database  
- **Laravel Breeze** – Authentication scaffolding  
- **Blade** – Templating engine  
- **Tailwind CSS & Bootstrap** – UI styling  
- **JavaScript** – Interactive features  
- **FullCalendar** – Interactive scheduling  
- **ApexCharts** – Data visualization  
- **Spatie Simple Excel** – CSV/Excel import/export  
- **Laravel Queues** – Automated check-out processing  
- **Pest PHP** – Testing framework  
- **Git & GitHub** – Version control  

---

## 🎯 Key Features

✔ Role-based authentication system  
✔ Attendance registration via PIN  
✔ Automatic check-out system using Laravel Queues  
✔ Attendance history tracking  
✔ Absence submission and approval workflow  
✔ CSV/Excel data import/export  
✔ Seeder-based demo data  
✔ Interactive calendar and reporting dashboards  

---

<br>

## 🔐 Demo Credentials

After running:

```bash
php artisan db:seed
```

### Admin
- Email: admin@example.com
- Password: password123  

### Instructor
- Email: sara@example.com
- Password: password123  

### Student
- Email: carmem.zavattieri.298335670@msft.cesae.pt
- Password: password123  

<br>

## 🔧 Installation Guide

> **Important:** Make sure your local environment (e.g., XAMPP, Laragon, etc.) is running and MySQL is active.

### 1️⃣ Clone the repository

```bash
git clone https://github.com/CarmemZava/RelogioPonto.git
cd RelogioPonto
```

### 2️⃣ Install dependencies

```bash
composer install
npm install
```

### 3️⃣ Environment configuration

```bash
cp .env.example .env
php artisan key:generate
```

Update your .env file with your database credentials before continuing.

### 4️⃣ Database setup

```bash
php artisan migrate
php artisan db:seed
```

### 5️⃣ Import schedule data (Required)
Manually import the following file into your database:

```bash
Data/data_base_cronograma(Folha1).csv
```
Use MySQL Workbench or any similar database management tool.

### 6️⃣ Refresh autoload files

```bash
composer dump-autoload
```

### 7️⃣ Storage configuration

```bash
php artisan storage:link
```

### 8️⃣ Install Excel library (if not already installed)

```bash
composer require spatie/simple-excel
```

### 9️⃣ (Optional) Generate additional demo attendance records

```bash
php artisan db:seed --class=PresencaSeeder
```

### 🔟 (Optional) Run queue worker - Required for automatic check-out feature

```bash
php artisan queue:work
```
