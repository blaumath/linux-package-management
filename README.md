# linux-package-management
Comprehensive guide to package management in Linux (APT, DNF, Pacman, Yay)

# 📦 Linux Package Management Guide

Este repositório contém um guia completo para gerenciamento de pacotes no Linux, cobrindo os gerenciadores **APT**, **DNF**, **Pacman** e **Yay**.

---

## 📋 Índice
- [🔍 Busca de Pacotes](#-busca-de-pacotes)
- [📥 Instalação](#-instalação)
- [🗑 Remoção](#-remoção)
- [ℹ️ Informações](#%EF%B8%8F-informações)
- [📌 Atualização](#-atualização)
- [🧹 Limpeza](#-limpeza)
- [📂 Gerenciamento de Repositórios (DNF)](#-gerenciamento-de-repositórios-dnf)
- [🔧 Comandos Avançados (Pacman & Yay)](#-comandos-avançados-pacman--yay)

---

## 🔍 Busca de Pacotes
```sh
apt search package
dnf search package
pacman -Ss package
```

## 📥 Instalação
```sh
apt install package
dnf install package
pacman -S package
```

## 🗑 Remoção
```sh
apt remove package
dnf remove package
pacman -R package
```

## ℹ️ Informações
```sh
apt show package
dnf info package
pacman -Qi package  # Se estiver instalado
pacman -Si package  # Se estiver no repositório
```

## 📌 Atualização
```sh
apt upgrade
dnf upgrade
pacman -Syu
```

---

## 🧹 Limpeza
### **APT & DNF**
```sh
dnf autoremove   # Remove dependências não utilizadas
dnf clean all    # Limpa pacotes e metadados do DNF
```
### **Pacman**
```sh
sudo pacman -Rns $(pacman -Qdtq)  # Remove pacotes e dependências não utilizados
sudo pacman -Sc  # Remove pacotes antigos do cache
sudo pacman -Syy # Atualiza banco de dados dos pacotes
```

---

## 📂 Gerenciamento de Repositórios (DNF)
```sh
dnf repolist        # Lista repositórios habilitados
dnf repolist all    # Lista todos os repositórios (habilitados e desabilitados)
dnf config-manager --add-repo [URL] # Adiciona um repositório
dnf config-manager --set-enabled [repo_name] # Habilita um repositório
dnf config-manager --set-disabled [repo_name] # Desabilita um repositório
```

---

## 🔧 Comandos Avançados (Pacman & Yay)
### **Pacman**
```sh
sudo pacman -Syuu  # Força atualização completa do sistema
sudo pacman -Scc   # Limpa completamente o cache de pacotes
```

### **Yay (AUR Helper)**
```sh
yay -c                         # Lista pacotes do AUR e repositórios
yay -G package_name            # Baixa o PKGBUILD de um pacote do AUR
yay --repo package_name        # Assume que o pacote está no repositório
yay --aur package_name         # Assume que o pacote está no AUR
```

---

## 📜 Licença
Este guia é de uso livre. Sinta-se à vontade para contribuir ou sugerir melhorias! 🚀
