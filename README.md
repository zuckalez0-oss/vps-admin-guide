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
Ver logs de um container específico em tempo real
```bash
docker logs -f <nome_do_container>
```
Subir ambiente via Docker Compose em segundo plano
```bash
docker-compose up -d
```
Limpar imagens, volumes e redes não utilizados
```bash
docker system prune -a --volumes
```
# 🔒 3. Segurança e Redes

Comandos para blindagem e controle de acesso via Tailscale ou Firewall.
Verificar status do Firewall (UFW)
```bash
sudo ufw status verbose
```
Liberar uma porta específica (ex: 8000 para Django)
```bash
sudo ufw allow 8000/tcp
```
Verificar status e dispositivos na rede Tailscale
```bash
tailscale status
```
Verificar portas em escuta no servidor
```bash
sudo ss -tunlp
```
# 🌐 4. Nginx & Proxy Reverso
Gerenciamento de tráfego e apontamento de domínios.
Testar sintaxe dos arquivos de configuração
```bash
sudo nginx -t
```
Recarregar Nginx após alterações
```bash
sudo systemctl reload nginx
```
Monitorar logs de erro de acesso
```bash
sudo tail -f /var/log/nginx/error.log
```
# 🛡️ 5. Monitoramento
Para auditoria interna e verificação de integridade.
Monitorar tentativas de login (SSH)
```bash
sudo tail -f /var/log/auth.log
```
Verificar quem está logado no momento
```bash
who -a
```
Listar conexões TCP ativas
```bash
netstat -atnp
```
# 📂 6. Arquivos e Backups
Movimentação de dados e permissões.
Alterar dono de uma pasta (Recursivo)
```bash
sudo chown -R $USER:$USER /caminho/do/diretorio
```
Copiar arquivo da VPS para sua máquina local (Executar no seu PC)
```bash
scp usuario@ip-da-vps:/caminho/arquivo/na/vps ~/Downloads/
```
Criar backup de banco de dados PostgreSQL (via Docker)
```bash
docker exec -t <container_db> pg_dumpall -c -U <usuario> > backup_db.sql
```
