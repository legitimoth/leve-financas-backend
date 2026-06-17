# Sistema Financeiro Pessoal - Especificação MVP

## Objetivo

Sistema simples para controle financeiro pessoal focado em: - Compras -
Despesas recorrentes - Cartões de crédito - Tags - Acompanhamento de
pagamentos

## Filosofia

-   Simplicidade acima de tudo.
-   O banco armazena apenas fatos que aconteceram.
-   Projeções e pendências são calculadas pela aplicação.
-   Não haverá controle de contas bancárias no MVP.

------------------------------------------------------------------------

# Entidades

## Compra

Representa qualquer gasto não recorrente.

### Campos

-   id
-   descricao (obrigatório)
-   valor_total (obrigatório)
-   data_compra (obrigatório)
-   forma_pagamento (obrigatório)
-   cartao_id (opcional)
-   quantidade_parcelas (opcional)
-   observacao (opcional)
-   tags \[\]

### Regras

-   Pode ser à vista ou parcelada.
-   Se forma_pagamento = Crédito, cartão e quantidade de parcelas podem
    ser informados.
-   Não existe status pendente/pago na compra.

------------------------------------------------------------------------

## PagamentoParcela

Representa um pagamento realizado de uma parcela de uma compra.

### Campos

-   id
-   compra_id
-   numero_parcela
-   valor_pago
-   data_pagamento

### Regras

-   Só existe quando a parcela foi paga.
-   Parcelas futuras não ficam armazenadas.
-   Adiantamento de parcelas gera múltiplos registros com a mesma data.

------------------------------------------------------------------------

## DespesaRecorrente

Representa obrigações recorrentes.

### Exemplos

-   Academia
-   Netflix
-   Plano de saúde
-   Internet
-   Celular
-   Seguro
-   Financiamento

### Campos

-   id
-   nome
-   valor_atual
-   periodicidade
-   proxima_cobranca
-   status
-   forma_pagamento
-   observacao
-   tags \[\]

### Periodicidades

-   Mensal
-   Trimestral
-   Semestral
-   Anual

### Status

-   Ativa
-   Pausada
-   Cancelada

### Regras

-   Valor pode ser alterado sem perder histórico.
-   Não é necessário cancelar para reajustar preço.

------------------------------------------------------------------------

## PagamentoDespesaRecorrente

Representa um pagamento realizado.

### Campos

-   id
-   despesa_recorrente_id
-   competencia
-   valor_pago
-   data_pagamento
-   observacao

### Regras

-   Só existe quando ocorreu pagamento.
-   Competências futuras são calculadas pela aplicação.
-   Permite pagamentos adiantados.

------------------------------------------------------------------------

## Cartao

### Campos

-   id
-   nome
-   ultimos_4_digitos
-   dia_fechamento
-   dia_vencimento
-   limite

### Regras

-   Nunca armazenar número completo.
-   Nunca armazenar CVV.
-   Nunca armazenar validade.

------------------------------------------------------------------------

## Tag

### Campos

-   id
-   nome
-   cor (opcional)

### Regras

-   Pode ser associada a Compras e Despesas Recorrentes.

------------------------------------------------------------------------

## Forma de Pagamento

Lista fixa: - PIX - Débito - Crédito - Boleto - Dinheiro - Transferência

Não haverá CRUD para formas de pagamento no MVP.

------------------------------------------------------------------------

# Roadmap MVP

## Fase 1

-   CRUD Tag
-   CRUD Cartão
-   CRUD Compra
-   CRUD Despesa Recorrente

## Fase 2

-   Registro de PagamentoParcela
-   Registro de PagamentoDespesaRecorrente
-   Tela de contas do mês

## Fase 3

-   Dashboard
-   Gastos por tag
-   Próximas cobranças
-   Estatísticas

------------------------------------------------------------------------

# Futuro (fora do MVP)

-   A pensar
