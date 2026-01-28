# 🖥️ VPS Admin - Guia de Comandos Rápidos
Este repositório serve como uma folha de consulta (cheatsheet) para a administração diária de servidores Linux, com foco em performance, segurança e gerenciamento de containers.

# 🛠️ 1. Manutenção do Sistema
Comandos essenciais para manter o servidor atualizado e limpo.

Atualizar listas e pacotes

```bash
sudo apt update && sudo apt upgrade -y
```
Remover pacotes desnecessários e limpar cache
```bash
sudo apt autoremove -y && sudo apt autoclean
```
Verificar uso de disco por partição
```bash
df -h
```
Monitorar recursos (CPU/RAM) em tempo real
```bash
htop
```

# 🐳 2. Gestão de Docker & Containers
Essencial para gerenciar suas automações no n8n e apps em Django/Spring Boot.
Listar todos os containers (ativos e parados)
```bash
docker ps -a
```
