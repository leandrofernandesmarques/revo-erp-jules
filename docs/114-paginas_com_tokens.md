# Guia de Implementação de Páginas com Design Tokens

Este documento detalha como implementar as páginas organizacionais do ERP Revo no Figma, utilizando os design tokens e componentes definidos anteriormente.

## Estrutura de Páginas

Cada página do sistema deve seguir uma estrutura consistente baseada nos tokens e componentes:

### Layout Base

```
Layout Base:
- Menu Lateral: width: size.menu.width.expanded
- Cabeçalho: height: size.header.height
- Área de Conteúdo: padding: spacing.lg
- Grid: 12 colunas, gutter: grid.gutter
```

## Páginas Principais

### Dashboard

**Estrutura**:

```
- Menu Lateral: Componente Menu Lateral (expandido)
- Cabeçalho:
  - Breadcrumbs: typography.textStyles.breadcrumb
  - Título: typography.textStyles.pageTitle
  - Ações Rápidas: Componentes de Botão de Ícone
- Área de Filtros:
  - Background: colors.neutral.white
  - Border-bottom: borderWidth.thin colors.neutral.border
  - Padding: spacing.sm spacing.lg
- Conteúdo Principal:
  - Grid de 12 colunas
  - Gap: spacing.lg
```

**Componentes**:

```
- Visão Geral:
  - Card: shadow.sm, borderRadius.lg
  - Padding: spacing.md
  - Gap entre indicadores: spacing.md
  - Indicadores:
    - Ícone: size.icon.lg, background colors.neutral.background
    - Valor: typography.fontSize.h2, fontWeight.medium
    - Legenda: typography.textStyles.caption

- Cards de Métricas:
  - Width: 4 colunas cada (responsivo)
  - Margin-bottom: spacing.lg
  - Título: typography.textStyles.cardTitle
  - Valor: typography.fontSize.h1, fontWeight.medium
  - Gráfico: height 120px

- Gráficos:
  - Width: 6 colunas cada (responsivo)
  - Height: 300px
  - Padding: spacing.md
  - Título: typography.textStyles.cardTitle
  - Legenda: typography.textStyles.caption
```

### Listagem de Registros

**Estrutura**:

```
- Menu Lateral: Componente Menu Lateral (expandido)
- Cabeçalho:
  - Breadcrumbs: typography.textStyles.breadcrumb
  - Título: typography.textStyles.pageTitle
  - Ações Rápidas: Componentes de Botão de Ícone
- Área de Filtros:
  - Background: colors.neutral.white
  - Border-bottom: borderWidth.thin colors.neutral.border
  - Padding: spacing.sm spacing.lg
  - Campo de Pesquisa: Componente Campo de Texto variante Pesquisa
- Barra de Ações:
  - Padding: spacing.md 0
  - Gap: spacing.sm
  - Botões: Componentes de Botão variantes Primário, Secundário, Terciário
- Conteúdo Principal:
  - Tabela: Componente Tabela
  - Paginação: Componente Paginação, margin-top: spacing.md
```

**Componentes**:

```
- Tabela:
  - Width: 12 colunas
  - Background: colors.neutral.white
  - Border: borderWidth.thin colors.neutral.border
  - Border-radius: borderRadius.lg
  - Cabeçalho:
    - Background: colors.neutral.background
    - Typography: typography.textStyles.subtitle
    - Padding: spacing.sm spacing.md
  - Células:
    - Typography: typography.textStyles.body
    - Padding: spacing.sm spacing.md
    - Border-bottom: borderWidth.thin colors.neutral.borderLight
  - Estados de Linha:
    - Hover: background colors.neutral.background
    - Selecionada: background colors.primary.light

- Paginação:
  - Alinhamento: direita
  - Gap: spacing.xs
  - Botões de Página:
    - Size: size.button.height.md x size.button.height.md
    - Border-radius: borderRadius.md
    - Typography: typography.textStyles.body
    - Estado Ativo: background colors.primary.base, color colors.neutral.white
```

### Formulário de Cadastro

**Estrutura**:

```
- Menu Lateral: Componente Menu Lateral (expandido)
- Cabeçalho:
  - Breadcrumbs: typography.textStyles.breadcrumb
  - Título: typography.textStyles.pageTitle
  - Ações Rápidas: Componentes de Botão de Ícone
- Abas (quando aplicável):
  - Border-bottom: borderWidth.thin colors.neutral.border
  - Padding: 0 spacing.lg
  - Item de Aba:
    - Padding: spacing.sm spacing.md
    - Typography: typography.textStyles.body
    - Estado Ativo: color colors.primary.base, border-bottom borderWidth.thick colors.primary.base
- Conteúdo Principal:
  - Padding: spacing.lg
  - Grid: 12 colunas, gutter grid.gutter
  - Grupos de Campos:
    - Margin-bottom: spacing.lg
    - Título do Grupo: typography.textStyles.subtitle, margin-bottom: spacing.sm
  - Campos:
    - Margin-bottom: spacing.md
    - Label: typography.textStyles.bodySecondary, margin-bottom: spacing.xxs
    - Campo: Componente Campo de Texto
    - Mensagem de Erro: typography.textStyles.caption, color colors.status.error
- Barra de Ações:
  - Padding: spacing.md spacing.lg
  - Border-top: borderWidth.thin colors.neutral.border
  - Alinhamento: direita
  - Gap: spacing.sm
  - Botões: Componentes de Botão variantes Primário, Secundário, Terciário
```

**Componentes**:

```
- Grupo de Campos:
  - Width: 12 colunas
  - Background: colors.neutral.white
  - Border-radius: borderRadius.lg
  - Padding: spacing.md
  - Border: borderWidth.thin colors.neutral.border

- Campo de Formulário:
  - Width: variável (3, 4, 6 ou 12 colunas dependendo do campo)
  - Label: typography.textStyles.bodySecondary
  - Campo: Componente Campo de Texto
  - Mensagem: typography.textStyles.caption
```

### Visualização Detalhada

**Estrutura**:

```
- Menu Lateral: Componente Menu Lateral (expandido)
- Cabeçalho:
  - Breadcrumbs: typography.textStyles.breadcrumb
  - Título: typography.textStyles.pageTitle
  - Ações Rápidas: Componentes de Botão de Ícone
- Barra de Ações:
  - Padding: spacing.md spacing.lg
  - Background: colors.neutral.white
  - Border-bottom: borderWidth.thin colors.neutral.border
  - Botões: Componentes de Botão variantes Primário, Secundário, Terciário
- Conteúdo Principal:
  - Grid: 12 colunas, gutter grid.gutter
  - Padding: spacing.lg
  - Gap: spacing.lg
```

**Componentes**:

```
- Card de Informações:
  - Width: variável (6 ou 12 colunas dependendo do conteúdo)
  - Background: colors.neutral.white
  - Border-radius: borderRadius.lg
  - Border: borderWidth.thin colors.neutral.border
  - Padding: spacing.md
  - Título: typography.textStyles.cardTitle, margin-bottom: spacing.sm
  - Conteúdo:
    - Linhas de Informação:
      - Padding: spacing.xs 0
      - Border-bottom: borderWidth.thin colors.neutral.borderLight
      - Label: typography.textStyles.bodySecondary, width: 30%
      - Valor: typography.textStyles.body, width: 70%

- Tabela de Itens:
  - Width: 12 colunas
  - Mesmas especificações da Tabela em Listagem de Registros
```

## Modais e Overlays

### Modal de Formulário

**Estrutura**:

```
- Overlay: background rgba(0, 0, 0, opacity.overlay)
- Container:
  - Width: variável (360px, 520px, 720px)
  - Background: colors.neutral.white
  - Border-radius: borderRadius.lg
  - Box-shadow: shadow.md
- Cabeçalho:
  - Padding: spacing.md spacing.lg
  - Border-bottom: borderWidth.thin colors.neutral.borderLight
  - Título: typography.textStyles.cardTitle
  - Botão Fechar: Componente Botão de Ícone
- Conteúdo:
  - Padding: spacing.lg
  - Gap entre campos: spacing.md
- Rodapé:
  - Padding: spacing.md spacing.lg
  - Border-top: borderWidth.thin colors.neutral.borderLight
  - Alinhamento: direita
  - Gap: spacing.sm
  - Botões: Componentes de Botão variantes Primário, Secundário
```

### Drawer

**Estrutura**:

```
- Overlay: background rgba(0, 0, 0, opacity.overlay)
- Container:
  - Width: variável (256px, 384px, 512px)
  - Height: 100vh
  - Background: colors.neutral.white
  - Box-shadow: -2px 0 8px rgba(0, 0, 0, 0.15) (direita) ou 2px 0 8px rgba(0, 0, 0, 0.15) (esquerda)
- Cabeçalho:
  - Padding: spacing.md spacing.lg
  - Border-bottom: borderWidth.thin colors.neutral.borderLight
  - Título: typography.textStyles.cardTitle
  - Botão Fechar: Componente Botão de Ícone
- Conteúdo:
  - Padding: spacing.lg
  - Gap entre campos: spacing.md
- Rodapé:
  - Padding: spacing.md spacing.lg
  - Border-top: borderWidth.thin colors.neutral.borderLight
  - Alinhamento: direita
  - Gap: spacing.sm
  - Botões: Componentes de Botão variantes Primário, Secundário
```

## Páginas Específicas

### Dashboard de Vendas

**Estrutura**:

```
- Layout Base
- Área de Filtros:
  - Filtro de Período: Componente Botão Terciário com ícone
  - Filtros Avançados: Componente Botão Terciário com ícone
  - Indicador de Atualização: typography.textStyles.bodySecondary
- Conteúdo:
  - Cards de Métricas (4 colunas cada):
    - Total de Vendas
    - Ticket Médio
    - Pedidos
  - Gráficos (6 colunas cada):
    - Pedidos por Estado (mapa)
    - Pedidos por Integrações (barras)
  - Produtos Mais Vendidos (12 colunas):
    - Tabela com paginação
```

### Listagem de Pedidos

**Estrutura**:

```
- Layout Base
- Área de Filtros:
  - Campo de Pesquisa
  - Botão de Filtros Avançados
- Barra de Ações:
  - Botão "Novo Pedido" (Primário)
  - Botão "Importar" (Secundário)
  - Botão "Exportar" (Terciário)
  - Dropdown "Mais Ações"
- Indicadores de Status (cards pequenos):
  - Em Aberto
  - Aprovado
  - Faturado
  - Cancelado
  - Total
- Tabela de Pedidos:
  - Colunas: Número, Data, Cliente, Valor Total, Status, Forma de Pagamento, Ações
  - Status: Componente Badge com cores variáveis
  - Ações: Ícones de Editar, Faturar, Cancelar, Mais Opções
- Paginação
```

### Formulário de Pedido

**Estrutura**:

```
- Layout Base
- Informações do Pedido (12 colunas):
  - Data: Componente DatePicker
  - Cliente: Componente Select com busca
  - Vendedor: Componente Select
  - Forma de Pagamento: Componente Select
  - Condição de Pagamento: Componente Select
  - Observações: Componente Textarea
- Produtos (12 colunas):
  - Tabela de produtos
  - Botão "Adicionar Produto"
- Resumo Financeiro (4 colunas, alinhado à direita):
  - Subtotal
  - Desconto
  - Frete
  - Total
- Barra de Ações:
  - Botão "Salvar" (Primário)
  - Botão "Cancelar" (Secundário)
  - Botão "Excluir" (Terciário)
  - Botão "Faturar" (Primário)
```

## Responsividade

### Desktop (≥992px)

```
- Menu lateral expandido (240px)
- Grid de 12 colunas
- Cards de métricas: 4 colunas cada (3 por linha)
- Tabelas com todas as colunas visíveis
```

### Tablet (≥768px e <992px)

```
- Menu lateral recolhido (64px)
- Grid de 8 colunas
- Cards de métricas: 4 colunas cada (2 por linha)
- Tabelas com scroll horizontal ou colunas menos importantes ocultas
```

### Mobile (<768px)

```
- Menu lateral oculto (acessível via botão de menu)
- Grid de 4 colunas
- Cards de métricas: 4 colunas cada (1 por linha)
- Tabelas com visualização adaptada ou cards em vez de tabelas
- Formulários com campos em largura total
- Modais ocupando toda a largura da tela
```

## Implementação no Figma

### Organização de Frames

```
- Agrupar frames relacionados em seções
- Nomear frames seguindo padrão: [Módulo] / [Subseção] / [Variante]
- Organizar frames em ordem lógica de uso
```

### Uso de Auto Layout

```
- Utilizar Auto Layout para todos os elementos da página
- Configurar resizing apropriado (hug/fill)
- Definir constraints para comportamento responsivo
```

### Variantes de Página

```
- Criar variantes para diferentes estados da página
- Exemplo: Listagem vazia, Listagem com dados, Listagem com filtros aplicados
- Exemplo: Formulário novo, Formulário em edição, Formulário com erros
```

### Documentação de Página

```
- Adicionar notas explicativas para elementos importantes
- Documentar comportamentos específicos
- Referenciar componentes utilizados
```

## Checklist de Implementação

Para cada página:

- [ ] Aplicar layout base consistente
- [ ] Utilizar componentes do design system
- [ ] Aplicar tokens de cor, tipografia e espaçamento
- [ ] Configurar Auto Layout apropriado
- [ ] Implementar variantes responsivas
- [ ] Documentar comportamentos específicos
- [ ] Verificar consistência com outras páginas
