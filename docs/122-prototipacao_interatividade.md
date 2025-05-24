# Prototipação de Interatividade e Fluxos - ERP Revo

Este documento detalha a prototipação de interatividade dos componentes e fluxos principais do ERP Revo no Figma, garantindo uma representação fiel do comportamento real do sistema.

## Princípios de Prototipação

### Abordagem de Prototipação

- **Fidelidade**: Alta fidelidade visual com interações representativas
- **Escopo**: Focar nos fluxos principais e interações críticas
- **Consistência**: Manter comportamentos consistentes em toda a interface
- **Feedback**: Incluir estados de feedback para todas as interações

### Técnicas no Figma

- **Variantes de Componentes**: Para representar diferentes estados
- **Propriedades de Componentes**: Para personalização dinâmica
- **Conexões de Protótipo**: Para simular navegação e interações
- **Ações de Protótipo**: Navegação, overlay, abrir/fechar, animações
- **Variáveis**: Para estados que persistem entre telas

## Interatividade de Componentes

### Menu Lateral

**Interações**:

1. **Expansão/Recolhimento**:

   - Trigger: Clique no botão de toggle
   - Ação: Alternar entre variantes expandido/recolhido
   - Animação: Smart animate com duração de 300ms

2. **Navegação entre Itens**:

   - Trigger: Clique em item de menu
   - Ação: Navegar para a página correspondente
   - Estado: Atualizar item ativo

3. **Expansão de Submenu**:
   - Trigger: Clique em item com submenu
   - Ação: Mostrar/ocultar submenu
   - Animação: Expandir/recolher com duração de 200ms

### Botões

**Interações**:

1. **Estados de Hover**:

   - Trigger: Mouse over
   - Ação: Alternar para variante hover
   - Timing: Instantâneo

2. **Estados de Clique**:

   - Trigger: Mouse down
   - Ação: Alternar para variante ativo
   - Timing: Instantâneo
   - Retorno: Voltar para estado normal após soltar

3. **Botões de Ação**:
   - Trigger: Clique
   - Ação: Executar ação correspondente (abrir modal, salvar, etc.)
   - Feedback: Alternar para variante de loading quando aplicável

### Campos de Formulário

**Interações**:

1. **Foco**:

   - Trigger: Clique no campo
   - Ação: Alternar para variante com foco
   - Feedback: Mostrar cursor de texto

2. **Preenchimento**:

   - Trigger: Digitação (simulada)
   - Ação: Mostrar texto digitado
   - Estado: Campo preenchido

3. **Validação**:

   - Trigger: Perda de foco ou submissão
   - Ação: Alternar para variante de erro se inválido
   - Feedback: Mostrar mensagem de erro abaixo do campo

4. **Campos com Máscara**:
   - Trigger: Digitação (simulada)
   - Ação: Aplicar formatação conforme digitação
   - Exemplo: CPF 123.456.789-00, Telefone (11) 98765-4321

### Dropdowns e Selects

**Interações**:

1. **Abertura**:

   - Trigger: Clique no campo
   - Ação: Mostrar overlay com opções
   - Animação: Fade in com duração de 200ms

2. **Seleção de Item**:

   - Trigger: Clique em item da lista
   - Ação: Fechar dropdown e atualizar valor selecionado
   - Feedback: Destacar item selecionado na lista

3. **Busca em Select**:
   - Trigger: Digitação no campo de busca
   - Ação: Filtrar itens da lista
   - Feedback: Mostrar apenas itens correspondentes

### Tabelas

**Interações**:

1. **Ordenação**:

   - Trigger: Clique no cabeçalho da coluna
   - Ação: Alternar entre ordenação ascendente/descendente
   - Feedback: Mostrar ícone de ordenação no cabeçalho

2. **Seleção de Linha**:

   - Trigger: Clique na linha
   - Ação: Alternar para variante selecionada
   - Estado: Linha destacada

3. **Ações em Linha**:

   - Trigger: Clique em botão de ação
   - Ação: Abrir menu de contexto ou executar ação direta
   - Feedback: Mostrar confirmação quando necessário

4. **Paginação**:
   - Trigger: Clique em número de página ou botões anterior/próximo
   - Ação: Navegar para a página correspondente
   - Feedback: Atualizar indicador de página atual

### Cards e Expansíveis

**Interações**:

1. **Expansão de Detalhes**:

   - Trigger: Clique em "expandir detalhes"
   - Ação: Mostrar modal com detalhes expandidos
   - Animação: Fade in do modal

2. **Cards Clicáveis**:

   - Trigger: Hover sobre card
   - Ação: Alternar para variante hover
   - Feedback: Elevação sutil (shadow) e cursor pointer

3. **Collapse**:
   - Trigger: Clique no cabeçalho
   - Ação: Expandir/recolher conteúdo
   - Animação: Expandir/recolher com duração de 300ms
   - Feedback: Rotação do ícone de seta

### Notificações e Alertas

**Interações**:

1. **Toast**:

   - Trigger: Após ação concluída (simulado)
   - Ação: Mostrar toast no canto superior direito
   - Animação: Slide in da direita, permanece por 3s, fade out
   - Interação: Clique no X para fechar imediatamente

2. **Alertas na Página**:

   - Trigger: Carregamento da página (simulado)
   - Ação: Mostrar alerta no topo do conteúdo
   - Interação: Clique no X para fechar

3. **Badges Dinâmicos**:
   - Trigger: Atualização de status (simulado)
   - Ação: Atualizar contagem ou status
   - Animação: Pulse ao atualizar

## Fluxos Principais

### Fluxo de Login

**Sequência**:

1. **Tela de Login**:

   - Interação: Preencher campos de usuário e senha
   - Validação: Mostrar erro se campos vazios
   - Ação: Clique no botão "Entrar"

2. **Loading**:

   - Feedback: Botão em estado de loading
   - Duração: 1-2 segundos (simulado)

3. **Redirecionamento**:

   - Sucesso: Navegar para Dashboard
   - Erro: Mostrar mensagem de erro no formulário

4. **Esqueci Minha Senha**:
   - Interação: Clique em "Esqueci minha senha"
   - Ação: Navegar para tela de recuperação
   - Interação: Preencher email e enviar
   - Feedback: Confirmação de envio

### Fluxo de Cadastro de Cliente

**Sequência**:

1. **Listagem de Clientes**:

   - Interação: Clique no botão "Novo Cliente"
   - Ação: Abrir formulário de cadastro

2. **Formulário - Dados Principais**:

   - Interação: Preencher campos obrigatórios
   - Validação: Mostrar erros em campos inválidos
   - Navegação: Alternar entre abas do formulário

3. **Formulário - Endereço**:

   - Interação: Preencher CEP
   - Ação: Auto-preenchimento de campos de endereço
   - Interação: Completar campos restantes

4. **Salvar**:
   - Interação: Clique no botão "Salvar"
   - Feedback: Botão em estado de loading
   - Sucesso: Toast de confirmação e retorno à listagem
   - Erro: Mensagem de erro e permanência no formulário

### Fluxo de Criação de Pedido

**Sequência**:

1. **Listagem de Pedidos**:

   - Interação: Clique no botão "Novo Pedido"
   - Ação: Abrir formulário de pedido

2. **Cabeçalho do Pedido**:

   - Interação: Selecionar cliente no dropdown com busca
   - Interação: Preencher data e demais campos

3. **Adicionar Produtos**:

   - Interação: Clique em "Adicionar Produto"
   - Ação: Abrir modal de seleção de produto
   - Interação: Buscar e selecionar produto
   - Interação: Definir quantidade e valores
   - Ação: Adicionar à tabela de produtos
   - Feedback: Atualização automática de subtotal e total

4. **Finalizar Pedido**:
   - Interação: Clique no botão "Salvar"
   - Feedback: Botão em estado de loading
   - Sucesso: Toast de confirmação e redirecionamento para visualização
   - Erro: Mensagem de erro e permanência no formulário

### Fluxo de Emissão de Nota Fiscal

**Sequência**:

1. **Listagem de Pedidos**:

   - Interação: Clique no ícone "Faturar" em um pedido
   - Ação: Abrir modal de confirmação

2. **Confirmação de Faturamento**:

   - Interação: Revisar informações do pedido
   - Interação: Clique em "Emitir Nota Fiscal"

3. **Processamento**:

   - Feedback: Modal com indicador de progresso
   - Estados: Validando dados, Enviando para SEFAZ, Processando

4. **Resultado**:
   - Sucesso: Modal com confirmação e opções (Visualizar NF-e, Imprimir DANFE)
   - Erro: Modal com detalhes do erro e opções de correção

### Fluxo de Filtros Avançados

**Sequência**:

1. **Listagem com Filtro Básico**:

   - Interação: Clique no botão "Filtros"
   - Ação: Abrir drawer de filtros avançados

2. **Configuração de Filtros**:

   - Interação: Selecionar valores nos campos de filtro
   - Interação: Expandir/recolher seções de filtros
   - Interação: Clique em "Limpar" para resetar filtros

3. **Aplicação de Filtros**:

   - Interação: Clique em "Aplicar Filtros"
   - Feedback: Drawer fecha e indicador de filtros ativos aparece
   - Ação: Listagem atualizada com itens filtrados

4. **Remoção de Filtros**:
   - Interação: Clique em tag de filtro ativo para remover
   - Interação: Clique em "Limpar todos" para remover todos os filtros
   - Feedback: Listagem atualizada sem filtros

### Fluxo de Configuração de Integração

**Sequência**:

1. **Listagem de Integrações Disponíveis**:

   - Interação: Clique em card de integração
   - Ação: Abrir modal de configuração

2. **Configuração Inicial**:

   - Interação: Preencher credenciais e configurações
   - Validação: Verificar campos obrigatórios
   - Interação: Clique em "Testar Conexão"

3. **Teste de Conexão**:

   - Feedback: Indicador de progresso
   - Sucesso: Mensagem de conexão bem-sucedida
   - Erro: Mensagem detalhada do erro

4. **Finalização**:
   - Interação: Clique em "Salvar"
   - Feedback: Modal de configurações adicionais (opcional)
   - Sucesso: Toast de confirmação e adição à lista de integrações ativas
   - Erro: Permanência no formulário com mensagens de erro

## Interações Específicas

### Dashboard Interativo

**Interações**:

1. **Filtro de Período**:

   - Trigger: Clique no filtro de período
   - Ação: Abrir popover com opções predefinidas e calendário
   - Interação: Selecionar período
   - Feedback: Atualização dos dados do dashboard

2. **Gráficos Interativos**:

   - Trigger: Hover sobre pontos do gráfico
   - Ação: Mostrar tooltip com valores detalhados
   - Interação: Clique em legenda para mostrar/ocultar séries

3. **Mapa Interativo**:
   - Trigger: Hover sobre estados
   - Ação: Destacar estado e mostrar tooltip com dados
   - Interação: Clique para filtrar dados por estado

### Tabelas Avançadas

**Interações**:

1. **Expansão de Linha**:

   - Trigger: Clique no ícone de expansão
   - Ação: Expandir linha para mostrar detalhes adicionais
   - Animação: Expandir com duração de 300ms

2. **Edição Inline**:

   - Trigger: Duplo clique em célula editável
   - Ação: Transformar em campo de edição
   - Interação: Editar valor e pressionar Enter
   - Feedback: Atualização do valor e indicador visual

3. **Seleção Múltipla**:
   - Trigger: Clique em checkbox de linha
   - Ação: Selecionar linha e mostrar ações em massa
   - Interação: Selecionar múltiplas linhas
   - Feedback: Contador de itens selecionados

### Formulários Dinâmicos

**Interações**:

1. **Campos Condicionais**:

   - Trigger: Alteração em campo de controle
   - Ação: Mostrar/ocultar campos dependentes
   - Exemplo: Tipo de pessoa (física/jurídica) altera campos visíveis

2. **Validação em Tempo Real**:

   - Trigger: Digitação ou perda de foco
   - Ação: Validar campo e mostrar feedback
   - Feedback: Ícone de status e mensagem de erro/sucesso

3. **Auto-completar Endereço**:
   - Trigger: Preenchimento de CEP
   - Ação: Simular busca e auto-preenchimento
   - Feedback: Campos preenchidos automaticamente
   - Interação: Possibilidade de editar campos auto-preenchidos

## Animações e Transições

### Transições de Página

**Tipos**:

1. **Navegação Principal**:

   - Estilo: Fade com duração de 300ms
   - Aplicação: Mudança entre módulos principais

2. **Navegação Secundária**:

   - Estilo: Slide horizontal com duração de 300ms
   - Aplicação: Navegação dentro do mesmo módulo

3. **Drill-down**:
   - Estilo: Scale up com duração de 300ms
   - Aplicação: Navegação de listagem para detalhe

### Animações de Componentes

**Tipos**:

1. **Expansão/Recolhimento**:

   - Estilo: Smooth height transition
   - Duração: 300ms
   - Aplicação: Collapse, submenu, detalhes expansíveis

2. **Fade**:

   - Estilo: Opacity transition
   - Duração: 200ms
   - Aplicação: Tooltips, popovers, mensagens

3. **Slide**:

   - Estilo: Position transition
   - Duração: 300ms
   - Aplicação: Drawers, notificações, painéis laterais

4. **Scale**:
   - Estilo: Size transition
   - Duração: 200ms
   - Aplicação: Botões, cards em hover, elementos de destaque

## Responsividade Interativa

### Adaptação de Menu

**Interações**:

1. **Menu em Tablet**:

   - Estado Inicial: Recolhido (apenas ícones)
   - Trigger: Clique no botão de expansão
   - Ação: Expandir temporariamente como overlay

2. **Menu em Mobile**:
   - Estado Inicial: Oculto
   - Trigger: Clique no botão de menu (hambúrguer)
   - Ação: Abrir menu como drawer lateral
   - Interação: Clique fora para fechar

### Adaptação de Tabelas

**Interações**:

1. **Tabelas em Tablet**:

   - Comportamento: Scroll horizontal para colunas extras
   - Interação: Swipe horizontal para navegar entre colunas

2. **Tabelas em Mobile**:
   - Comportamento: Transformação em cards
   - Layout: Cada linha vira um card com dados em formato vertical
   - Interação: Tap para expandir/recolher detalhes

### Adaptação de Formulários

**Interações**:

1. **Formulários em Tablet**:

   - Comportamento: Campos em duas colunas se transformam em uma
   - Interação: Navegação vertical mais extensa

2. **Formulários em Mobile**:
   - Comportamento: Campos ocupam largura total
   - Interação: Foco em campo move a tela para centralizar o campo
   - Adaptação: Datepickers e selects otimizados para touch

## Implementação no Figma

### Organização de Protótipo

1. **Páginas de Fluxo**:

   - Agrupar telas relacionadas a um mesmo fluxo
   - Nomear claramente com prefixos de fluxo

2. **Conexões de Protótipo**:

   - Documentar com descrições claras
   - Usar cores para categorizar tipos de interação

3. **Variáveis**:

   - Criar variáveis para estados persistentes
   - Exemplo: usuário_logado, filtros_ativos, tema

4. **Componentes Interativos**:
   - Criar variantes para todos os estados
   - Documentar comportamentos esperados

### Apresentação do Protótipo

1. **Modo de Apresentação**:

   - Configurar ponto de início para cada fluxo
   - Adicionar hotspots visíveis para áreas interativas

2. **Documentação Integrada**:

   - Adicionar notas explicativas para interações complexas
   - Incluir instruções para testadores

3. **Handoff para Desenvolvimento**:
   - Documentar especificações de animação
   - Detalhar comportamentos condicionais
   - Especificar breakpoints e comportamentos responsivos

## Fluxos Completos para Prototipação

### 1. Fluxo Completo de Login e Dashboard

- Login > Validação > Dashboard > Navegação pelo Menu > Filtros do Dashboard > Expansão de Métricas

### 2. Fluxo Completo de Cadastro de Cliente

- Listagem > Novo Cliente > Preenchimento de Dados > Validação > Salvar > Confirmação > Retorno à Listagem

### 3. Fluxo Completo de Pedido de Venda

- Listagem > Novo Pedido > Seleção de Cliente > Adição de Produtos > Cálculos > Salvar > Faturar > Emissão de NF-e

### 4. Fluxo Completo de Gestão Financeira

- Dashboard Financeiro > Filtros > Contas a Receber > Novo Recebimento > Baixa de Título > Atualização de Saldo

### 5. Fluxo Completo de Configuração de Integração

- Integrações > Adicionar > Seleção de Plataforma > Configuração > Teste > Ativação > Sincronização
