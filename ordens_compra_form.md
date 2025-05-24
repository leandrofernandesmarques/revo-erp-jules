# Formulário: Ordens de Compra

## Filtros e Controles Principais (Listagem)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por fornecedor, nº do pedido ou ordem de..." |
| Por período | Button/Modal | Não | Abre seletor de período para filtrar |
| Status | Toggle buttons | Não | Todos, Em aberto, Em andamento, Atendidas, Canceladas |

## Botões de Ação (Listagem)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Imprimir | Button | Imprime ordens de compra selecionadas |
| Incluir ordem de compra | Button | Abre formulário para nova ordem |
| Mais ações | Dropdown button | Opções adicionais (exportar, importar, etc.) |

## Tabela de Ordens de Compra (Listagem)

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox | Checkbox | Seleção de múltiplas ordens |
| Número | Column | Número de identificação da ordem |
| Data | Column | Data de criação da ordem |
| Previsto | Column | Data prevista de entrega |
| Fornecedor | Column | Nome do fornecedor |
| Total | Column | Valor total da ordem |
| Marcadores | Column | Etiquetas/status visuais |
| Integrações | Column | Indicadores de integração |

## Formulário de Inclusão/Edição de Ordem de Compra

### Dados do Fornecedor

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Fornecedor | Input text/Search | Sim | Pesquisa pelas iniciais do nome do fornecedor |
| Dados do fornecedor | Button | Não | Exibe detalhes do fornecedor selecionado |
| Ver últimas compras | Button | Não | Exibe histórico de compras do fornecedor |
| Pessoas de contato | Button | Não | Exibe contatos do fornecedor |
| Número | Input text | Sim | Número de controle do pedido |

### Itens da Compra

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa de item | Input text | Não | Pesquisa por descrição, código (SKU) ou GTIN |
| Adicionar item | Button | Não | Adiciona item à ordem de compra |
| Busca avançada de itens | Button | Não | Abre modal de busca avançada |

### Tabela de Itens

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Item | Column | Descrição do produto |
| Cód (SKU) | Column | Código interno do produto |
| GTIN/EAN | Column | Código de barras do produto |
| Qtde | Column/Input | Quantidade solicitada |
| UN | Column | Unidade de medida |
| Preço un | Column/Input | Preço unitário |
| IPI % | Column/Input | Percentual de IPI |
| Preço total | Column | Valor total do item |
| Ações | Column | Botões para editar/remover item |

### Totais da Compra

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nº de itens | Input text | Automático | Quantidade de itens na ordem |
| Soma das qtdes | Input text | Automático | Soma das quantidades de todos os itens |
| Total dos produtos | Input text | Automático | Subtotal dos produtos sem desconto |
| Desconto | Input text | Não | Valor fixo ou percentual (Ex: 3,00 ou 10%) |
| Frete | Input text | Não | Valor do frete |
| Total do IPI | Input text | Automático | Soma dos valores de IPI |
| Total ICMS ST | Input text | Automático | Soma dos valores de ICMS ST |
| Total geral | Input text | Automático | Valor total da ordem de compra |

### Detalhes da Compra

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nº no fornecedor | Input text | Não | Número da ordem no sistema do fornecedor |
| Data da compra | Datepicker | Sim | Data de emissão da ordem (dd/mm/aaaa) |
| Data prevista | Datepicker | Não | Data prevista de entrega (dd/mm/aaaa) |

### Campos Adicionais (Abas)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Observações | Textarea | Não | Observações gerais sobre a ordem |
| Forma de pagamento | Select | Não | Formas de pagamento disponíveis |
| Condição de pagamento | Select | Não | Condições de pagamento disponíveis |
| Depósito | Select | Não | Depósito de destino dos produtos |
| Transportadora | Select | Não | Transportadora para entrega |

## Botões de Ação (Formulário)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a ordem de compra |
| Cancelar | Button | Cancela a criação/edição da ordem |

## Formulário de Recebimento Parcial

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Item | Label | N/A | Nome do item recebido |
| Quantidade pedida | Label | N/A | Quantidade original solicitada |
| Quantidade a receber | Input number | Sim | Quantidade sendo recebida |
| Data de recebimento | Datepicker | Sim | Data do recebimento parcial |
| Observação | Textarea | Não | Observações sobre o recebimento |
