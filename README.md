# Docker MySQL Workbench (Ubuntu 25.10 Questing)

Este repositório disponibiliza o **MySQL Workbench** dentro de um container Docker. Uma solução definitiva para quem enfrenta instabilidades na versão Questing do Ubuntu 25.10

## O Problema
Ao utilizar o novo **Ubuntu 25.10 (Questing)**, notei que a instalação do Workbench via métodos tradicionais apresentava falhas críticas:
* **APT:** Dependências desatualizadas para o ambiente
* **Snap:** Ausência de bibliotecas (libs) essenciais e conflitos no `dpkg`
* **Flatpak:** Inexistência da imagem oficial/estável necessária
* **Site Oficial (Oracle):** Problemas de compatibilidade similares ao Snap

## Obs: Projeto desenvolvido para fins de estudo e troubleshooting no curso de Desenvolvimento de Sistemas(Senac-RS). Ubuntu Questing estará ativo até 09/07/2026

## A Solução
Para isolar a ferramenta e evitar "brigar" com as bibliotecas do sistema, utilizei a imagem da `linuxserver/mysql-workbench` via **Docker Compose** 

**Resultado:** Interface estável, sem travamentos em diagramas ER ou criação de bancos, e sem poluir o sistema operacional principal (se caso quiser usar em seu OS, alguns navegadores oferecem a opção baixar(atalho desktop) logo ao lado da barra de busca)


## Conexões
Este container funciona como uma instalação limpa do MySQL Workbench
- Para conectar em bancos externos (RDS, Azure, DigitalOcean), use o IP/Hostname do servidor normalmente
- **Atenção:** Se tentar conectar em um MySQL instalado diretamente no seu `localhost` (fora do Docker), lembre-se que o isolamento de rede do Docker exigirá configurações adicionais de IP

## Como usar

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/Onnboy/docker-mysql-workbench
   cd docker-mysql-workbench
   cp .env.example .env
   docker compose up -d (padrão)
