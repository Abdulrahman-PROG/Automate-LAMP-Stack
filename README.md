# Automate LAMP Stack Deployment

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Features](#features)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction
This project automates the deployment of a **LAMP Stack** (Linux, Apache, MySQL, PHP) using **Ansible**. It is designed to streamline the process of setting up a web server environment, making it suitable for web developers and system administrators.

**Repository URL:** [GitHub Repository](https://github.com/Abdulrahman-PROG/Automate-LAMP-Stack)

---

## Project Structure
The project is organized into the following structure:
```
lamp-stack/
├── ansible.cfg               # Ansible configuration file
├── inventory/
│   └── dev                   # Inventory file for development servers
├── playbook.yml              # Main playbook to deploy LAMP stack
├── roles/
│   ├── apache/
│   │   ├── tasks/            # Apache-related tasks
│   │   ├── handlers/         # Handlers for Apache tasks
│   │   └── files/            # Apache-specific files (e.g., index.php)
│   ├── mysql/
│   │   └── tasks/            # MySQL-related tasks
│   └── php/
│       └── tasks/            # PHP-related tasks
└── README.md                 # Documentation (this file)
```

---

## Prerequisites
Before running this project, ensure the following requirements are met:
- **Operating System:** Fedora (or any Linux-based OS).
- **Ansible Installed:** Version 2.9 or higher.
  - Install Ansible on Fedora:
    ```bash
    sudo dnf install ansible -y
    ```
- **Python Installed:** Version 3.6 or higher.
- SSH access to the target servers (or run locally on `localhost`).

---

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/Abdulrahman-PROG/Automate-LAMP-Stack.git
   cd lamp-stack
   ```

2. Ensure the `inventory/dev` file is configured correctly:
   - Example:
     ```ini
     [webservers]
     localhost ansible_connection=local
     ```

3. Verify the file structure and ensure all required files (e.g., `index.php`) are in place.

---

## Usage
1. Run the Ansible Playbook:
   ```bash
   ansible-playbook -i inventory/dev playbook.yml --ask-become-pass
   ```

2. After execution, verify the following:
   - Apache is installed and running.
   - PHP is functional (visit `http://localhost/index.php` to confirm).
   - MySQL (MariaDB) is installed and secured.

---

## Testing
To verify the deployment:
1. **Apache Test:**
   - Open a browser and navigate to `http://localhost/index.php`.
   - You should see the PHP info page.

2. **MySQL Test:**
   - Log in to MariaDB:
     ```bash
     mysql -u root -p
     ```
   - Check if the database is configured correctly.

---

## Features
- Automated deployment of LAMP stack.
- Modular design using Ansible roles for Apache, MySQL, and PHP.
- Supports both local (localhost) and remote server configurations.
- Easy to extend and customize.

---

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes and commit them:
   ```bash
   git commit -m "Add your feature description"
   ```
4. Push your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Create a pull request.

---
![image](https://github.com/user-attachments/assets/7e8d0aaa-bc82-408d-9b05-90762784ad70)


## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
