---
title: 'Atualizando o PostgreSQL no Docker: Guia Prático'
date: Sun, 25 Jan 2026 16:00:00 +0000
draft: false
tags: ['postgresql', 'docker', 'banco de dados', 'devops', 'containers', 'upgrade', 'migração']
---

Manter o PostgreSQL atualizado é uma prática essencial para qualquer desenvolvedor ou equipe de infraestrutura. Novas versões trazem melhorias de performance, correções de segurança e, principalmente, novos recursos que muitas aplicações modernas passam a exigir como requisito mínimo.

Recentemente, me deparei com essa necessidade: algumas aplicações que eu precisava rodar exigiam uma versão mais recente do PostgreSQL como requisito. Precisei encontrar uma forma simples e segura de fazer essa atualização sem perder meus dados.

Neste artigo, vamos aprender juntos como atualizar o PostgreSQL em containers Docker de forma prática e sem complicações.

---

## Antes de Começar

Para seguir este guia, você vai precisar de:

- Docker instalado
- Acesso ao terminal
- Saber o nome ou ID do container onde o PostgreSQL está rodando

Vamos utilizar o comando `pg_dump`, uma ferramenta nativa do PostgreSQL que cria uma cópia completa do seu banco de dados em formato SQL. Essa cópia pode ser restaurada em qualquer versão compatível do PostgreSQL.

**Dica:** Para descobrir o nome ou ID do seu container, use o comando `docker ps`.

---

## Passo 1: Fazer o Dump do Banco de Dados

Primeiro, vamos criar um backup (dump) do banco de dados. Esse backup será usado para popular o novo container. Não é necessário parar o container para isso, pois o `pg_dump` consegue fazer a exportação com o banco em execução.

```bash
docker exec -it <nome-do-container> pg_dump -U <usuario> <nome-do-banco> > db_backup.sql
```

**Exemplo prático:**

```bash
docker exec -it meu_postgres pg_dump -U postgres minha_aplicacao > db_backup.sql
```

Após executar o comando, você terá um arquivo `db_backup.sql` no diretório atual com todo o conteúdo do seu banco de dados.

---

## Passo 2: Parar e Remover o Container Atual

Agora vamos parar e remover o container atual para poder criar um novo com a versão atualizada.

```bash
docker stop <nome-do-container>
docker rm <nome-do-container>
```

**Exemplo prático:**

```bash
docker stop meu_postgres
docker rm meu_postgres
```

---

## Passo 3: Criar o Novo Container com a Versão Atualizada

Vamos criar um novo container com a versão atualizada do PostgreSQL. Por exemplo, se você estava rodando a versão 15 e quer atualizar para a versão 17:

```bash
docker run -d --name <nome-do-container> -e POSTGRES_PASSWORD=<senha> postgres:17
```

**Exemplo prático:**

```bash
docker run -d --name meu_postgres -e POSTGRES_PASSWORD=minha_senha postgres:17
```

**IMPORTANTE:** Se você está atualizando de uma versão anterior à 18 para a versão 18 ou superior, o caminho do volume de dados mudou de `/var/lib/postgresql/data` para `/var/lib/postgresql/<versao>/docker`. Consulte a documentação oficial para mais detalhes.

---

## Passo 4: Importar o Banco de Dados

Por fim, vamos importar o backup para o novo container, restaurando todos os dados.

```bash
cat db_backup.sql | docker exec -i <nome-do-container> psql -U <usuario> <nome-do-banco>
```

**Exemplo prático:**

```bash
cat db_backup.sql | docker exec -i meu_postgres psql -U postgres minha_aplicacao
```

Aguarde a execução completa. Dependendo do tamanho do banco, pode levar alguns minutos.

---

## Conclusão

Com esses quatro passos, você consegue atualizar seu PostgreSQL em containers Docker de forma segura e sem complicações. Resumindo o processo: **backup → parar container → criar novo container → restaurar**.

Algumas dicas importantes:

- **Sempre teste em desenvolvimento primeiro** antes de aplicar em produção
- **Mantenha seus backups em local seguro**, de preferência em mais de um lugar
- **Verifique a compatibilidade** da nova versão com sua aplicação antes de atualizar

Participe do nosso grupo no [WhatsApp](https://chat.whatsapp.com/DeshTGsaqy53ZfUDvYzfy9).

Bons estudos e mãos à obra!
