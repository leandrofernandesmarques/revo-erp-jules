# Guia de Prototipação com Design Tokens

Este documento detalha como implementar protótipos interativos no Figma para o ERP Revo, utilizando os design tokens e componentes definidos anteriormente.

## Princípios de Prototipação

### Abordagem

- **Fidelidade**: Alta fidelidade visual com interações representativas
- **Consistência**: Comportamentos padronizados em toda a interface
- **Feedback**: Estados visuais claros para todas as interações
- **Acessibilidade**: Considerar diferentes formas de interação

## Configuração de Protótipos no Figma

### Configuração Básica

```
- Dispositivo: Desktop Web (1440x900)
- Início: Definir frame inicial para cada fluxo
- Hotspots: Tornar visíveis durante apresentação
- Animações: Usar Smart Animate para transições suaves
```

### Variantes e Propriedades

```
- Usar variantes de componentes para diferentes estados
- Configurar propriedades para personalização dinâmica
- Criar variáveis para estados que persistem entre telas
```

## Interatividade de Componentes

### Botões

```
- Trigger: Clique
- Ação: Navegação, Overlay, Abrir/Fechar
- Estados:
  - Normal: colors.primary.base
  - Hover: colors.primary.dark
  - Active: Escurecer 10%
  - Disabled: opacity.disabled
- Timing: animation.duration.fast
- Easing: animation.easing.standard
```

### Campos de Formulário

```
- Trigger: Clique, Digitação
- Ação: Alternar para variante com foco
- Estados:
  - Normal: borderWidth.thin colors.neutral.border
  - Focus: borderWidth.thin colors.primary.base, shadow.focus
  - Error: borderWidth.thin colors.status.error
  - Disabled: opacity.disabled
- Validação:
  - Trigger: Perda de foco ou submissão
  - Ação: Mostrar/ocultar mensagem de erro
```

### Dropdowns e Selects

```
- Trigger: Clique
- Ação: Abrir overlay com opções
- Animação: Fade in, duration.fast
- Estados:
  - Normal: borderWidth.thin colors.neutral.border
  - Open: borderWidth.thin colors.primary.base
  - Item Hover: background colors.neutral.background
  - Item Selected: background colors.primary.light, color colors.primary.base
```

### Tabelas

```
- Trigger: Clique em linha
- Ação: Selecionar linha
- Estados:
  - Normal: background colors.neutral.white
  - Hover: background colors.neutral.background
  - Selected: background colors.primary.light
- Ordenação:
  - Trigger: Clique em cabeçalho
  - Ação: Alternar ícone de ordenação
  - Estados: Não ordenado, Ascendente, Descendente
```

### Menu Lateral

```
- Trigger: Clique em item
- Ação: Navegação para página correspondente
- Estados:
  - Normal: background transparent
  - Hover: background colors.neutral.background
  - Active: background colors.primary.light, color colors.primary.base
- Expansão/Recolhimento:
  - Trigger: Clique no botão de toggle
  - Ação: Alternar entre variantes expandido/recolhido
  - Animação: Smart animate, duration.normal
```

### Cards e Expansíveis

```
- Trigger: Clique em cabeçalho
- Ação: Expandir/recolher conteúdo
- Animação: Expandir/recolher, duration.normal
- Feedback: Rotação do ícone de seta
```

## Fluxos Principais

### Fluxo de Login

```
Sequência:
1. Tela de Login
   - Interação: Preencher campos de usuário e senha
   - Validação: Mostrar erro se campos vazios
   - Ação: Clique no botão "Entrar"
2. Loading
   - Feedback: Botão em estado de loading
   - Duração: 1-2 segundos (simulado)
3. Redirecionamento
   - Sucesso: Navegar para Dashboard
   - Erro: Mostrar mensagem de erro no formulário
```

### Fluxo de Listagem e Filtros

```
Sequência:
1. Listagem Inicial
   - Interação: Visualizar dados em tabela
   - Ação: Clique no botão "Filtros"
2. Drawer de Filtros
   - Interação: Selecionar valores nos campos de filtro
   - Ação: Clique em "Aplicar Filtros"
3. Listagem Filtrada
   - Feedback: Indicador de filtros ativos
   - Interação: Clique em tag de filtro para remover
```

### Fluxo de Cadastro

```
Sequência:
1. Listagem
   - Interação: Clique no botão "Novo"
   - Ação: Abrir formulário de cadastro
2. Formulário - Dados Principais
   - Interação: Preencher campos obrigatórios
   - Validação: Mostrar erros em campos inválidos
   - Navegação: Alternar entre abas do formulário
3. Salvar
   - Interação: Clique no botão "Salvar"
   - Feedback: Botão em estado de loading
   - Sucesso: Toast de confirmação e retorno à listagem
```

### Fluxo de Pedido de Venda

```
Sequência:
1. Listagem de Pedidos
   - Interação: Clique no botão "Novo Pedido"
   - Ação: Abrir formulário de pedido
2. Cabeçalho do Pedido
   - Interação: Selecionar cliente no dropdown com busca
   - Interação: Preencher data e demais campos
3. Adicionar Produtos
   - Interação: Clique em "Adicionar Produto"
   - Ação: Abrir modal de seleção de produto
   - Interação: Buscar e selecionar produto
   - Interação: Definir quantidade e valores
   - Ação: Adicionar à tabela de produtos
4. Finalizar Pedido
   - Interação: Clique no botão "Salvar"
   - Feedback: Botão em estado de loading
   - Sucesso: Toast de confirmação e redirecionamento
```

## Interações Específicas

### Dashboard Interativo

```
Interações:
1. Filtro de Período
   - Trigger: Clique no filtro de período
   - Ação: Abrir popover com opções e calendário
   - Interação: Selecionar período
   - Feedback: Atualização dos dados do dashboard
2. Gráficos Interativos
   - Trigger: Hover sobre pontos do gráfico
   - Ação: Mostrar tooltip com valores detalhados
   - Interação: Clique em legenda para mostrar/ocultar séries
```

### Tabelas Avançadas

```
Interações:
1. Expansão de Linha
   - Trigger: Clique no ícone de expansão
   - Ação: Expandir linha para mostrar detalhes
   - Animação: Expandir, duration.normal
2. Edição Inline
   - Trigger: Duplo clique em célula editável
   - Ação: Transformar em campo de edição
   - Interação: Editar valor e pressionar Enter
3. Seleção Múltipla
   - Trigger: Clique em checkbox de linha
   - Ação: Selecionar linha e mostrar ações em massa
   - Feedback: Contador de itens selecionados
```

### Formulários Dinâmicos

```
Interações:
1. Campos Condicionais
   - Trigger: Alteração em campo de controle
   - Ação: Mostrar/ocultar campos dependentes
   - Exemplo: Tipo de pessoa (física/jurídica) altera campos
2. Validação em Tempo Real
   - Trigger: Digitação ou perda de foco
   - Ação: Validar campo e mostrar feedback
   - Feedback: Ícone de status e mensagem
3. Auto-completar Endereço
   - Trigger: Preenchimento de CEP
   - Ação: Simular busca e auto-preenchimento
   - Feedback: Campos preenchidos automaticamente
```

## Animações e Transições

### Transições de Página

```
Tipos:
1. Navegação Principal
   - Estilo: Fade, duration.normal
   - Aplicação: Mudança entre módulos principais
2. Navegação Secundária
   - Estilo: Slide horizontal, duration.normal
   - Aplicação: Navegação dentro do mesmo módulo
3. Drill-down
   - Estilo: Scale up, duration.normal
   - Aplicação: Navegação de listagem para detalhe
```

### Animações de Componentes

```
Tipos:
1. Expansão/Recolhimento
   - Estilo: Smooth height transition
   - Duração: animation.duration.normal
   - Aplicação: Collapse, submenu, detalhes expansíveis
2. Fade
   - Estilo: Opacity transition
   - Duração: animation.duration.fast
   - Aplicação: Tooltips, popovers, mensagens
3. Slide
   - Estilo: Position transition
   - Duração: animation.duration.normal
   - Aplicação: Drawers, notificações, painéis laterais
```

## Feedback Visual

### Mensagens de Sistema

```
Tipos:
1. Toast
   - Trigger: Após ação concluída
   - Posição: Canto superior direito
   - Duração: 3 segundos
   - Animação: Slide in da direita, fade out
   - Variantes: Sucesso, Erro, Informação, Aviso
2. Alertas na Página
   - Trigger: Carregamento da página
   - Posição: Topo do conteúdo
   - Variantes: Sucesso, Erro, Informação, Aviso
   - Interação: Clique no X para fechar
```

### Indicadores de Loading

```
Tipos:
1. Botão com Loading
   - Trigger: Clique em botão que inicia ação assíncrona
   - Estilo: Spinner no lugar do texto ou ao lado
   - Estado: Desabilitado durante loading
2. Loading de Página
   - Trigger: Navegação ou carregamento de dados
   - Estilo: Spinner centralizado ou skeleton screens
   - Duração: Simulada para protótipo (1-2 segundos)
```

### Confirmações

```
Tipos:
1. Modal de Confirmação
   - Trigger: Ações destrutivas ou importantes
   - Estilo: Modal com título, mensagem e botões
   - Botões: Confirmar (primário), Cancelar (secundário)
   - Animação: Fade in, scale up
2. Inline Confirmation
   - Trigger: Ações menos críticas
   - Estilo: Mensagem inline próxima ao elemento
   - Duração: Temporária (3 segundos)
```

## Responsividade Interativa

### Adaptação de Menu

```
Interações:
1. Menu em Tablet
   - Estado Inicial: Recolhido (apenas ícones)
   - Trigger: Clique no botão de expansão
   - Ação: Expandir temporariamente como overlay
2. Menu em Mobile
   - Estado Inicial: Oculto
   - Trigger: Clique no botão de menu (hambúrguer)
   - Ação: Abrir menu como drawer lateral
```

### Adaptação de Tabelas

```
Interações:
1. Tabelas em Tablet
   - Comportamento: Scroll horizontal para colunas extras
   - Interação: Swipe horizontal para navegar
2. Tabelas em Mobile
   - Comportamento: Transformação em cards
   - Layout: Cada linha vira um card com dados em formato vertical
   - Interação: Tap para expandir/recolher detalhes
```

## Implementação no Figma

### Organização de Protótipo

```
1. Páginas de Fluxo
   - Agrupar telas relacionadas a um mesmo fluxo
   - Nomear claramente com prefixos de fluxo
2. Conexões de Protótipo
   - Documentar com descrições claras
   - Usar cores para categorizar tipos de interação
3. Variáveis
   - Criar variáveis para estados persistentes
   - Exemplo: usuário_logado, filtros_ativos, tema
```

### Apresentação do Protótipo

```
1. Modo de Apresentação
   - Configurar ponto de início para cada fluxo
   - Adicionar hotspots visíveis para áreas interativas
2. Documentação Integrada
   - Adicionar notas explicativas para interações complexas
   - Incluir instruções para testadores
```

## Fluxos Completos para Prototipação

### 1. Fluxo Completo de Login e Dashboard

```
- Login > Validação > Dashboard > Navegação pelo Menu > Filtros do Dashboard > Expansão de Métricas
```

### 2. Fluxo Completo de Cadastro de Cliente

```
- Listagem > Novo Cliente > Preenchimento de Dados > Validação > Salvar > Confirmação > Retorno à Listagem
```

### 3. Fluxo Completo de Pedido de Venda

```
- Listagem > Novo Pedido > Seleção de Cliente > Adição de Produtos > Cálculos > Salvar > Faturar > Emissão de NF-e
```

### 4. Fluxo Completo de Gestão Financeira

```
- Dashboard Financeiro > Filtros > Contas a Receber > Novo Recebimento > Baixa de Título > Atualização de Saldo
```

## Checklist de Prototipação

Para cada fluxo:

- [ ] Criar todas as telas necessárias
- [ ] Configurar variantes de componentes para diferentes estados
- [ ] Definir conexões de protótipo entre telas
- [ ] Configurar animações e transições
- [ ] Implementar feedback visual para todas as interações
- [ ] Testar fluxo completo em modo de apresentação
- [ ] Documentar pontos importantes ou comportamentos específicos
