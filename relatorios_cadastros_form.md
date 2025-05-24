# Formulário: Relatórios de Cadastros

## Relatório de Preços dos Produtos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Filtro por Produto | Input text/Select | Não | Permite pesquisar produtos específicos |
| Filtro por Tag | Select | Não | Permite agrupar por tags cadastradas |
| Período | Datepicker | Não | Permite selecionar período para análise |
| Formato de Saída | Select | Sim | PDF, Excel, CSV |

## Outros Relatórios Disponíveis

### Relatórios de Produtos

| Nome do Relatório | Descrição | Filtros Disponíveis |
|-------------------|-----------|---------------------|
| Relatório de Estoque | Situação atual do estoque | Produto, Depósito, Situação |
| Relatório de Movimentação | Histórico de movimentações | Período, Produto, Tipo de Movimentação |
| Relatório de Produtos | Lista completa de produtos | Categoria, Situação, Tipo |

### Relatórios de Clientes e Fornecedores

| Nome do Relatório | Descrição | Filtros Disponíveis |
|-------------------|-----------|---------------------|
| Relatório de Clientes | Lista de clientes cadastrados | Tipo, Situação, Região |
| Relatório de Fornecedores | Lista de fornecedores | Tipo, Situação, Categoria |
| Relatório de Contatos | Lista de contatos | Tipo, Origem, Situação |

### Relatórios de Vendedores

| Nome do Relatório | Descrição | Filtros Disponíveis |
|-------------------|-----------|---------------------|
| Relatório de Vendedores | Lista de vendedores | Situação, Região |
| Relatório de Desempenho | Desempenho de vendas por vendedor | Período, Vendedor, Produto |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Outros Relatórios | Button | Acessa relatórios adicionais |
| Gerar Relatório | Button | Processa e exibe o relatório selecionado |
| Exportar | Button | Exporta o relatório no formato selecionado |
