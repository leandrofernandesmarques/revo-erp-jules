# Formulário: Dashboard

## Dashboard de Vendas

### Filtros e Controles

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Select | Sim | últimos 7 dias (padrão), últimos 30 dias, mês atual, mês anterior, personalizado |
| Filtros | Button/Modal | Não | Abre modal com filtros adicionais |
| Atualizado | Label | N/A | Mostra quando foi a última atualização |
| Expandir detalhes | Link | Não | Expande cards para mostrar mais informações |

### Visão Geral - Cards Informativos

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Total das vendas | Card informativo | Valor total de vendas no período |
| Ticket médio | Card informativo | Valor médio por venda no período |
| Pedidos | Card informativo | Número total de pedidos no período |
| Vendas em e-commerce | Card informativo | Número de vendas online |
| Vendas físicas | Card informativo | Número de vendas presenciais |
| Valor total | Card informativo | Valor total de todas as vendas |
| NF-e emitidas | Card informativo | Número de notas fiscais emitidas |
| Integração em alta | Card informativo | Canal de vendas com melhor desempenho |

### Gráficos e Visualizações

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Gráfico de vendas | Gráfico interativo | Evolução de vendas no período |
| Produtos mais vendidos | Tabela | Lista de produtos com melhor desempenho |
| Pedidos por integrações | Gráfico | Distribuição de pedidos por canal |
| Pedidos por estado | Mapa interativo | Distribuição geográfica de vendas |

## Dashboard de Finanças

### Filtros e Controles

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Select | Sim | últimos 7 dias (padrão), últimos 30 dias, mês atual, mês anterior, personalizado |
| Filtros | Button/Modal | Não | Abre modal com filtros adicionais |
| Atualizado | Label | N/A | Mostra quando foi a última atualização |

### Visão Geral - Cards Informativos

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Saldo atual | Card informativo | Saldo disponível em todas as contas |
| Contas a receber | Card informativo | Valor total a receber no período |
| Contas a pagar | Card informativo | Valor total a pagar no período |
| Fluxo de caixa | Card informativo | Diferença entre entradas e saídas |

### Gráficos e Visualizações

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Gráfico de fluxo de caixa | Gráfico interativo | Evolução de entradas e saídas |
| Contas por categoria | Gráfico | Distribuição de despesas por categoria |
| Previsão financeira | Gráfico | Projeção de saldo para próximos períodos |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Atualizar | Button | Atualiza os dados do dashboard |
| Exportar | Button | Exporta dados para relatório |
| Configurar | Button | Personaliza visualização do dashboard |
