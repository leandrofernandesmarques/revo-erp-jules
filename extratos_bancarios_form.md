# Formulário: Extratos Bancários

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por nome" |
| Por período | Button | Não | Filtro por período de tempo |
| Importar extrato bancário | Button | Não | Abre formulário de importação |
| Conhecer Conta Digital | Button | Não | Redireciona para informações da Conta Digital |

## Formulário de Importação de Extrato - Importação do extrato OFX

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Selecione a conta bancária | Select | Sim | Lista de contas bancárias disponíveis |
| Procurar arquivo | File upload | Sim | Formato .ofx, limite de 2MB |
| Fechar | Button | Não | Fecha o modal de importação |
| Cancelar | Button | Não | Cancela a operação atual |

## Tabela de Extratos Bancários (Listagem Principal)

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Data | Column | Data da transação |
| Descrição | Column | Descrição da transação |
| Valor | Column | Valor da transação (R$) |
| Saldo | Column | Saldo após a transação (R$) |
| Conta | Column | Conta bancária relacionada |
| Conciliado | Column | Status de conciliação |
| Ações | Button group | Botões para editar, conciliar e excluir |

## Formulário de Conciliação

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo | Select | Sim | Receita ou Despesa |
| Conta financeira | Select | Sim | Lista de contas financeiras |
| Categoria | Select | Não | Lista de categorias financeiras |
| Histórico | Input text | Sim | Descrição da transação |
| Valor | Input number | Sim | Valor da transação (R$) |
| Data | Datepicker | Sim | Data da transação |
| Conciliar | Button | Não | Confirma a conciliação |
| Cancelar | Button | Não | Cancela a operação atual |

## Filtros Avançados

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Date range picker | Não | Últimos 30 dias |
| Conta bancária | Select | Não | Lista de contas bancárias |
| Status | Select | Não | Todos, Conciliados, Não conciliados |
| Tipo | Select | Não | Todos, Receitas, Despesas |
| Valor mínimo | Input number | Não | Formato monetário |
| Valor máximo | Input number | Não | Formato monetário |
| Descrição | Input text | Não | Texto para busca |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Importar extrato bancário | Button | Inicia processo de importação |
| Conciliar | Button | Abre formulário de conciliação |
| Editar | Button | Permite editar transação |
| Excluir | Button | Remove transação selecionada |
| Filtrar | Button | Aplica filtros selecionados |
| Limpar filtros | Button | Remove filtros aplicados |

## Seção Informativa

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Deixe de fazer inúmeros uploads de extratos bancários | Text display | Mensagem promocional |
| Com Conta Digital | Text display | Informação sobre funcionalidade |
| Novo | Badge | Indicador de nova funcionalidade |
