# Formulário: Notas de Entrada

## Filtros e Controles Principais (Listagem)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente ou número" |
| Período | Dropdown | Não | Últimos 30 dias (padrão), Hoje, Ontem, Esta semana, etc. |
| Tipo de data | Dropdown | Não | Data de emissão (padrão), Data de entrada |
| Filtros | Button/Modal | Não | Abre modal com filtros adicionais |
| Limpar filtros | Button | Não | Remove todos os filtros aplicados |
| Status | Toggle buttons | Não | Todas, Pendentes, Registradas, Emitidas, Canceladas |

## Botões de Ação (Listagem)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Importar XML da NFe | Button | Abre formulário para importação de XML |
| Incluir nota fiscal | Button | Abre formulário para nova nota fiscal |
| Mais ações | Dropdown button | Opções adicionais (exportar, importar, etc.) |
| Alterar ambiente | Button | Alterna entre ambiente de produção e testes |

## Tabela de Notas Fiscais (Listagem)

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Checkbox | Checkbox | Seleção de múltiplas notas |
| Número | Column | Número da nota fiscal |
| Série | Column | Série da nota fiscal |
| Data de emissão | Column | Data de emissão da nota |
| Data de entrada | Column | Data de entrada da nota |
| Fornecedor/Cliente | Column | Nome do fornecedor ou cliente |
| Valor | Column | Valor total da nota |
| Status | Column | Situação atual da nota |
| Chave de acesso | Column | Chave de acesso da NFe |

## Formulário de Inclusão/Edição de Nota Fiscal

### Dados da Nota

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de Entrada | Select | Sim | Emissão própria, Importação, Emitida por terceiros, CT-e emitido por terceiros, XML de NFe |
| Série | Input text | Sim | Série da nota fiscal |
| Número | Input text | Sim | Número da nota fiscal |
| Data emissão | Datepicker | Sim | Data de emissão (dd/mm/aaaa) |
| Hora emissão | Timepicker | Sim | Hora de emissão (hh:mm:ss) |
| Natureza da operação | Input text | Sim | Descrição da natureza da operação |
| Data entrada | Datepicker | Sim | Data de entrada (dd/mm/aaaa) |
| Hora entrada | Timepicker | Sim | Hora de entrada (hh:mm:ss) |
| Finalidade | Select | Sim | NF-e normal, NF-e complementar, NF-e de ajuste, Devolução, Devolução (cupom fiscal), NFe com chave de acesso referenciada |
| Código de regime tributário | Select | Sim | Simples nacional, Simples nacional - excesso de sublimite, Regime normal, Microempreendedor Individual (MEI) |
| Consumidor final | Select | Sim | Selecione, Sim, Não |
| Intermediador | Button/Select | Não | Sem intermediador (padrão), Com intermediador |

### Dados do Remetente

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome | Input text/Search | Sim | Pesquisa pelas iniciais do nome do destinatário |
| Ver últimas compras | Button | Não | Exibe histórico de compras do fornecedor |
| Tipo de pessoa | Select | Sim | Jurídica, Física, Estrangeiro, Estrangeiro no Brasil |
| Contribuinte | Select | Não | Não informado, Contribuinte ICMS, Contribuinte isento de Inscrição, Não Contribuinte |
| CNPJ/CPF | Input text | Sim | Máscara conforme tipo de pessoa |
| Consultar na receita federal | Button | Não | Consulta dados na Receita Federal |
| Insc. Estadual | Input text | Condicional | Obrigatório para contribuintes |
| CEP | Input text | Sim | Máscara: XXXXX-XXX |
| Buscar dados do CEP | Button | Não | Preenche endereço automaticamente |
| Cidade | Input text | Sim | Nome da cidade |
| UF | Select | Sim | Lista de estados brasileiros |
| Endereço | Input text | Sim | Endereço completo |

### Itens da Nota

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa de item | Input text | Não | Pesquisa por descrição, código (SKU) ou GTIN |
| Adicionar item | Button | Não | Adiciona item à nota fiscal |
| Busca avançada de itens | Button | Não | Abre modal de busca avançada |

### Tabela de Itens

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Item | Column | Descrição do produto |
| Cód (SKU) | Column | Código interno do produto |
| GTIN/EAN | Column | Código de barras do produto |
| NCM | Column | Código NCM do produto |
| CFOP | Column | Código Fiscal de Operações |
| CST | Column | Código de Situação Tributária |
| Qtde | Column/Input | Quantidade recebida |
| UN | Column | Unidade de medida |
| Valor unitário | Column/Input | Preço unitário |
| Desconto | Column/Input | Valor do desconto |
| Valor total | Column | Valor total do item |
| Ações | Column | Botões para editar/remover item |

### Totais da Nota

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Base de cálculo ICMS | Input text | Automático | Base para cálculo do ICMS |
| Valor do ICMS | Input text | Automático | Valor total do ICMS |
| Base de cálculo ICMS ST | Input text | Automático | Base para cálculo do ICMS ST |
| Valor do ICMS ST | Input text | Automático | Valor total do ICMS ST |
| Valor do IPI | Input text | Automático | Valor total do IPI |
| Valor do PIS | Input text | Automático | Valor total do PIS |
| Valor do COFINS | Input text | Automático | Valor total do COFINS |
| Valor do frete | Input text | Não | Valor do frete |
| Valor do seguro | Input text | Não | Valor do seguro |
| Outras despesas | Input text | Não | Valor de outras despesas |
| Valor total | Input text | Automático | Valor total da nota fiscal |

### Transporte

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Modalidade do frete | Select | Sim | Por conta do emitente, Por conta do destinatário, Por conta de terceiros, Sem frete |
| Transportadora | Select/Search | Condicional | Obrigatório se houver frete |
| Placa do veículo | Input text | Não | Placa do veículo de transporte |
| UF da placa | Select | Condicional | Obrigatório se informada a placa |
| Volumes | Input number | Não | Quantidade de volumes |
| Espécie | Input text | Não | Tipo de embalagem |
| Peso bruto | Input number | Não | Peso bruto total |
| Peso líquido | Input number | Não | Peso líquido total |

## Formulário de Importação de XML

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Arquivo XML | File upload | Sim | Arquivo XML da NFe |
| Chave de acesso | Input text | Alternativo | Chave de acesso da NFe |
| Depósito | Select | Sim | Depósito de destino dos produtos |
| Vincular a pedido | Select | Não | Pedido de compra relacionado |
| Atualizar preços | Checkbox | Não | Atualiza preços dos produtos |
| Atualizar NCM | Checkbox | Não | Atualiza códigos NCM dos produtos |

## Botões de Ação (Formulário)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a nota fiscal |
| Cancelar | Button | Cancela a criação/edição da nota |
