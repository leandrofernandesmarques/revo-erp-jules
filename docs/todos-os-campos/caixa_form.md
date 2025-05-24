# Formulário: Caixa

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente" |
| Por período | Button | Não | Abre seletor de período |
| Filtros | Button | Não | Abre painel de filtros avançados |
| Limpar filtros | Button | Não | Remove filtros aplicados |
| Imprimir | Button | Não | Imprime relatório de caixa |
| Transferir | Button | Não | Abre formulário de transferência |
| Incluir lançamento | Button | Não | Abre formulário de novo lançamento |
| Mais ações | Dropdown button | Não | Opções adicionais |

## Tabela de Lançamentos

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox seleção | Checkbox | Seleciona lançamento para ações em massa |
| Data | Column | Data do lançamento |
| Histórico | Column | Descrição do lançamento |
| Cliente | Column | Nome do cliente relacionado |
| Categoria | Column | Categoria do lançamento |
| Entradas | Column | Valor de entrada (R$) |
| Saídas | Column | Valor de saída (R$) |
| Marcadores | Column | Etiquetas visuais |
| Origem | Column | Origem do lançamento |
| Ações | Button group | Botões de edição e exclusão |

## Resumo Financeiro

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Saldo atual | Label | Valor atual em caixa |
| Saldo inicial | Label | Valor inicial do período |
| Entradas | Label | Total de entradas no período |
| Saídas | Label | Total de saídas no período |
| Saldo final | Label | Saldo após movimentações |
| Lançamentos | Label | Quantidade de lançamentos |

## Formulário de Inclusão de Lançamento

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo | Radio buttons | Sim | Entrada, Saída |
| Data | Datepicker | Sim | Data atual |
| Valor | Input number | Sim | Formato monetário |
| Histórico | Input text | Sim | Descrição do lançamento |
| Cliente/Fornecedor | Autocomplete | Não | Seleciona contato |
| Categoria | Select | Não | Lista de categorias |
| Forma de pagamento | Select | Não | Lista de formas de pagamento |
| Conta | Select | Sim | Conta de destino |
| Marcadores | Multiselect | Não | Lista de marcadores |
| Observações | Textarea | Não | Texto livre |
| Comprovante | File upload | Não | Anexo de arquivo |

## Formulário de Transferência

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data | Datepicker | Sim | Data atual |
| Valor | Input number | Sim | Formato monetário |
| Conta de origem | Select | Sim | Lista de contas |
| Conta de destino | Select | Sim | Lista de contas |
| Histórico | Input text | Sim | Descrição da transferência |
| Observações | Textarea | Não | Texto livre |

## Filtros Avançados

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Date range picker | Não | Período atual |
| Tipo | Checkbox group | Não | Entradas, Saídas |
| Cliente/Fornecedor | Autocomplete | Não | Seleciona contato |
| Categoria | Select | Não | Lista de categorias |
| Forma de pagamento | Select | Não | Lista de formas de pagamento |
| Conta | Select | Não | Lista de contas |
| Marcadores | Multiselect | Não | Lista de marcadores |
| Valor mínimo | Input number | Não | Formato monetário |
| Valor máximo | Input number | Não | Formato monetário |
| Histórico | Input text | Não | Texto para busca |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva o lançamento ou transferência |
| Cancelar | Button | Cancela a operação atual |
| Excluir | Button | Remove o lançamento selecionado |
| Editar | Button | Abre formulário de edição |
| Duplicar | Button | Cria cópia do lançamento |
| Conciliar | Button | Marca lançamento como conciliado |
