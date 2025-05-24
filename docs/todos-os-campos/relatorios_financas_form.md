# Formulário: Relatórios Financeiros

## Navegação Principal

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Geral | Tab | Acesso aos relatórios gerais de finanças |
| Caixa | Tab | Acesso aos relatórios específicos de caixa |
| Contas a Pagar | Tab | Acesso aos relatórios de contas a pagar |
| Contas a Receber | Tab | Acesso aos relatórios de contas a receber |
| Outros relatórios | Button | Acesso a relatórios adicionais |

## Relatório: Balancete

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Conta | Select | Não | Todas, Caixa, Aplicação, Banco Inter |
| Considerar transferências | Checkbox | Não | Desativado por padrão |
| Categoria | Select | Não | Lista de categorias financeiras |
| Visualização | Select | Não | Automática, Por dia, Por semana, Por mês |
| Tipo do gráfico | Select | Não | Não exibir, Linhas, Barras |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |
| Exibir filtros | Button | Mostra/oculta os filtros do relatório |
| Download | Button | Baixa o relatório em formato CSV/Excel |
| Compartilhar | Button | Permite compartilhar o relatório |
| Imprimir | Button | Imprime o relatório |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Categoria | Column | Categoria da transação |
| Período (colunas) | Column group | Colunas de períodos (semanas/meses) |
| Entradas | Row group | Valores de entrada por categoria |
| Saídas | Row group | Valores de saída por categoria |
| Resultado | Row group | Cálculos de totais e saldos |
| Total | Column | Soma dos valores por linha |

## Relatório: Fluxo de Caixa

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Períodos | Button group | Sim | Do mês, Até o mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Visualização | Select | Não | Automática, Por dia, Por semana, Por mês |
| Tipo do gráfico | Select | Não | Não exibir, Linhas, Barras |
| Contas atrasadas | Select | Não | Considerar no saldo inicial, Não considerar |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |
| Exibir filtros | Button | Mostra/oculta os filtros do relatório |
| Download | Button | Baixa o relatório em formato CSV/Excel |
| Compartilhar | Button | Permite compartilhar o relatório |
| Imprimir | Button | Imprime o relatório |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Categoria | Column | Categoria da transação |
| Período (colunas) | Column group | Colunas de períodos (semanas/meses) |
| Receitas | Row group | Valores de receita por categoria |
| Despesas | Row group | Valores de despesa por categoria |
| Resultado | Row group | Cálculos de saldo inicial, totais e saldo acumulado |
| Total | Column | Soma dos valores por linha |

## Relatório: Entradas e Saídas por Categoria

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Conta | Select | Não | Todas, Caixa, Aplicação, Banco Inter |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Categoria | Column | Categoria da transação |
| Valor | Column | Valor total por categoria |
| Percentual | Column | Percentual em relação ao total |

## Relatório: Entradas e Saídas por Cliente

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Conta | Select | Não | Todas, Caixa, Aplicação, Banco Inter |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Cliente | Column | Nome do cliente/fornecedor |
| Valor | Column | Valor total por cliente |
| Percentual | Column | Percentual em relação ao total |

## Relatório: Contas a Pagar

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Períodos | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Situação | Select | Não | Todas, Em aberto, Emitidas, Pagas, Atrasadas, Canceladas |
| Categoria | Select | Não | Lista de categorias financeiras |
| Marcador | Select | Não | Sem filtro por marcador, Agrupado, Sem marcadores |
| Agrupar por | Select | Não | Não agrupar, Fornecedor, Data de vencimento, Categoria |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Fornecedor | Column | Nome do fornecedor |
| Histórico | Column | Descrição da conta |
| Vencimento | Column | Data de vencimento |
| Valor | Column | Valor da conta |
| Situação | Column | Status da conta |

## Relatório: Recebimentos

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Forma de recebimento | Select | Não | Todas, Dinheiro, Cartão, Boleto, etc. |
| Cliente | Select | Não | Lista de clientes |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Data | Column | Data do recebimento |
| Cliente | Column | Nome do cliente |
| Histórico | Column | Descrição do recebimento |
| Forma | Column | Forma de recebimento |
| Valor | Column | Valor recebido |

## Relatório: Contas a Receber

### Filtros e Parâmetros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Períodos | Button group | Sim | Do mês, Intervalo |
| Mês | Input date | Sim (se "Do mês") | Mês atual |
| Data inicial | Input date | Sim (se "Intervalo") | Primeiro dia do mês atual |
| Data final | Input date | Sim (se "Intervalo") | Último dia do mês atual |
| Situação | Select | Não | Todas, Em aberto, Emitidas, Recebidas, Atrasadas, Canceladas |
| Categoria | Select | Não | Lista de categorias financeiras |
| Marcador | Select | Não | Sem filtro por marcador, Agrupado, Sem marcadores |
| Agrupar por | Select | Não | Não agrupar, Cliente, Data de vencimento, Categoria |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |

### Tabela de Resultados

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Cliente | Column | Nome do cliente |
| Histórico | Column | Descrição da conta |
| Vencimento | Column | Data de vencimento |
| Valor | Column | Valor da conta |
| Situação | Column | Status da conta |

## Botões de Ação (Comuns a todos os relatórios)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |
| Exibir filtros | Button | Mostra/oculta os filtros do relatório |
| Download | Button | Baixa o relatório em formato CSV/Excel |
| Compartilhar | Button | Permite compartilhar o relatório |
| Imprimir | Button | Imprime o relatório |
