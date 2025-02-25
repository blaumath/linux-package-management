📦 Linux Package Management Guide
Este repositório contém um guia prático para gerenciar pacotes em distribuições Linux que utilizam APT (Debian/Ubuntu), DNF (Fedora) e Pacman (Arch Linux).

📌 Tabela Comparativa de Comandos
Aqui está um resumo rápido dos comandos mais comuns para gerenciamento de pacotes:

🛠️ Ação	🐧 APT (Debian/Ubuntu)	🔵 DNF (Fedora)	🔴 Pacman (Arch)
🔍 Buscar pacotes	apt search	dnf search	pacman -Ss
📥 Instalar pacote	apt install	dnf install	pacman -S
❌ Remover pacote	apt remove	dnf remove	pacman -R
🔄 Atualizar sistema	apt upgrade	dnf upgrade	pacman -Syu
🧹 Limpeza de cache	apt clean	dnf clean all	pacman -Scc
💡 Se preferir visualizar os comandos de forma detalhada, confira as seções abaixo!

🔹 Gerenciamento de Pacotes

Buscar Pacotes

apt search package  # Debian/Ubuntu
dnf search package  # Fedora
pacman -Ss package  # Arch Linux

Instalar Pacotes

apt install package  # Debian/Ubuntu
dnf install package  # Fedora
pacman -S package    # Arch Linux

Remover Pacotes

apt remove package  # Debian/Ubuntu
dnf remove package  # Fedora
pacman -R package   # Arch Linux

Exibir Informações do Pacote

apt show package       # Debian/Ubuntu
dnf info package       # Fedora
pacman -Qi package     # Se instalado (Arch Linux)
pacman -Si package     # Se remoto (Arch Linux)

Atualizar o Sistema

apt upgrade      # Debian/Ubuntu
dnf upgrade      # Fedora
pacman -Syu      # Arch Linux

🔹 Comandos Avançados

Remoção Completa (Extra)

pacman -Rssn  # Remove pacote, dependências e arquivos de configuração
pacman -Rcun  # Opção menos agressiva que -Rssn

Limpeza de Pacotes

sudo pacman -Rns $(pacman -Qdtq)  # Remove pacotes órfãos
sudo pacman -Sc                   # Remove pacotes em cache (exceto os mais recentes)
sudo pacman -Syy                  # Força atualização do banco de dados

dnf autoremove      # Remove dependências não utilizadas
dnf clean dbcache   # Limpa banco de dados

🔹 Gerenciamento de Repositórios (DNF)

dnf repolist             # Lista repositórios ativos
dnf repolist all         # Lista todos os repositórios, incluindo desativados
dnf config-manager --add-repo [URL]  # Adiciona repositório
dnf config-manager --set-enabled [repo_name]  # Ativa um repositório
dnf config-manager --set-disabled [repo_name]  # Desativa um repositório

🔹 Exemplo de Uso

Instalar um Pacote

sudo pacman -S vlc

📌 Este comando instala o VLC Media Player, baixando o pacote e resolvendo dependências.

Atualizar o Sistema

sudo pacman -Syu

📌 Este comando atualiza o banco de dados e depois realiza o upgrade de todos os pacotes instalados.

Remover um Pacote

sudo pacman -R gimp

📌 Remove o pacote GIMP do sistema. Se não houver dependências, ele será completamente removido.

Limpar Cache de Pacotes

sudo pacman -Scc

📌 Remove todos os pacotes em cache, liberando espaço no disco. Use com cautela!

Consultar um Pacote Instalado

pacman -Qi nano

📌 Mostra informações detalhadas sobre o editor de texto Nano.

🤝 Como Contribuir

Faça um fork do repositório.

Crie um branch com a sua feature (git checkout -b minha-melhoria).

Faça commit das mudanças (git commit -m "Melhoria: Adicionado XYZ").

Envie para o repositório (git push origin minha-melhoria).

Abra um Pull Request e descreva sua alteração!

📚 Referências

APT - Debian Documentation

DNF - Fedora Documentation

Pacman - Arch Wiki

Yay - AUR Helper

