# Projeto inicial com Strapi
Projeto seguindo curso de React Avançado

## Sumário

- [Anotações](#anotações)
  - [Content type builder](#content-type-builder)
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
