# Formulário: Relatórios de Suprimentos

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Outros relatórios | Button | Acessa relatórios adicionais |
| Controle de Estoques | Tab/Button | Filtra relatórios de controle de estoques |
| Notas de Entrada | Tab/Button | Filtra relatórios de notas de entrada |
| Ordens de Compra | Tab/Button | Filtra relatórios de ordens de compra |

## Relatório: Entradas e Saídas de Estoque

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Datepicker (range) | Sim | Data inicial e final (padrão: mês atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Produto | Select/Search | Não | Pesquisa de produtos específicos |
| Tipo de movimentação | Select | Não | Entrada, Saída, Transferência, Ajuste |
| Motivo | Select | Não | Lista de motivos cadastrados |
| Agrupar por | Select | Não | Produto, Data, Tipo de movimentação, Motivo |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Saldos em Estoque

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data de referência | Datepicker | Sim | Data para cálculo do saldo (padrão: data atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Categoria | Select | Não | Lista de categorias de produtos |
| Mostrar produtos | Select | Sim | Todos, Com estoque, Sem estoque |
| Ordenar por | Select | Sim | Nome, Código, Estoque (crescente/decrescente) |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Produtos com Maior Circulação

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Datepicker (range) | Sim | Data inicial e final (padrão: mês atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Tipo de movimentação | Select | Sim | Entrada, Saída, Ambos (padrão: Saída) |
| Quantidade de produtos | Input number | Sim | Número de produtos a exibir (padrão: 10) |
| Ordenar por | Select | Sim | Quantidade, Valor (crescente/decrescente) |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Produtos sem Movimentação

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Datepicker (range) | Sim | Data inicial e final (padrão: mês atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Categoria | Select | Não | Lista de categorias de produtos |
| Considerar apenas | Select | Não | Todos, Produtos ativos, Produtos inativos |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Produtos Abaixo do Estoque Mínimo

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Categoria | Select | Não | Lista de categorias de produtos |
| Ordenar por | Select | Sim | Nome, Código, Estoque atual (crescente/decrescente) |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Visão Financeira do Estoque

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data de referência | Datepicker | Sim | Data para cálculo do valor (padrão: data atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Categoria | Select | Não | Lista de categorias de produtos |
| Agrupar por | Select | Não | Nenhum, Categoria, Depósito |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Movimentação de um Produto

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Produto | Select/Search | Sim | Pesquisa de produto específico |
| Período | Datepicker (range) | Sim | Data inicial e final (padrão: mês atual) |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Tipo de movimentação | Select | Não | Entrada, Saída, Transferência, Ajuste |
| Incluir gráfico | Checkbox | Não | Inclui gráfico de evolução do estoque |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Relatório: Lotes e Validades de Produtos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Produto | Select/Search | Não | Pesquisa de produto específico |
| Depósito | Select | Não | Lista de depósitos cadastrados |
| Status de validade | Select | Não | Todos, Vencidos, A vencer em X dias |
| Dias para vencimento | Input number | Condicional | Obrigatório se "A vencer em X dias" selecionado |
| Formato | Radio buttons | Sim | PDF, Excel, CSV (padrão: PDF) |

## Botões de Ação (Comuns a todos os relatórios)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Gerar relatório | Button | Processa e exibe o relatório com os filtros selecionados |
| Limpar filtros | Button | Remove todos os filtros aplicados |
| Salvar configuração | Button | Salva a configuração atual de filtros para uso futuro |
| Exportar | Button | Exporta o relatório no formato selecionado |
