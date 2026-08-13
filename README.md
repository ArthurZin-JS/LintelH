# LintelH Painel

Tema personalizado do Pterodactyl, com identidade visual azul/branco da LintelH.

**Autor:** Arthur L

## Instalação

Isso vai substituir os arquivos do seu Painel Pterodactyl pelos arquivos do LintelH Painel.
Você pode ver a versão base (Pterodactyl) no nome do arquivo de release.

### Requisitos

- PHP 8.1 ou superior (mesmo requisito do Pterodactyl original)
- Uma instalação do Pterodactyl já funcionando

### Passo 1 — Entrar em modo de manutenção

```bash
cd /var/www/pterodactyl

php artisan down
```

### Passo 2 — Baixar o tema

```bash
curl -L https://github.com/ArthurZin-JS/LintelH/releases/download/1.0/panel.tar.gz | tar -xzv
```

Depois de baixar os arquivos, ajuste as permissões das pastas de cache e storage:

```bash
chmod -R 755 storage/* bootstrap/cache
```

### Passo 3 — Atualizar dependências

```bash
composer install --no-dev --optimize-autoloader
```

### Passo 4 — Limpar cache de templates

```bash
php artisan view:clear
php artisan config:clear
```

### Passo 5 — Permissões finais

```bash
# NGINX ou Apache (exceto CentOS):
chown -R www-data:www-data /var/www/pterodactyl/*

# NGINX no CentOS:
chown -R nginx:nginx /var/www/pterodactyl/*

# Apache no CentOS:
chown -R apache:apache /var/www/pterodactyl/*
```

### Passo 6 — Reiniciar filas

```bash
php artisan queue:restart
```

### Passo 7 — Sair do modo de manutenção

```bash
php artisan up
```

Pronto! Seu painel agora está com o tema LintelH.

---

## Reverter para o Pterodactyl original

Basta repetir os mesmos passos usando o `panel.tar.gz` oficial do
[Pterodactyl](https://github.com/pterodactyl/panel/releases/latest).
