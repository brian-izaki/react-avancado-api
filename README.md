# Projeto inicial com Strapi
Projeto seguindo curso de React Avançado

## Sumário

- [Anotações](#anotações)
  - [Content type builder](#content-type-builder)
  - [Postgres](#postgres)
- [Development](#development)
  - [Setup inicial](#setup-inicial)
  - [Iniciar projeto](#iniciar-projeto)
  - [Outros comandos](#outros-comandos)
- [Strapi initial content](#strapi-initial-content)
- [Referencias](#referencias)

---

## Anotações

### Content type builder

Monta a arquitetura de dados de conteúdo

<br>

### Postgres

```bash
# realizar backup do BD a partir do container
docker exec -i nome_container pg_dump -c --if-exists --exclude-table=nome_tabela_ignora_backup -h ipv4_postgres -U user_postgres -W > nome_arquivo.sql

# realizar importação de um backup
cat nome_arquivo.sql | docker exec -i nome_container psql -U nome_user_db

```

<br>

---

## Development

### Setup inicial
- ter o docker e o docker-compose instalado na máquina
- Execute para instalar e criar um container com o Postgres
  - _obs: deve estar no msm diretorio com o arquivo (deve estar no diretorio com o `docker-compose.yaml`)_ 
  ```bash
  docker-compose pull
  docker-compose up -d
  ```
- dados para importação
  - caso queira importar dados iniciais, use o arquivo [`strapi.sql`](./assets/strapi.sql), digite o seguinte comando no terminal (o caminho no terminal deve estar dentro do assets)
    ```bash
    # backup no postgres dentro de um container
    cat strapi.sql | docker exec -i nome_container psql -U nome_user_db
    ```
  - _obs: no momento desta anotação estou utilizando o wsl2 e rodando os comandos no terminal ubuntu com o docker ativo no windows._

### Iniciar projeto
- docker (deve estar no diretorio com o `docker-compose.yaml`)
  - Iniciar o postgres
    ```bash
    docker-compose up
    ```
  - parar o postgres
    ```bash
    docker-compose down
    ```

- Strapi (deve ter o postgres já rodando)
  - Iniciar Strapi com autoReload habilitado
    ```bash
    npm run develop
    # or
    yarn develop
    ```
  - Iniciar Strapi com autoReload desabilitado
    ```bash
    npm run start
    # or
    yarn start
    ```

### Outros comandos
- strapi
  - Fazer o build da tela de admin
    ```bash
    npm run build
    # or
    yarn build
    ```

---

## Referencias

- Strapi
  - [Cheat Sheet do strapi com as principais info](https://strapi-showcase.s3-us-west-2.amazonaws.com/CheatSheet.pdf)
  - [documentation](https://docs.strapi.io) - Official Strapi documentation.
  - [tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
  - [deploy](https://docs.strapi.io/developer-docs/latest/setup-deployment-guides/deployment.html)
  - [build](https://docs.strapi.io/developer-docs/latest/developer-resources/cli/CLI.html#strapi-build)
  - [Command Line Interface](https://docs.strapi.io/developer-docs/latest/developer-resources/cli/CLI.html)
- Postgres
  - [documentação pg_dump](https://www.postgresql.org/docs/current/app-pgdump.html)
