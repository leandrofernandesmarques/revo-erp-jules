# Estrutura de Páginas Organizacionais - ERP Revo

Este documento detalha a estrutura e organização das principais páginas do ERP Revo para implementação no Figma, seguindo o design system e componentes definidos anteriormente.

## Estrutura Geral do Arquivo Figma

### Organização de Páginas no Figma

1. **Design System**

   - Cores, Tipografia, Espaçamento
   - Componentes Base (Botões, Campos, etc.)
   - Componentes Compostos (Cards, Tabelas, etc.)
   - Ícones e Assets

2. **Templates**

   - Layout Base com Menu Lateral
   - Layout Base sem Menu Lateral
   - Layout de Página de Login
   - Layout de Dashboard
   - Layout de Listagem
   - Layout de Formulário
   - Layout de Visualização Detalhada

3. **Dashboard**

   - Dashboard Principal
   - Dashboard de Vendas
   - Dashboard Financeiro

4. **Cadastros**

   - Listagem de Clientes/Fornecedores
   - Formulário de Cliente/Fornecedor
   - Listagem de Produtos
   - Formulário de Produto
   - Listagem de Serviços
   - Formulário de Serviço

5. **Vendas**

   - Listagem de Pedidos
   - Formulário de Pedido
   - Listagem de Notas Fiscais
   - Visualização de Nota Fiscal
   - Listagem de Propostas Comerciais
   - Formulário de Proposta Comercial

6. **Finanças**

   - Listagem de Contas a Pagar
   - Formulário de Conta a Pagar
   - Listagem de Contas a Receber
   - Formulário de Conta a Receber
   - Extrato Bancário
   - Fluxo de Caixa

7. **Suprimentos**

   - Listagem de Ordens de Compra
   - Formulário de Ordem de Compra
   - Controle de Estoque
   - Movimentações de Estoque

8. **Serviços**

   - Listagem de Ordens de Serviço
   - Formulário de Ordem de Serviço
   - Listagem de Contratos
   - Formulário de Contrato

9. **Ferramentas e Integrações**

   - Listagem de Integrações
   - Configuração de Integração
   - Ferramentas de Backup
   - Ferramentas de Importação

10. **Protótipos**
    - Fluxo de Login
    - Fluxo de Cadastro de Cliente
    - Fluxo de Criação de Pedido
    - Fluxo de Emissão de Nota Fiscal

## Detalhamento das Páginas Principais

### Dashboard Principal

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Dashboard"
- **Área de Filtros**: Componente Barra de Filtros com filtro de período, filtros avançados e atualização
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Visão Geral** (12 colunas):

   - Card com indicadores em formato de ícones
   - 6 indicadores: Pedidos, Vendas E-commerce, Vendas Físicas, Valor Total, NF-e Emitidas, Status de Integração
   - Layout: Flex, wrap, espaçamento uniforme

2. **Cards de Métricas** (4 colunas cada):

   - Total de Vendas: Valor principal + gráfico de linha
   - Ticket Médio: Valor principal + gráfico de linha
   - Pedidos: Valor principal + gráfico de linha

3. **Gráficos** (6 colunas cada):

   - Pedidos por Estado: Mapa do Brasil com tooltip
   - Pedidos por Integrações: Gráfico de barras

4. **Produtos Mais Vendidos** (12 colunas):
   - Tabela com colunas: Produto, Quantidade, Valor Total
   - Paginação na parte inferior

### Listagem de Clientes/Fornecedores

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Clientes e Fornecedores"
- **Área de Filtros**: Componente Barra de Filtros com campo de pesquisa e filtros avançados
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Barra de Ações** (12 colunas):

   - Botão Primário "Novo Cliente/Fornecedor"
   - Botão Secundário "Importar"
   - Botão Terciário "Exportar"
   - Dropdown "Mais Ações"

2. **Tabela de Clientes/Fornecedores** (12 colunas):

   - Colunas: Código, Nome/Razão Social, CPF/CNPJ, Cidade/UF, Telefone, E-mail, Ações
   - Cabeçalho com opções de ordenação
   - Linhas com hover e seleção
   - Coluna de Ações: Ícones de Editar, Excluir, Mais Opções

3. **Paginação** (12 colunas):
   - Componente Paginação
   - Seletor de itens por página
   - Indicador de total de itens

### Formulário de Cliente/Fornecedor

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Novo Cliente" ou "Editar Cliente"
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Abas** (12 colunas):

   - Dados Principais
   - Endereço
   - Contatos
   - Financeiro
   - Observações

2. **Formulário - Dados Principais**:

   - Tipo: Radio Button (Cliente, Fornecedor, Ambos)
   - Pessoa: Radio Button (Física, Jurídica)
   - Nome/Razão Social: Campo de Texto (obrigatório)
   - CPF/CNPJ: Campo de Texto com máscara (obrigatório)
   - RG/IE: Campo de Texto
   - Data de Nascimento/Fundação: DatePicker
   - Telefone: Campo de Texto com máscara
   - Celular: Campo de Texto com máscara
   - E-mail: Campo de Texto tipo email
   - Site: Campo de Texto tipo url

3. **Formulário - Endereço**:

   - CEP: Campo de Texto com máscara e botão de busca
   - Logradouro: Campo de Texto
   - Número: Campo de Texto
   - Complemento: Campo de Texto
   - Bairro: Campo de Texto
   - Cidade: Select
   - UF: Select
   - País: Select

4. **Barra de Ações** (12 colunas):
   - Botão Primário "Salvar"
   - Botão Secundário "Cancelar"
   - Botão Terciário "Excluir" (apenas em edição)

### Listagem de Pedidos

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Pedidos de Venda"
- **Área de Filtros**: Componente Barra de Filtros com campo de pesquisa e filtros avançados
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Barra de Ações** (12 colunas):

   - Botão Primário "Novo Pedido"
   - Botão Secundário "Importar"
   - Botão Terciário "Exportar"
   - Dropdown "Mais Ações"

2. **Indicadores de Status** (12 colunas):

   - Cards pequenos com contadores
   - Status: Em Aberto, Aprovado, Faturado, Cancelado, Total

3. **Tabela de Pedidos** (12 colunas):

   - Colunas: Número, Data, Cliente, Valor Total, Status, Forma de Pagamento, Ações
   - Cabeçalho com opções de ordenação
   - Linhas com hover e seleção
   - Coluna de Status: Badge colorido conforme status
   - Coluna de Ações: Ícones de Editar, Faturar, Cancelar, Mais Opções

4. **Paginação** (12 colunas):
   - Componente Paginação
   - Seletor de itens por página
   - Indicador de total de itens

### Formulário de Pedido

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Novo Pedido" ou "Editar Pedido #123"
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Informações do Pedido** (12 colunas):

   - Data: DatePicker (obrigatório)
   - Cliente: Select com busca (obrigatório)
   - Vendedor: Select
   - Forma de Pagamento: Select
   - Condição de Pagamento: Select
   - Observações: Textarea

2. **Produtos** (12 colunas):

   - Tabela de produtos com colunas: Produto, Quantidade, Valor Unitário, Desconto, Valor Total
   - Botão "Adicionar Produto"
   - Campos editáveis na tabela
   - Cálculo automático de valores

3. **Resumo Financeiro** (4 colunas, alinhado à direita):

   - Subtotal: Texto
   - Desconto: Campo de Texto com opção percentual/valor
   - Frete: Campo de Texto
   - Total: Texto em destaque

4. **Barra de Ações** (12 colunas):
   - Botão Primário "Salvar"
   - Botão Secundário "Cancelar"
   - Botão Terciário "Excluir" (apenas em edição)
   - Botão "Faturar" (apenas em edição)

### Dashboard Financeiro

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Dashboard Financeiro"
- **Área de Filtros**: Componente Barra de Filtros com filtro de período, filtros avançados e atualização
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Cards de Métricas** (4 colunas cada):

   - Saldo Atual: Valor principal + variação percentual
   - Contas a Receber: Valor principal + gráfico de linha
   - Contas a Pagar: Valor principal + gráfico de linha

2. **Fluxo de Caixa** (12 colunas):

   - Gráfico de barras com receitas e despesas
   - Linha de saldo
   - Legenda

3. **Contas a Receber por Vencimento** (6 colunas):

   - Gráfico de pizza com categorias: A vencer, Vencido 1-15 dias, Vencido 16-30 dias, Vencido >30 dias
   - Legenda com valores

4. **Contas a Pagar por Vencimento** (6 colunas):

   - Gráfico de pizza com categorias: A vencer, Vencido 1-15 dias, Vencido 16-30 dias, Vencido >30 dias
   - Legenda com valores

5. **Tabela de Próximos Vencimentos** (12 colunas):
   - Colunas: Data, Descrição, Valor, Tipo (Receber/Pagar), Status
   - Limitada a 5-10 itens
   - Link "Ver todos"

### Controle de Estoque

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Controle de Estoque"
- **Área de Filtros**: Componente Barra de Filtros com campo de pesquisa e filtros avançados
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Indicadores de Estoque** (3 colunas cada):

   - Total de Produtos: Valor numérico
   - Produtos com Estoque Baixo: Valor numérico + alerta
   - Produtos sem Estoque: Valor numérico + alerta
   - Valor Total em Estoque: Valor monetário

2. **Tabela de Produtos** (12 colunas):

   - Colunas: Código, Produto, Estoque Atual, Estoque Mínimo, Estoque Máximo, Valor Unitário, Valor Total, Ações
   - Cabeçalho com opções de ordenação
   - Linhas com hover e seleção
   - Destaque visual para produtos com estoque baixo ou zerado
   - Coluna de Ações: Ícones de Ajustar Estoque, Histórico, Mais Opções

3. **Paginação** (12 colunas):
   - Componente Paginação
   - Seletor de itens por página
   - Indicador de total de itens

### Integrações

**Estrutura**:

- **Menu Lateral**: Componente Menu Lateral (expandido)
- **Cabeçalho**: Componente Cabeçalho com breadcrumbs e título "Integrações"
- **Conteúdo Principal**: Grid de 12 colunas

**Componentes**:

1. **Abas** (12 colunas):

   - Minhas Integrações
   - Adicionar Integração

2. **Minhas Integrações**:

   - Tabela com colunas: Integração, Status, Última Sincronização, Ações
   - Status: Badge colorido (Ativo, Inativo, Erro)
   - Coluna de Ações: Ícones de Configurar, Sincronizar, Desativar/Ativar, Remover

3. **Adicionar Integração**:

   - Campo de pesquisa
   - Categorias de integrações: Marketplaces, E-commerce, Outros
   - Cards de integrações disponíveis:
     - Logo
     - Nome
     - Descrição curta
     - Botão "Instalar"

4. **Modal de Configuração**:
   - Título com nome da integração
   - Campos específicos conforme a integração
   - Botões: Cancelar, Salvar

## Modais e Overlays

### Modal de Confirmação

**Estrutura**:

- **Overlay**: Background semi-transparente
- **Container**: Background branco, border-radius, box-shadow
- **Largura**: 400px

**Componentes**:

1. **Cabeçalho**:

   - Ícone conforme tipo (informação, sucesso, aviso, erro)
   - Título

2. **Conteúdo**:

   - Texto de confirmação

3. **Rodapé**:
   - Botão Secundário "Cancelar"
   - Botão Primário "Confirmar" (ou variação conforme ação)

### Modal de Formulário

**Estrutura**:

- **Overlay**: Background semi-transparente
- **Container**: Background branco, border-radius, box-shadow
- **Largura**: 600px ou 800px

**Componentes**:

1. **Cabeçalho**:

   - Título
   - Botão de fechar (X)

2. **Conteúdo**:

   - Campos de formulário
   - Mensagens de validação

3. **Rodapé**:
   - Botão Secundário "Cancelar"
   - Botão Primário "Salvar"

### Drawer de Filtros Avançados

**Estrutura**:

- **Overlay**: Background semi-transparente
- **Container**: Background branco, box-shadow
- **Largura**: 320px
- **Posição**: Direita

**Componentes**:

1. **Cabeçalho**:

   - Título "Filtros Avançados"
   - Botão de fechar (X)

2. **Conteúdo**:

   - Campos de formulário para filtros
   - Agrupados por categorias

3. **Rodapé**:
   - Botão Terciário "Limpar Filtros"
   - Botão Primário "Aplicar Filtros"

### Popover de Ações

**Estrutura**:

- **Container**: Background branco, border, border-radius, box-shadow
- **Largura**: 200px
- **Posição**: Relativa ao elemento de trigger

**Componentes**:

1. **Lista de Ações**:
   - Itens com ícone e texto
   - Hover background
   - Separador entre grupos de ações
   - Destaque para ações destrutivas (vermelho)

## Notificações e Mensagens

### Toast de Notificação

**Estrutura**:

- **Container**: Background branco, border-radius, box-shadow
- **Posição**: Canto superior direito
- **Duração**: Temporária (auto-dismiss)

**Componentes**:

1. **Ícone**: Conforme tipo (sucesso, erro, aviso, informação)
2. **Conteúdo**:
   - Título (opcional)
   - Mensagem
3. **Botão de Fechar**: X no canto superior direito

### Mensagem de Página Vazia

**Estrutura**:

- **Container**: Centralizado na área de conteúdo
- **Alinhamento**: Centro

**Componentes**:

1. **Ilustração**: Imagem representativa
2. **Título**: Texto informativo
3. **Descrição**: Texto explicativo
4. **Ação**: Botão primário para ação principal

## Páginas de Autenticação

### Login

**Estrutura**:

- **Background**: Cor de fundo ou imagem
- **Container**: Card centralizado

**Componentes**:

1. **Logo**: Centralizado no topo
2. **Título**: "Acesse sua conta"
3. **Formulário**:
   - Campo de Email/Usuário
   - Campo de Senha (com toggle de visibilidade)
   - Checkbox "Lembrar-me"
   - Botão "Esqueci minha senha"
   - Botão Primário "Entrar" (largura total)
4. **Rodapé**: Informações de copyright

### Esqueci Minha Senha

**Estrutura**:

- **Background**: Cor de fundo ou imagem
- **Container**: Card centralizado

**Componentes**:

1. **Logo**: Centralizado no topo
2. **Título**: "Recuperar senha"
3. **Descrição**: Texto explicativo
4. **Formulário**:
   - Campo de Email
   - Botão Primário "Enviar instruções" (largura total)
   - Link "Voltar para o login"
5. **Rodapé**: Informações de copyright

## Responsividade

### Desktop (≥992px)

- Menu lateral expandido (240px)
- Grid de 12 colunas
- Cards de métricas: 4 colunas cada (3 por linha)
- Tabelas com todas as colunas visíveis

### Tablet (≥768px e <992px)

- Menu lateral recolhido (64px)
- Grid de 8 colunas
- Cards de métricas: 4 colunas cada (2 por linha)
- Tabelas com scroll horizontal ou colunas menos importantes ocultas

### Mobile (<768px)

- Menu lateral oculto (acessível via botão de menu)
- Grid de 4 colunas
- Cards de métricas: 4 colunas cada (1 por linha)
- Tabelas com visualização adaptada ou cards em vez de tabelas
- Formulários com campos em largura total
- Modais ocupando toda a largura da tela
