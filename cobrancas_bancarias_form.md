# Formulário: Cobranças Bancárias

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por nome" |
| Por banco | Button | Não | Filtro por instituição bancária |
| Por período | Button | Não | Filtro por período de tempo |
| Incluir remessa | Button | Não | Abre formulário de nova remessa |

## Abas de Navegação

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Remessas | Tab | Exibe lista de remessas bancárias |
| Retornos bancários | Tab | Exibe lista de retornos bancários |

## Formulário de Inclusão de Remessa - Dados da remessa

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Banco ou gateway | Select | Sim | Lista de bancos/gateways disponíveis |
| Incluir títulos sem portador | Checkbox | Não | Desativado por padrão |
| Incluir títulos cancelados | Checkbox | Não | Desativado por padrão |

## Filtros de Período para Títulos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Por período | Tab | Não | Filtro geral de período |
| Por vencimento | Tab | Não | Filtro por data de vencimento |
| Por emissão | Tab | Não | Filtro por data de emissão |

## Opções de Filtro de Vencimento

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Sem filtro | Button | Não | Remove filtros de vencimento |
| No dia | Button | Não | Filtra títulos com vencimento no dia atual |
| Na semana | Button | Não | Filtra títulos com vencimento na semana atual |
| No mês | Button | Não | Filtra títulos com vencimento no mês atual |
| No intervalo | Button | Não | Permite definir intervalo personalizado |

## Tabela de Títulos para Registro

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox seleção | Checkbox | Seleciona título para inclusão na remessa |
| Cliente | Column | Nome do cliente |
| Emissão | Column | Data de emissão do título |
| Vencimento | Column | Data de vencimento do título |
| Histórico | Column | Descrição do título |
| Valor | Column | Valor do título (R$) |

## Resumo da Remessa

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Número de títulos | Text display | Não | Contagem automática de títulos selecionados |
| Valor total dos títulos | Text display | Não | Soma automática dos valores dos títulos selecionados |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a remessa bancária |
| Cancelar | Button | Cancela a operação atual |

## Tabela de Remessas (Listagem Principal)

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Número | Column | Número identificador da remessa |
| Data | Column | Data de criação da remessa |
| Banco | Column | Instituição bancária da remessa |
| Títulos | Column | Quantidade de títulos na remessa |
| Valor | Column | Valor total da remessa (R$) |
| Situação | Column | Status atual da remessa |
| Ações | Button group | Botões para visualizar, baixar e excluir |

## Tabela de Retornos Bancários

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Número | Column | Número identificador do retorno |
| Data | Column | Data de recebimento do retorno |
| Banco | Column | Instituição bancária do retorno |
| Títulos | Column | Quantidade de títulos no retorno |
| Valor | Column | Valor total do retorno (R$) |
| Situação | Column | Status atual do retorno |
| Ações | Button group | Botões para visualizar e excluir |
