# 📦 Linux Package Management Guide

Este repositório contém um guia prático para gerenciar pacotes em distribuições Linux que utilizam **APT (Debian/Ubuntu)**, **DNF (Fedora)** e **Pacman (Arch Linux)**.

---

## 📌 Tabela Comparativa de Comandos

Aqui está um resumo rápido dos comandos mais comuns para gerenciamento de pacotes:

| 🛠️ Ação             | 🐧 APT (Debian/Ubuntu) | 🔵 DNF (Fedora)  | 🔴 Pacman (Arch)  |
|------------------|-------------------|---------------|----------------|
| 🔍 Buscar pacotes  | `apt search`      | `dnf search`  | `pacman -Ss`  |
| 📥 Instalar pacote | `apt install`     | `dnf install` | `pacman -S`   |
| ❌ Remover pacote  | `apt remove`      | `dnf remove`  | `pacman -R`   |
| 🔄 Atualizar sistema | `apt upgrade`     | `dnf upgrade` | `pacman -Syu` |
| 🧹 Limpeza de cache | `apt clean`       | `dnf clean all` | `pacman -Scc` |

💡 *Se preferir visualizar os comandos de forma detalhada, confira as seções abaixo!*

---

## 🔹 Gerenciamento de Pacotes

### 🔍 Buscar Pacotes
```sh
apt search package  # Debian/Ubuntu
dnf search package  # Fedora
pacman -Ss package  # Arch Linux
```

### 📥 Instalar Pacotes
```sh
apt install package  # Debian/Ubuntu
dnf install package  # Fedora
pacman -S package    # Arch Linux
```

### ❌ Remover Pacotes
```sh
apt remove package  # Debian/Ubuntu
dnf remove package  # Fedora
pacman -R package   # Arch Linux
```

### ℹ️ Exibir Informações do Pacote
```sh
apt show package       # Debian/Ubuntu
dnf info package       # Fedora
pacman -Qi package     # Se instalado (Arch Linux)
pacman -Si package     # Se remoto (Arch Linux)
```

### 🔄 Atualizar o Sistema
```sh
apt upgrade      # Debian/Ubuntu
dnf upgrade      # Fedora
pacman -Syu      # Arch Linux
```

---

## 🔹 Comandos Avançados

### ❌ Remoção Completa (Extra)
```sh
pacman -Rssn  # Remove pacote, dependências e arquivos de configuração
pacman -Rcun  # Opção menos agressiva que -Rssn
```

### 🧹 Limpeza de Pacotes
```sh
sudo pacman -Rns $(pacman -Qdtq)  # Remove pacotes órfãos
sudo pacman -Sc                   # Remove pacotes em cache (exceto os mais recentes)
sudo pacman -Syy                  # Força atualização do banco de dados
```
```sh
dnf autoremove      # Remove dependências não utilizadas
dnf clean dbcache   # Limpa banco de dados
```

---

## 🔹 Gerenciamento de Repositórios (DNF)
```sh
dnf repolist             # Lista repositórios ativos
dnf repolist all         # Lista todos os repositórios, incluindo desativados
dnf config-manager --add-repo [URL]  # Adiciona repositório
dnf config-manager --set-enabled [repo_name]  # Ativa um repositório
dnf config-manager --set-disabled [repo_name]  # Desativa um repositório
```

---

## 🔹 Exemplos de Uso

### 📥 Instalar um Pacote
```sh
sudo pacman -S vlc
```
📌 *Instala o VLC Media Player, baixando o pacote e resolvendo dependências.*

### 🔄 Atualizar o Sistema
```sh
sudo pacman -Syu
```
📌 *Atualiza o banco de dados e depois realiza o upgrade de todos os pacotes instalados.*

### ❌ Remover um Pacote
```sh
sudo pacman -R gimp
```
📌 *Remove o pacote GIMP do sistema. Se não houver dependências, ele será completamente removido.*

### 🧹 Limpar Cache de Pacotes
```sh
sudo pacman -Scc
```
📌 *Remove todos os pacotes em cache, liberando espaço no disco. Use com cautela!*

### ℹ️ Consultar um Pacote Instalado
```sh
pacman -Qi nano
```
📌 *Mostra informações detalhadas sobre o editor de texto Nano.*

---

## 🤝 Como Contribuir

💡 **Quer contribuir com o projeto?** Siga os passos abaixo:

1️⃣ Faça um **fork** do repositório.  
2️⃣ Crie um **branch** com a sua melhoria (`git checkout -b minha-melhoria`).  
3️⃣ Faça commit das mudanças (`git commit -m "Melhoria: Adicionado XYZ"`).  
4️⃣ Envie para o repositório (`git push origin minha-melhoria`).  
5️⃣ Abra um **Pull Request** e descreva sua alteração!  

📢 *Sugestões e correções são sempre bem-vindas!* 🚀

---

## 📚 Referências e Documentação

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

Este guia está disponível em:
- [English](README_EN.md)
- [Português](README.md)

---
