# RTU Tindahan

An E-Commerce Web Platform for Food and Merchandise Trading using LLM, built for the students and personnel of Rizal Technological University, Pasig Campus.

**Group:** Big Black Lorenz (BBL)
**Members:** Arellano, Lian Andrew R. (Project Leader) · Aliermo, Neil Ryan · Mangalino, Lorenz Ivan · Saldivar, Mark John

---

## Tech Stack

- **Backend:** Laravel 12 (PHP 8.2+)
- **Database:** MySQL
- **Frontend:** Laravel Breeze (Blade templates)
- **Local environment:** XAMPP (Apache + MySQL)
- **Version control:** Git + GitHub

---

## Requirements Before You Start

Make sure you have these installed:

1. **XAMPP** — [download here](https://www.apachefriends.org/) (gives you PHP + MySQL + Apache)
2. **Composer** — [download here](https://getcomposer.org/) (PHP package manager)
3. **Node.js (LTS version)** — [download here](https://nodejs.org/) (needed for frontend asset compilation)
4. **Git** — [download here](https://git-scm.com/)

---

## Setup Instructions (for a fresh clone)

### 1. Clone the repository
```
git clone https://github.com/Najimi0-0/rtu_tindahan.git
cd rtu_tindahan
```

### 2. Install PHP dependencies
```
composer install
```
> If you get a "zip extension missing" error, open your `php.ini` (in XAMPP's `php` folder) and remove the `;` in front of `extension=zip`, then retry.

### 3. Install JavaScript dependencies
```
npm install
```
> If PowerShell blocks this with a script execution error, run this once in an **Administrator** PowerShell window:
> `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`

### 4. Set up your environment file
```
copy .env.example .env
```
(On Mac/Linux, use `cp .env.example .env` instead)

### 5. Generate your app key
```
php artisan key:generate
```

### 6. Create your local database
- Start Apache and MySQL in XAMPP Control Panel
- Open `http://localhost/phpmyadmin`
- Create a new database named exactly: `rtu_tindahan`

### 7. Point Laravel to your database
Open `.env` and set:
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=rtu_tindahan
DB_USERNAME=root
DB_PASSWORD=
```

### 8. Run migrations
```
php artisan migrate
```

### 9. Build frontend assets
```
npm run build
```

### 10. Start the dev server
```
php artisan serve
```
Visit `http://127.0.0.1:8000` — you should see the Laravel welcome page with Log in / Register links.

---

## Daily Git Workflow

**Before you start working:**
```
git pull
```

**After you finish working:**
```
git add .
git commit -m "Short description of what you changed"
git push
```

If `git pull` shows a merge conflict, don't panic — flag it in the group chat and we'll resolve it together.

---

## Project Status

See `DEVLOG.md` for a running log of what's been built and why.

**Current phase:** Sprint 1 — Core platform (database, account registration with campus verification, login, role management)

---

## Troubleshooting

| Problem | Likely fix |
|---|---|
| `Could not open input file: artisan` | You're in the wrong folder — `cd` into the project root |
| `SQLSTATE[HY000] [2002] No connection could be made` | MySQL isn't running — start it in XAMPP Control Panel |
| MySQL won't start / InnoDB corruption errors | Stop MySQL, rename `mysql/data` to `mysql/data_old`, copy `mysql/backup` and rename it to `data`, restart MySQL, recreate the database, re-run migrations |
| `npm install` blocked by PowerShell | Run `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` in an Admin PowerShell window |
