# Project Title

A brief description of what this project does and who it's for

# WordPress Deployment with Nginx and GitHub Actions

This repository contains the setup for deploying a WordPress website using the Nginx web server, LEMP stack, and GitHub Actions for continuous deployment.

## Table of Contents

- [Introduction](#introduction)
- [Setup](#setup)
  - [Server Provisioning](#server-provisioning)
  - [GitHub Actions Workflow](#github-actions-workflow)
- [Usage](#usage)
- [Optimizations](#optimizations)
- [API Reference](#api-reference)
- [License](#license)

## Introduction

This project demonstrates the automated deployment of a WordPress website using Nginx, the LEMP stack (Linux, Nginx, MySQL, PHP), and GitHub Actions for continuous deployment.

## Setup

### Server Provisioning

- Provisioned a Virtual Private Server (VPS) with a secure Linux distribution (e.g., Ubuntu 22.04).
- Configured Nginx as the web server, MySQL/MariaDB as the database, and PHP for processing dynamic content.

### GitHub Actions Workflow

- Created a GitHub Actions workflow (`main.yml`) for automated deployment.
- The workflow triggers on push events to the `main` branch.
- The workflow performs the following steps:
  - Checks out the repository.
  - Installs necessary dependencies and services (mariadb-server, nginx, php, etc.).
  - Downloads and extracts the latest WordPress version.
  - Configures the MySQL/MariaDB database and user.
  - Copies and configures the `wp-config.php` file.
  - Restarts Nginx for the changes to take effect.

## Usage

1. Make changes to your WordPress website locally.
2. Commit and push changes to the `main` branch.
3. GitHub Actions workflow will automatically deploy changes to the VPS.
4. Access your WordPress website via the VPS IP address.

## API Reference

Configure your Nginx server block to handle PHP requests and include `index.php` in the list of index files:


# Add index.php to the list if you are using PHP
index index.php index.html index.htm index nginx-debian.html;


nginx
location ~ \.php$ {
    include snippets/fastcgi-php.conf;

    # With php-fpm (or other unix sockets):
    fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
    # With php-cgi (or other tcp sockets):
    # fastcgi_pass 127.0.0.1:9000;
}


## Screenshots

<p align="center">
  <img width="960" alt="wp-2" src="!![Screenshot 2023-08-21 at 19-06-07 EC2 Instance Connect](https://github.com/Dhruvpatel827740/wordpresstask/assets/125884129/693da020-f728-4d87-907c-a3d0cd3e6616)">
</p>
<br>


<p align="center">
  <img width="960" alt="wp-2" src="![Screenshot 2023-08-21 at 19-04-50 Dashboard ‹ Brainstorm — WordPress](https://github.com/Dhruvpatel827740/wordpresstask/assets/125884129/507e2dfe-8a35-433b-b240-158d7e82a47d)">
</p>
<br>


<p align="center">
  <img width="960" alt="wp-2" src="![Screenshot 2023-08-21 at 19-06-07 EC2 Instance Connect](https://github.com/Dhruvpatel827740/wordpresstask/assets/125884129/c8a59f39-db65-4777-8a78-342357219c09)">
</p>
<br>



