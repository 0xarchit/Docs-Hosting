---
label: Secure FTP Explorer
icon: file-directory
description: "Modern, secure, and responsive web-based FTP client built with PHP featuring AES-256 encryption and multi-server management."
order: 83
tags: [PHP, MySQL, Tailwind CSS, Security, FTP]
---

# :icon-file-directory: Secure FTP Explorer

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/ftp-explorer?style=flat-square)    
![Stars](https://img.shields.io/github/stars/0xarchit/ftp-explorer?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/ftp-explorer?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/ftp-explorer?style=flat-square) [![Website](https://img.shields.io/website?url=https://0xarchit.rf.gd&style=flat-square)](https://0xarchit.rf.gd){target="_blank"}

**:icon-mark-github: GitHub:** [https://github.com/0xarchit/ftp-explorer](https://github.com/0xarchit/ftp-explorer){target="_blank"}  
**:icon-globe: Live Demo:** [https://0xarchit.rf.gd](https://0xarchit.rf.gd){target="_blank"}

> [!TIP]
> :icon-rocket: **Quick Start**: Clone the repository, configure your database, and start managing files securely in minutes.

## :icon-star: Features {#features}

### :icon-lock: Enterprise-Grade Security {#security}

- :icon-lock: **AES-256-CBC Encryption**: All FTP passwords are encrypted in the database using industry-standard encryption.
- :icon-shield: **Secure Authentication**: Bcrypt password hashing and hardened session management.
- :icon-alert: **CSRF Protection**: Comprehensive protection against Cross-Site Request Forgery attacks.
- :icon-code: **SQL Injection Prevention**: Full use of PDO prepared statements for all database interactions.
- :icon-check: **Security Headers**: Implemented HSTS, X-Frame-Options, X-XSS-Protection, and more.

### :icon-rocket: Multi-Server Management {#server-management}

- :icon-server: **Multiple Accounts**: Add, edit, and switch between multiple FTP accounts seamlessly.
- :icon-zap: **Instant Switching**: Connect to different servers without re-login.

### :icon-file-directory: File Management {#file-management}

- :icon-upload: **Multi-File Upload**: Upload to one or **all** configured servers simultaneously.
- :icon-trash: **Bulk Actions**: Delete multiple files at once with a single click.
- :icon-pencil: **File Operations**: Rename, Delete, Download, and Preview files (Images, Code, Text).
- :icon-link: **Public Links**: Generate direct public links for files (if configured).

### :icon-paintbrush: Modern UI {#ui}

- :icon-paintbrush: **Tailwind CSS**: Built with a modern utility-first CSS framework.
- :icon-device-mobile: **Responsive Design**: Fully optimized for both mobile and desktop devices.
- :icon-graph: **Storage Visualization**: Real-time storage usage visualization.

## :icon-tools: Installation & Setup {#installation}

### Prerequisites {#prerequisites}

- **PHP**: 7.4 or higher
- **Database**: MySQL / MariaDB
- **Web Server**: Apache / Nginx
- **Extensions**: `openssl` PHP extension

### 1. Clone & Upload
Clone the repository or download the source code. Upload all files to your web server's public directory (e.g., `public_html` or `htdocs`).

```bash
git clone https://github.com/0xarchit/ftp-explorer.git
```

### 2. Database Setup
1.  Create a new MySQL database.
2.  Import the `schema.sql` file located in the root directory.
    *   This will create the necessary `auth` and `ftp` tables.

### 3. Configuration
1.  Open `config/config.php`.
2.  Update the database credentials:
    ```php
    define('DB_HOST', 'your_db_host');
    define('DB_USER', 'your_db_user');
    define('DB_PASS', 'your_db_password');
    define('DB_NAME', 'your_db_name');
    ```
3.  **Important**: Change the `ENCRYPTION_KEY` to a random 32-character string for production security.

### 4. Default Login
Register a new account on the login screen. The first user registered can start adding FTP servers immediately.

## :icon-cloud: Deploying on InfinityFree {#deploying}

This project is optimized for shared hosting environments like InfinityFree.

1.  **Upload Files**: Use the InfinityFree File Manager or an FTP client (like FileZilla) to upload the project files to the `htdocs` folder.
2.  **Create Database**: Go to the Control Panel -> MySQL Databases. Create a new database and note the Hostname, Username, and Password.
3.  **Import SQL**: Open phpMyAdmin (via Control Panel), select your database, and import `schema.sql`.
4.  **Update Config**: Edit `config/config.php` via the File Manager with the credentials from Step 2.

> [!WARNING]
> :icon-shield-lock: **Security Note**: This application uses **AES-256-CBC** to encrypt FTP passwords. However, the decryption key is stored in `config/config.php`. Ensure this file is protected and not accessible via the web browser.
