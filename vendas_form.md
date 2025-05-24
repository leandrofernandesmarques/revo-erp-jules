# Formulário: Módulo de Vendas

## Submódulo: Pedidos de Venda

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente ou número" |
| Últimos 30 dias | Button | Não | Filtro de período |
| Filtros | Button | Não | Abre filtros avançados |
| Limpar filtros | Button | Não | Remove filtros aplicados |
| Imprimir | Button | Não | Imprime pedidos selecionados |
| Incluir pedido | Button | Não | Abre formulário de inclusão |
| Mais ações | Dropdown | Não | Opções adicionais |

### Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Todos | Tab | Exibe todos os pedidos |
| Em aberto | Tab | Exibe pedidos em aberto |
| Aprovado | Tab | Exibe pedidos aprovados |
| Preparando envio | Tab | Exibe pedidos em preparação |
| Faturado | Tab | Exibe pedidos faturados |
| Mais | Dropdown | Outras situações de pedidos |

### Formulário de Inclusão/Edição - Dados Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Natureza da operação | Input text | Sim | Ex: "Venda de mercadorias" |
| Número | Input text | Não | Gerado automaticamente |
| Cliente | Input text | Sim | Autocomplete com busca |
| Dados do cliente | Button | Não | Abre detalhes do cliente |
| Ver últimas vendas | Button | Não | Histórico de vendas do cliente |
| Limite de crédito | Button | Não | Informações de crédito |
| Vendedor | Input text | Não | Nome do vendedor responsável |
| Endereço de entrega diferente | Checkbox | Não | Desativado por padrão |

### Formulário de Inclusão/Edição - Itens de produtos ou serviços

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa de item | Input text | Sim | Placeholder: "Pesquise por descrição, código (SKU) ou gtin" |
| Quantidade | Input number | Sim | Valor maior que zero |
| Valor unitário | Input number | Sim | Formato monetário (R$) |
| Desconto | Input number | Não | Valor ou percentual |
| Subtotal | Input number | Não | Calculado automaticamente |
| Adicionar outro item | Button | Não | Adiciona nova linha de item |
| Busca avançada de itens | Button | Não | Abre busca com mais filtros |

### Formulário de Inclusão/Edição - Aba Comissões

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Vendedor | Input text | Não | Nome do vendedor |
| Percentual | Input number | Não | Formato percentual (%) |
| Valor | Input number | Não | Formato monetário (R$) |

### Formulário de Inclusão/Edição - Aba Impostos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| MVA % | Input number | Não | Formato percentual (%) |
| ICMS ST % | Input number | Não | Formato percentual (%) |
| ICMS ST R$ | Input number | Não | Formato monetário (R$) |
| FCP ST % | Input number | Não | Formato percentual (%) |
| FCP ST R$ | Input number | Não | Formato monetário (R$) |
| IPI % | Input number | Não | Formato percentual (%) |
| IPI R$ | Input number | Não | Formato monetário (R$) |

### Totalizadores do Pedido

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nº de itens | Input number | Não | Calculado automaticamente |
| Soma das qtdes | Input number | Não | Calculado automaticamente |
| Peso Bruto | Input number | Não | Formato decimal (kg) |
| Peso Líquido | Input number | Não | Formato decimal (kg) |
| Total produtos | Input number | Não | Calculado automaticamente |
| Valor IPI | Input number | Não | Calculado automaticamente |
| Valor ICMS ST + FCP ST | Input number | Não | Calculado automaticamente |
| Total da venda | Input number | Não | Calculado automaticamente |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva o pedido |
| Cancelar | Button | Cancela a operação |

## Submódulo: CRM

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por contato, CPF/CNPJ ou descrição" |
| Lista | Tab | Não | Visualização em lista |
| Por estágio | Tab | Não | Visualização por estágio |
| Por período | Tab | Não | Visualização por período |
| Filtros | Button | Não | Abre filtros avançados |
| Incluir assunto | Button | Não | Abre formulário de inclusão |

### Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Todos | Tab | Exibe todos os assuntos |
| Com ações pendentes | Tab | Exibe assuntos com pendências |
| Encerrados | Tab | Exibe assuntos encerrados |
| Com estrela | Tab | Exibe assuntos marcados com estrela |
| Arquivados | Tab | Exibe assuntos arquivados |

### Formulário de Inclusão/Edição

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Cliente | Input text | Sim | Autocomplete com busca |
| Título do assunto | Input text | Sim | Descrição do assunto |
| Novo contato | Input text | Não | Nome do novo contato |
| Telefone | Input text | Não | Formato: (99) 99999-9999 |
| Email | Input text | Não | Formato: email@dominio.com |
| Cargo | Input text | Não | Cargo do contato |
| Estágio do assunto | Select | Sim | Prospecção, Contato realizado, Proposta apresentada, Negociação, Encerrado |
| Mais detalhes | Button | Não | Exibe campos adicionais |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva o assunto |
| Cancelar | Button | Cancela a operação |

## Submódulo: Painel de Automações

### Configurações de Automação

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Lançar saída de estoque | Select | Não | Selecionar ação inicial, Ao autorizar a nota fiscal, Ao salvar a nota fiscal, Ao salvar o pedido, Ao marcar pedido como enviado |
| Emitir Nota Fiscal Eletrônica (NFe) | Select | Não | Selecionar ação inicial, Ao aprovar o pedido |
| Enviar para expedição | Select | Não | Selecionar ação inicial, Ao autorizar a nota fiscal, Ao salvar a nota fiscal, Ao salvar o pedido, Ao aprovar o pedido |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar automações | Button | Salva as configurações de automação |

## Submódulo: PDV

### Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Abrir caixa | Button | Sim | Inicia operação de caixa |
| Ver detalhes do caixa | Link | Não | Exibe detalhes do caixa atual |

### Formulário de Abertura de Caixa

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Valor disponível em caixa | Input number | Sim | Formato monetário (R$) |
| Imprimir comprovante de abertura de caixa | Checkbox | Não | Desativado por padrão |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Abrir caixa | Button | Confirma abertura do caixa |
| Cancelar | Button | Cancela a operação |

## Submódulo: Propostas Comerciais

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente ou número" |
| Por período | Button | Não | Filtro de período |
| Filtros | Button | Não | Abre filtros avançados |
| Imprimir | Button | Não | Imprime propostas selecionadas |
| Incluir proposta | Button | Não | Abre formulário de inclusão |
| Mais ações | Dropdown | Não | Opções adicionais |

### Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Todas | Tab | Exibe todas as propostas |
| Em aberto | Tab | Exibe propostas em aberto |
| Rascunhos | Tab | Exibe propostas em rascunho |
| Pendentes | Tab | Exibe propostas pendentes |
| Aguardando | Tab | Exibe propostas aguardando |
| Aprovadas | Tab | Exibe propostas aprovadas |
| Mais | Dropdown | Outras situações de propostas |

### Formulário de Inclusão/Edição - Dados Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Natureza da operação | Input text | Sim | Ex: "Venda de mercadorias" |
| Cliente | Input text | Sim | Autocomplete com busca |
| Dados do cliente | Button | Não | Abre detalhes do cliente |
| Ver últimas vendas | Button | Não | Histórico de vendas do cliente |
| Pessoas de contato | Button | Não | Lista contatos do cliente |
| Aos cuidados de | Input text | Não | Nome do contato |
| Endereço de entrega diferente | Checkbox | Não | Desativado por padrão |
| Introdução | Textarea | Não | Texto introdutório da proposta |
| Nº Proposta | Input text | Não | Gerado automaticamente |
| Vendedor | Input text | Não | Nome do vendedor responsável |
| Data | Datepicker | Sim | Data atual |
| Data do Próximo Contato | Datepicker | Não | Data futura |

### Formulário de Inclusão/Edição - Itens de produto ou serviço

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa de item | Input text | Sim | Placeholder: "Pesquise por descrição, código (SKU) ou gtin" |
| Código (SKU) | Input text | Não | Código do produto |
| Quantidade | Input number | Sim | Valor maior que zero |
| UN | Input text | Não | Unidade de medida |
| Preço unitário | Input number | Sim | Formato monetário (R$) |
| Preço total | Input number | Não | Calculado automaticamente |

### Formulário de Inclusão/Edição - Descrições complementares

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Código (SKU) | Input text | Não | Código do produto |
| NCM | Input text | Não | Código NCM |
| Descrição complementar | Textarea | Não | Descrição adicional do item |

### Formulário de Inclusão/Edição - Impostos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| MVA % | Input number | Não | Formato percentual (%) |
| ICMS ST % | Input number | Não | Formato percentual (%) |
| ICMS ST R$ | Input number | Não | Formato monetário (R$) |
| FCP ST % | Input number | Não | Formato percentual (%) |
| FCP ST R$ | Input number | Não | Formato monetário (R$) |
| IPI % | Input number | Não | Formato percentual (%) |
| IPI R$ | Input number | Não | Formato monetário (R$) |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a proposta |
| Cancelar | Button | Cancela a operação |

## Submódulo: Notas Fiscais

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise pelo nome do cliente" |
| Cliente | Button | Não | Filtro por cliente |
| Últimos 30 dias | Button | Não | Filtro de período |
| Data de emissão | Button | Não | Filtro por data de emissão |
| Filtros | Button | Não | Abre filtros avançados |
| Limpar filtros | Button | Não | Remove filtros aplicados |
| Imprimir DANFEs | Button | Não | Imprime DANFEs selecionadas |
| Autorizar pendentes | Button | Não | Autoriza notas pendentes |
| Incluir nota fiscal | Button | Não | Abre formulário de inclusão |
| Mais ações | Dropdown | Não | Opções adicionais |
| Alterar ambiente | Button | Não | Alterna entre ambiente de produção e testes |

### Abas de Status

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Todas | Tab | Exibe todas as notas |
| Pendentes | Tab | Exibe notas pendentes |
| Emitidas | Tab | Exibe notas emitidas |
| Canceladas | Tab | Exibe notas canceladas |

### Formulário de Inclusão/Edição - Dados Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de Saída | Select | Sim | Emissão própria, Exportação, Emitida por terceiros, XML de NFe |
| Série | Input text | Sim | Número da série |
| Número | Input text | Não | Gerado automaticamente |
| Data emissão | Datepicker | Sim | Data atual |
| Hora emissão | Input time | Sim | Hora atual |
| Natureza da operação | Input text | Sim | Ex: "Venda de mercadorias" |
| Data saída | Datepicker | Não | Data atual ou futura |
| Hora saída | Input time | Não | Hora atual |
| Finalidade | Select | Sim | NF-e normal, NF-e complementar, NF-e de ajuste, Devolução, NFe com cupom referenciado, NFe com chave de acesso referenciada |
| Código de regime tributário | Select | Sim | Simples nacional, Simples nacional - excesso de sublimite, Regime normal, Microempreendedor Individual (MEI) |
| Consumidor final | Select | Sim | Sim, Não |
| Intermediador | Button | Não | Sem intermediador |

### Formulário de Inclusão/Edição - Destinatário

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome | Input text | Sim | Autocomplete com busca |
| Ver últimas vendas | Button | Não | Histórico de vendas do cliente |
| Limite de crédito | Button | Não | Informações de crédito |
| Tipo de pessoa | Select | Sim | Jurídica, Física, Estrangeiro, Estrangeiro no Brasil |
| Contribuinte | Select | Sim | Não informado, Contribuinte ICMS, Contribuinte isento de Inscrição, Não Contribuinte |
| CNPJ | Input text | Sim (se PJ) | Formato: 99.999.999/9999-99 |
| Consultar na receita federal | Button | Não | Consulta dados na Receita |
| Insc. Estadual | Input text | Não | Inscrição Estadual |
| CEP | Input text | Sim | Formato: 99999-999 |
| Buscar dados do CEP | Button | Não | Preenche endereço pelo CEP |
| Cidade | Input text | Sim | Nome da cidade |
| UF | Select | Sim | Lista de estados brasileiros |
| Endereço | Input text | Sim | Logradouro completo |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a nota fiscal |
| Cancelar | Button | Cancela a operação |

## Submódulo: Comissões

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por vendedor ou pedido" |
| Por período | Button | Não | Filtro de período |
| Filtros | Button | Não | Abre filtros avançados |
| Vendedor | Select | Não | Lista de vendedores |
| Status | Select | Não | Todos, Pendentes, Pagas, Canceladas |

### Tabela de Comissões

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Vendedor | Column | Nome do vendedor |
| Pedido | Column | Número do pedido |
| Cliente | Column | Nome do cliente |
| Data | Column | Data da venda |
| Valor da venda | Column | Valor total da venda |
| Percentual | Column | Percentual de comissão |
| Valor da comissão | Column | Valor calculado da comissão |
| Status | Column | Status da comissão |
| Ações | Button group | Botões para pagar, editar e excluir |

## Submódulo: Expedição

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente ou pedido" |
| Por período | Button | Não | Filtro de período |
| Filtros | Button | Não | Abre filtros avançados |
| Transportadora | Select | Não | Lista de transportadoras |
| Status | Select | Não | Todos, Aguardando separação, Em separação, Separado, Enviado |

### Tabela de Expedição

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Pedido | Column | Número do pedido |
| Cliente | Column | Nome do cliente |
| Data | Column | Data do pedido |
| Valor | Column | Valor total do pedido |
| Transportadora | Column | Nome da transportadora |
| Status | Column | Status da expedição |
| Ações | Button group | Botões para separar, enviar e cancelar |

## Submódulo: Devoluções de venda

### Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por cliente ou número" |
| Por período | Button | Não | Filtro de período |
| Filtros | Button | Não | Abre filtros avançados |
| Incluir devolução | Button | Não | Abre formulário de inclusão |

### Tabela de Devoluções

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Número | Column | Número da devolução |
| Cliente | Column | Nome do cliente |
| Data | Column | Data da devolução |
| Valor | Column | Valor total da devolução |
| Status | Column | Status da devolução |
| Ações | Button group | Botões para visualizar, editar e excluir |

## Submódulo: Relatórios

### Relatórios Disponíveis

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Geral | Tab | Relatórios gerais de vendas |
| Vendas por Período | Link | Relatório de vendas por período |
| Vendas por Cliente | Link | Relatório de vendas por cliente |
| Vendas por Produto | Link | Relatório de vendas por produto |
| Vendas por Vendedor | Link | Relatório de vendas por vendedor |
| Ranking de Produtos | Link | Ranking dos produtos mais vendidos |
| Ranking de Clientes | Link | Ranking dos maiores clientes |
| Curva ABC | Link | Análise de curva ABC de produtos |

### Filtros Comuns de Relatórios

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Button group | Sim | Do mês, Intervalo |
| Data inicial | Datepicker | Sim (se Intervalo) | Primeiro dia do mês atual |
| Data final | Datepicker | Sim (se Intervalo) | Último dia do mês atual |
| Cliente | Select | Não | Lista de clientes |
| Vendedor | Select | Não | Lista de vendedores |
| Produto | Select | Não | Lista de produtos |
| Status | Select | Não | Todos, Em aberto, Aprovado, Faturado, etc. |

### Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar | Button | Gera o relatório com os filtros selecionados |
| Exibir filtros | Button | Mostra/oculta os filtros do relatório |
| Download | Button | Baixa o relatório em formato CSV/Excel |
| Compartilhar | Button | Permite compartilhar o relatório |
| Imprimir | Button | Imprime o relatório |
