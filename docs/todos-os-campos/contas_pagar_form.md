# Formulário: Contas a Pagar

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por fornecedor ou nº doc" |
| Por período | Dropdown | Não | Padrão: "Últimos 30 dias" |
| Filtros | Button | Não | Abre painel de filtros avançados |
| Limpar filtros | Button | Não | Remove filtros aplicados |
| Imprimir | Button | Não | Imprime relatório de contas a pagar |
| Gerenciar pagamentos | Button | Não | Abre painel de gerenciamento |
| Incluir conta a pagar | Button | Não | Abre formulário de nova conta |
| Mais ações | Dropdown button | Não | Opções adicionais |

## Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Todas | Tab | Exibe todas as contas |
| Em aberto | Tab | Exibe apenas contas em aberto |
| Emitidas | Tab | Exibe apenas contas emitidas |
| Pagas | Tab | Exibe apenas contas pagas |
| Atrasadas | Tab | Exibe apenas contas atrasadas |
| Canceladas | Tab | Exibe apenas contas canceladas |

## Tabela de Contas a Pagar

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox seleção | Checkbox | Seleciona conta para ações em massa |
| Fornecedor | Column | Nome do fornecedor |
| Histórico | Column | Descrição da conta |
| Nº documento | Column | Número do documento |
| Vencimento | Column | Data de vencimento |
| Valor | Column | Valor da conta (R$) |
| Saldo | Column | Saldo pendente (R$) |
| Pago | Column | Valor já pago (R$) |
| Marcadores | Column | Etiquetas visuais |
| Ações | Button group | Botões de edição, pagamento e exclusão |

## Formulário de Inclusão/Edição - Guia: Dados da conta

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Forma Pagamento | Select | Sim | Lista de formas de pagamento |
| Fornecedor | Autocomplete | Sim | Pesquisa por iniciais do nome |
| Vencimento | Datepicker | Sim | Data futura |
| Valor | Input number | Sim | Formato monetário |
| Data de emissão | Datepicker | Sim | Data atual |
| Nº do documento | Input text | Não | Texto livre |
| Histórico | Textarea | Sim | Descrição da conta |
| Categoria | Select | Não | Lista de categorias |
| Ocorrência | Select | Sim | Única, Semanal, Quinzenal, Mensal, etc. |

## Formulário de Inclusão/Edição - Guia: Competência

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Competência | Datepicker (month/year) | Não | Mês e ano atual |

## Formulário de Inclusão/Edição - Guia: Anexos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Procurar arquivo | File upload | Não | Limite de 2MB |

## Formulário de Inclusão/Edição - Guia: Marcadores

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Marcador | Input text | Não | Separados por vírgula ou tab |

## Formulário de Pagamento

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data de pagamento | Datepicker | Sim | Data atual |
| Valor pago | Input number | Sim | Valor pendente da conta |
| Juros | Input number | Não | Formato monetário |
| Multa | Input number | Não | Formato monetário |
| Desconto | Input number | Não | Formato monetário |
| Conta | Select | Sim | Lista de contas disponíveis |
| Forma de pagamento | Select | Sim | Lista de formas de pagamento |
| Observações | Textarea | Não | Texto livre |

## Filtros Avançados

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Date range picker | Não | Últimos 30 dias |
| Status | Checkbox group | Não | Em aberto, Pagas, Atrasadas, etc. |
| Fornecedor | Autocomplete | Não | Pesquisa por nome |
| Categoria | Select | Não | Lista de categorias |
| Forma de pagamento | Select | Não | Lista de formas de pagamento |
| Valor mínimo | Input number | Não | Formato monetário |
| Valor máximo | Input number | Não | Formato monetário |
| Nº documento | Input text | Não | Texto livre |
| Histórico | Input text | Não | Texto para busca |
| Marcadores | Multiselect | Não | Lista de marcadores |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a conta a pagar |
| Cancelar | Button | Cancela a operação atual |
| Excluir | Button | Remove a conta selecionada |
| Editar | Button | Abre formulário de edição |
| Pagar | Button | Abre formulário de pagamento |
| Duplicar | Button | Cria cópia da conta |
| Imprimir | Button | Imprime detalhes da conta |
