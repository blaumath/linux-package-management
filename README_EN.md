# 📦 Linux Package Management Guide

This repository contains a practical guide for managing packages on Linux distributions that use **APT (Debian/Ubuntu)**, **DNF (Fedora)**, and **Pacman (Arch Linux)**.

---

## 📌 Comparative Command Table

Here is a quick summary of the most common package management commands:

| 🛠️ Action            | 🐧 APT (Debian/Ubuntu) | 🔵 DNF (Fedora)  | 🔴 Pacman (Arch)  |
|----------------------|------------------------|------------------|------------------|
| 🔍 Search packages   | `apt search`           | `dnf search`     | `pacman -Ss`     |
| 📥 Install package   | `apt install`          | `dnf install`    | `pacman -S`      |
| ❌ Remove package    | `apt remove`           | `dnf remove`     | `pacman -R`      |
| 🔄 Upgrade system    | `apt upgrade`          | `dnf upgrade`    | `pacman -Syu`    |
| 🧹 Clean cache       | `apt clean`            | `dnf clean all`  | `pacman -Scc`    |

💡 *If you prefer to see the commands in detail, check out the sections below!*

---

## 🔹 Package Management

### 🔍 Search Packages
```sh
apt search package  # Debian/Ubuntu
dnf search package  # Fedora
pacman -Ss package  # Arch Linux
```

### 📥 Install Packages
```sh
apt install package  # Debian/Ubuntu
dnf install package  # Fedora
pacman -S package    # Arch Linux
```

### ❌ Remove Packages
```sh
apt remove package  # Debian/Ubuntu
dnf remove package  # Fedora
pacman -R package   # Arch Linux
```

### ℹ️ Show Package Information
```sh
apt show package       # Debian/Ubuntu
dnf info package       # Fedora
pacman -Qi package     # If installed (Arch Linux)
pacman -Si package     # If remote (Arch Linux)
```

### 🔄 Upgrade the System
```sh
apt upgrade      # Debian/Ubuntu
dnf upgrade      # Fedora
pacman -Syu      # Arch Linux
```

---

## 🔹 Advanced Commands

### ❌ Complete Removal (Extra)
```sh
pacman -Rssn  # Remove package, dependencies, and configuration files
pacman -Rcun  # Less aggressive option than -Rssn
```

### 🧹 Package Cleanup
```sh
sudo pacman -Rns $(pacman -Qdtq)  # Remove orphaned packages
sudo pacman -Sc                   # Remove cached packages (except the most recent ones)
sudo pacman -Syy                  # Force update of the database
```
```sh
dnf autoremove      # Remove unused dependencies
dnf clean dbcache   # Clean database cache
```

---

## 🔹 Repository Management (DNF)
```sh
dnf repolist             # List active repositories
dnf repolist all         # List all repositories, including disabled ones
dnf config-manager --add-repo [URL]  # Add repository
dnf config-manager --set-enabled [repo_name]  # Enable a repository
dnf config-manager --set-disabled [repo_name]  # Disable a repository
```

---

## 🔹 Usage Examples

### 📥 Install a Package
```sh
sudo pacman -S vlc
```
📌 *Installs VLC Media Player, downloading the package and resolving dependencies.*

### 🔄 Upgrade the System
```sh
sudo pacman -Syu
```
📌 *Updates the database and then upgrades all installed packages.*

### ❌ Remove a Package
```sh
sudo pacman -R gimp
```
📌 *Removes the GIMP package from the system. If there are no dependencies, it will be completely removed.*

### 🧹 Clean Package Cache
```sh
sudo pacman -Scc
```
📌 *Removes all cached packages, freeing up disk space. Use with caution!*

### ℹ️ Consult an Installed Package
```sh
pacman -Qi nano
```
📌 *Shows detailed information about the Nano text editor.*

---

## 🤝 How to Contribute

💡 **Want to contribute to the project?** Follow the steps below:

1️⃣ Fork the repository.  
2️⃣ Create a branch with your improvement (`git checkout -b my-improvement`).  
3️⃣ Commit the changes (`git commit -m "Improvement: Added XYZ"`).  
4️⃣ Push to the repository (`git push origin my-improvement`).  
5️⃣ Open a Pull Request and describe your change!  

📢 *Suggestions and corrections are always welcome!* 🚀

---

## 📚 References and Documentation

📖 [APT - Debian Documentation](https://wiki.debian.org/Apt)  
📖 [DNF - Fedora Documentation](https://dnf.readthedocs.io/en/latest/)  
📖 [Pacman - Arch Wiki](https://wiki.archlinux.org/title/Pacman)  
📖 [Yay - AUR Helper](https://github.com/Jguer/yay)  

---

## 🖼️ Visuals

### Package Management Workflow

![Package Management Workflow](https://example.com/path/to/diagram.png)

### System Update Flowchart

![System Update Flowchart](https://example.com/path/to/flowchart.png)

---

## 🌐 Localization

This guide is available in:
- [English](README_EN.md)
- [Português](README.md)

---