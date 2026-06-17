💰 Sistema Financeiro Pessoal

Um sistema financeiro pessoal simples, focado em organização e controle de gastos, sem tentar substituir aplicativos bancários.

A proposta é ser uma ferramenta leve para acompanhar:

* 🛒 Compras avulsas
* 🔁 Despesas recorrentes
* 💳 Cartões de crédito
* 🏷️ Tags e categorias
* 📈 Estatísticas e dashboards

⸻

✨ Objetivos

O sistema foi pensado com alguns princípios:

* Simplicidade acima de tudo
* Cadastro rápido e intuitivo
* Armazenar apenas fatos que realmente aconteceram
* Não controlar saldo bancário ou fazer conciliação
* Permitir crescimento gradual de funcionalidades

⸻

🛒 Compras

Representa qualquer gasto não recorrente.

Exemplos:

* Mercado
* Restaurante
* Amazon
* IPTU
* IPVA
* Viagens
* Compras parceladas

Recursos

* Cadastro de valor e data
* Associação de tags
* Diversas formas de pagamento
* Compras parceladas no cartão
* Histórico de parcelas pagas
* Possibilidade de adiantamento de parcelas

⸻

🔁 Despesas recorrentes

Representa obrigações que se repetem ao longo do tempo.

Exemplos:

* Academia 🏋️
* Netflix 🎬
* ChatGPT 🤖
* Plano de saúde 🩺
* Internet 🌐
* Celular 📱
* Seguro 🚗
* Financiamento 🏠

Recursos

* Periodicidade:
    * Mensal
    * Trimestral
    * Semestral
    * Anual
* Status:
    * ✅ Ativa
    * ⏸️ Pausada
    * ❌ Cancelada
* Registro de pagamentos realizados
* Alteração de valor sem perder histórico
* Possibilidade de pagamentos adiantados

⸻

💳 Cartões

Cadastro simplificado de cartões.

Informações armazenadas:

* Nome
* Últimos 4 dígitos
* Dia de fechamento
* Dia de vencimento
* Limite

Segurança 🔒

O sistema não armazena:

* Número completo do cartão
* CVV
* Data de validade
* Nome impresso

⸻

🏷️ Tags

Permitem categorizar compras e despesas recorrentes.

Exemplos:

* IA 🤖
* Trabalho 💼
* Casa 🏠
* Saúde 🩺
* Carro 🚗
* Lazer 🎮
* Streaming 📺

⸻

💸 Formas de pagamento

Inicialmente:

* PIX
* Débito
* Crédito
* Boleto
* Dinheiro
* Transferência

⸻

🧠 Filosofia de modelagem

O banco de dados deve armazenar apenas fatos ocorridos.

Exemplo

Se uma compra foi parcelada em 12x:

* A compra é armazenada uma única vez.
* Os pagamentos das parcelas são registrados somente quando forem pagos.

O mesmo vale para despesas recorrentes:

* A despesa representa a obrigação.
* Os pagamentos representam os eventos que realmente aconteceram.

Isso reduz complexidade, evita inconsistências e facilita a evolução do sistema.

⸻

🚀 Roadmap

MVP

Fase 1

* CRUD de Tags
* CRUD de Cartões
* CRUD de Compras
* CRUD de Despesas Recorrentes

Fase 2

* Registro de pagamentos de parcelas
* Registro de pagamentos de despesas recorrentes
* Tela de contas do mês

Fase 3

* Dashboard
* Gastos por categoria
* Próximas cobranças
* Estatísticas

⸻

🔮 Futuro

Funcionalidades que podem ser adicionadas posteriormente:

* A pensar
⸻

💡 Este projeto nasceu com uma ideia simples:

Ter clareza sobre para onde o dinheiro está indo, sem a complexidade dos aplicativos financeiros tradicionais.