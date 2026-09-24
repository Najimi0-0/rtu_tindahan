# Development Log — RTU Tindahan

A running record of what was built, why, and any issues encountered along the way. Add a new entry after each work session. This log is useful later for writing the methodology and implementation sections of the manuscript.

**Format for each entry:**
```
## [Date] — [Name]
**What I did:**
-

**Why / decisions made:**
-

**Issues hit & how I solved them:**
-
```

---

## September 22, 2026 — Lian Andrew Arellano

**What I did:**
- Installed XAMPP (PHP 8.2, MySQL/MariaDB, Apache)
- Created Laravel 12 project (`RTU_Tindahan`) via Composer
- Switched database connection from Laravel's default SQLite to MySQL
- Installed Laravel Breeze for authentication scaffolding (registration, login, password reset)
- Set up Git version control and pushed the project to GitHub (private repo)

**Why / decisions made:**
- Chose Laravel + MySQL per the proposal's tech stack, over Django + PostgreSQL, mainly for built-in auth scaffolding (Breeze) and cheaper/simpler shared hosting compatibility for deployment later
- Chose Laravel 12 instead of the newest v13, since v13 requires PHP 8.3+ and our XAMPP install has 8.2

**Issues hit & how I solved them:**
- Composer couldn't download packages: PHP's `zip` extension was disabled in `php.ini` — fixed by uncommenting `extension=zip`
- MySQL repeatedly crashed with InnoDB corruption errors after a PC restart — traced to a Windows Fast Startup / antivirus interference issue; resolved by restoring `mysql/data` from XAMPP's clean `mysql/backup` folder, adding a Windows Defender exclusion for the XAMPP folder, and disabling Fast Startup
- `npm install` blocked by PowerShell's script execution policy — resolved by running `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` in an Administrator terminal

---

## [Next entry — add below as work continues]
