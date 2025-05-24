# Formulário: Contas a Receber

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente, nº no banco ou nº doc" |
| Por período | Dropdown | Não | Padrão: "Últimos 30 dias" |
| Por meio de recebimento | Dropdown | Não | Lista de meios de recebimento |
| Filtros | Button | Não | Abre painel de filtros avançados |
| Limpar filtros | Button | Não | Remove filtros aplicados |
| Imprimir | Button | Não | Imprime relatório de contas a receber |
| Gerenciar recebimentos | Button | Não | Abre painel de gerenciamento |
| Incluir conta a receber | Button | Não | Abre formulário de nova conta |
| Mais ações | Dropdown button | Não | Opções adicionais |

## Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Em aberto | Tab | Exibe apenas contas em aberto |
| Emitidas | Tab | Exibe apenas contas emitidas |
| Recebidas | Tab | Exibe apenas contas recebidas |
| Atrasadas | Tab | Exibe apenas contas atrasadas |
| Canceladas | Tab | Exibe apenas contas canceladas |

## Tabela de Contas a Receber

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox seleção | Checkbox | Seleciona conta para ações em massa |
| Cliente | Column | Nome do cliente |
| Histórico | Column | Descrição da conta |
| Vencimento | Column | Data de vencimento |
| Valor | Column | Valor da conta (R$) |
| Saldo | Column | Saldo pendente (R$) |
| Valor líquido | Column | Valor líquido (R$) |
| Recebido | Column | Valor já recebido (R$) |
| Data Emissão | Column | Data de emissão da conta |
| Marcadores | Column | Etiquetas visuais |
| Ações | Button group | Botões de edição, recebimento e exclusão |

## Formulário de Inclusão/Edição - Guia: Dados da conta

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Cliente | Autocomplete | Sim | Pesquisa por iniciais do nome |
| Vencimento | Datepicker | Sim | Data futura |
| Valor | Input number | Sim | Formato monetário (R$) |
| Data emissão | Datepicker | Sim | Data atual |
| Nº documento | Input text | Não | Texto livre |
| Histórico | Textarea | Sim | Descrição da conta |
| Categoria | Select | Não | Lista de categorias financeiras |
| Forma de recebimento | Select | Sim | Lista de formas de recebimento |
| Link de pagamento | Button | Não | Gera link para pagamento digital |
| Ocorrência | Select | Sim | Única, Semanal, Quinzenal, Mensal, etc. |

## Formulário de Inclusão/Edição - Guia: Anexos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Procurar arquivo | File upload | Não | Limite de 2MB |

## Formulário de Inclusão/Edição - Guia: Marcadores

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Marcador | Input text | Não | Separados por vírgula ou tab |

## Formulário de Recebimento

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data de recebimento | Datepicker | Sim | Data atual |
| Valor recebido | Input number | Sim | Valor pendente da conta |
| Juros | Input number | Não | Formato monetário |
| Multa | Input number | Não | Formato monetário |
| Desconto | Input number | Não | Formato monetário |
| Conta | Select | Sim | Lista de contas disponíveis |
| Forma de recebimento | Select | Sim | Lista de formas de recebimento |
| Observações | Textarea | Não | Texto livre |

## Filtros Avançados

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Date range picker | Não | Últimos 30 dias |
| Status | Checkbox group | Não | Em aberto, Recebidas, Atrasadas, etc. |
| Cliente | Autocomplete | Não | Pesquisa por nome |
| Categoria | Select | Não | Lista de categorias |
| Forma de recebimento | Select | Não | Lista de formas de recebimento |
| Valor mínimo | Input number | Não | Formato monetário |
| Valor máximo | Input number | Não | Formato monetário |
| Nº documento | Input text | Não | Texto livre |
| Histórico | Input text | Não | Texto para busca |
| Marcadores | Multiselect | Não | Lista de marcadores |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a conta a receber |
| Cancelar | Button | Cancela a operação atual |
| Excluir | Button | Remove a conta selecionada |
| Editar | Button | Abre formulário de edição |
| Receber | Button | Abre formulário de recebimento |
| Duplicar | Button | Cria cópia da conta |
| Imprimir | Button | Imprime detalhes da conta |
