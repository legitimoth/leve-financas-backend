# Leve Finanças --- Decisões de Arquitetura

## Objetivo

Construir um SaaS de controle financeiro pessoal, priorizando
simplicidade, organização e reutilização de código.

------------------------------------------------------------------------

# Stack Tecnológica

## Backend

-   .NET 10 (LTS)
-   ASP.NET Core Web API

## Frontend

-   Angular (desenvolvido em uma série separada)

## Banco de Dados

-   PostgreSQL

## ORM

-   Entity Framework Core

## Migrations

-   EF Core Migrations

## Validação

-   FluentValidation

## Documentação

-   Swagger / OpenAPI

## Autenticação

-   MVP: usuário fixo (CurrentUser mockado)
-   Futuro: avaliar Auth0 ou Clerk
-   Não utilizar ASP.NET Identity

------------------------------------------------------------------------

# Estrutura da Solution

    LeveFinancas.sln

    ├── LeveFinancas.Backend
    └── ThCodes.Core

## ThCodes.Core (temporário na mesma solution)

Objetivo: evoluir junto com o projeto e futuramente ser extraído para um
repositório próprio e distribuído via NuGet.

Conteúdo previsto:

-   ControllerBase
-   RepositoryBase
-   Result / ApiResponse
-   CurrentUser
-   Paginação
-   Tratamento global de exceções
-   Middlewares compartilhados
-   Utilitários reutilizáveis

------------------------------------------------------------------------

# Estrutura do Backend

    LeveFinancas.Backend

    Features/
        Compras/
        Cartoes/
        Tags/
        DespesasRecorrentes/
        Dashboard/

    Domain/
        Entities/
        Enums/

    Configuration/
    Middlewares/
    Extensions/

    Program.cs

## Estrutura de cada Feature

    Cartoes/

    Controllers/
    Services/
    Repositories/
    Contracts/
    Mappers/

## Regras Arquiteturais

-   Features não dependem umas das outras.
-   Cada feature acessa apenas seu próprio repositório.
-   Entidades ficam em Domain por serem compartilhadas.
-   Services representam responsabilidades da feature.
-   Caso uma Service cresça demais, extrair novas Services específicas.
-   RepositoryBase apenas com operações CRUD genéricas.
-   Consultas específicas permanecem no Repository da Feature.

------------------------------------------------------------------------

# Modelo de Usuário

Durante o MVP:

-   Usuário fixo
-   CurrentUser preenchido por middleware

Preparação para autenticação futura:

-   UserId nas entidades raiz:
    -   Compra
    -   Cartão
    -   Tag
    -   DespesaRecorrente

Entidades filhas herdam o contexto pelo relacionamento.

------------------------------------------------------------------------

# Filosofia

-   Modular Monolith
-   Organização por Features
-   Código simples
-   Evoluir somente quando necessário
-   Reutilizar componentes através do ThCodes.Core
