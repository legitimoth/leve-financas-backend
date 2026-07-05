# Leve Finanças --- Architecture Decision Records (ADRs)

> Este documento registra as principais decisões arquiteturais do
> projeto e o motivo de cada uma delas.

------------------------------------------------------------------------

# ADR-001 --- Backend em .NET 10 (LTS)

## Decisão

Utilizar .NET 10 LTS como plataforma principal do backend.

## Motivos

-   Atualização técnica com o ecossistema .NET.
-   Excelente performance.
-   Ecossistema maduro.
-   Ótima integração com Angular.
-   Facilidade para futuros projetos do canal.

------------------------------------------------------------------------

# ADR-002 --- Banco PostgreSQL

## Decisão

Utilizar PostgreSQL.

## Motivos

-   Gratuito.
-   Amplamente suportado por provedores cloud.
-   Confiável e maduro.
-   Excelente integração com EF Core.

------------------------------------------------------------------------

# ADR-003 --- Entity Framework Core

## Decisão

Utilizar EF Core como ORM.

## Motivos

-   Alta produtividade.
-   Migrations nativas.
-   Boa integração com PostgreSQL.
-   Menor complexidade para o MVP.

------------------------------------------------------------------------

# ADR-004 --- Organização por Features

## Decisão

Organizar o projeto por Features (módulos).

## Motivos

-   Navegação simples.
-   Tudo relacionado ao módulo fica no mesmo lugar.
-   Facilita manutenção.
-   Possibilita futura extração para microserviços, caso necessário.

------------------------------------------------------------------------

# ADR-005 --- Domínio Compartilhado

## Decisão

Entities e Enums ficam em Domain.

## Motivos

-   Representam conceitos de negócio.
-   São reutilizados por diversas features.
-   Evita duplicação.

------------------------------------------------------------------------

# ADR-006 --- Features Independentes

## Decisão

Uma feature não deve depender da implementação de outra.

## Motivos

-   Reduz acoplamento.
-   Facilita manutenção.
-   Facilita evolução futura.

------------------------------------------------------------------------

# ADR-007 --- Repository Pattern

## Decisão

Cada feature terá seu próprio Repository.

## Motivos

-   Restringe o acesso aos dados da própria feature.
-   Centraliza consultas.
-   Mantém regras de acesso ao banco organizadas.

### RepositoryBase

O RepositoryBase conterá apenas operações CRUD genéricas.

Consultas específicas permanecem no Repository da própria Feature.

------------------------------------------------------------------------

# ADR-008 --- ThCodes.Core

## Decisão

Criar o ThCodes.Core como um projeto separado dentro da mesma Solution.

## Motivos

-   Desenvolvimento simultâneo.
-   Evita publicar versões NuGet durante a construção.
-   Após estabilização, será extraído para um repositório próprio.

------------------------------------------------------------------------

# ADR-009 --- Autenticação

## Decisão

Não implementar autenticação no MVP.

## Motivos

-   Foco na entrega das funcionalidades.
-   Arquitetura preparada para multiusuário.

### Futuro

Avaliar: - Auth0 - Clerk

------------------------------------------------------------------------

# ADR-010 --- Filosofia do Projeto

## Princípios

-   Simplicidade acima de tudo.
-   Não adicionar complexidade sem necessidade.
-   Evoluir conforme o projeto crescer.
-   Código organizado por responsabilidade.
-   Reutilização através do ThCodes.Core.
-   Decisões baseadas em necessidade real, e não em tendências
    arquiteturais.
