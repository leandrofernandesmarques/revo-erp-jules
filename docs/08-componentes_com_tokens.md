# Guia de Implementação de Componentes com Design Tokens

Este documento explica como implementar os componentes do ERP Revo no Figma utilizando os design tokens definidos nos arquivos JSON e YAML.

## Visão Geral

Os design tokens são a base para a criação de componentes consistentes e reutilizáveis. Eles definem valores fundamentais como cores, tipografia, espaçamentos e outros atributos visuais que devem ser aplicados em toda a interface.

## Como Utilizar os Design Tokens

### No Figma

1. **Configuração Inicial**:

   - Crie estilos de cores baseados nos tokens de cores
   - Crie estilos de texto baseados nos tokens de tipografia
   - Crie estilos de efeitos baseados nos tokens de sombras
   - Configure grids baseados nos tokens de grid

2. **Aplicação em Componentes**:
   - Use sempre os estilos criados, nunca valores diretos
   - Aplique espaçamentos conforme os tokens de spacing
   - Utilize os tamanhos definidos nos tokens de size
   - Siga os raios de borda definidos nos tokens de borderRadius

### Para Desenvolvedores

Os arquivos `design_tokens.json` e `design_tokens.yaml` podem ser utilizados diretamente em sistemas de design como:

- Style Dictionary
- Theo
- Tailwind CSS (via configuração)
- CSS Variables (via script de transformação)
- Styled Components (via tema)

## Mapeamento de Tokens para Componentes

### Botões

```
Botão Primário:
- Background: colors.primary.base
- Texto: colors.neutral.white
- Padding: spacing.xs (horizontal) spacing.xxs (vertical)
- Border-radius: borderRadius.md
- Altura: size.button.height.md
- Estados:
  - Hover: colors.primary.dark
  - Disabled: opacity.disabled
```

### Campos de Formulário

```
Campo de Texto:
- Border: borderWidth.thin colors.neutral.border
- Border-radius: borderRadius.md
- Padding: spacing.xs (horizontal) spacing.xxs (vertical)
- Altura: size.input.height.md
- Texto: typography.textStyles.body
- Placeholder: typography.textStyles.bodySecondary
- Estados:
  - Focus: shadow.focus
  - Error: colors.status.error (borda)
```

### Cards

```
Card Padrão:
- Background: colors.neutral.white
- Border-radius: borderRadius.lg
- Shadow: shadow.sm
- Padding: spacing.md
- Título: typography.textStyles.cardTitle
- Conteúdo: typography.textStyles.body
```

### Tabelas

```
Tabela:
- Cabeçalho:
  - Background: colors.neutral.background
  - Texto: typography.textStyles.subtitle
  - Padding: spacing.xs
- Células:
  - Border-bottom: borderWidth.thin colors.neutral.borderLight
  - Padding: spacing.xs
  - Texto: typography.textStyles.body
- Estados:
  - Hover: colors.neutral.background
  - Selecionado: colors.primary.light
```

### Menu Lateral

```
Menu:
- Background: colors.neutral.background
- Largura: size.menu.width.expanded
- Item:
  - Altura: size.button.height.md
  - Padding: spacing.xs
  - Texto: typography.textStyles.body
  - Ícone: size.icon.md
  - Estados:
    - Hover: opacity.hover
    - Ativo: colors.primary.light (background), colors.primary.base (texto)
```

## Componentes Compostos

Os componentes compostos devem ser construídos a partir dos componentes base, mantendo a consistência com os tokens.

### Formulário de Cadastro

```
Estrutura:
- Título: typography.textStyles.pageTitle
- Espaçamento entre campos: spacing.md
- Agrupamento de campos: spacing.lg
- Botões de ação: alinhados à direita, espaçamento spacing.xs
```

### Dashboard Card

```
Estrutura:
- Card base: seguindo especificação de Card Padrão
- Título: typography.textStyles.cardTitle
- Valor principal: typography.fontSize.h1, fontWeight.medium
- Gráfico: altura 120px
- Rodapé: borderWidth.thin colors.neutral.borderLight (top)
```

## Responsividade

Utilize os breakpoints definidos nos tokens para criar variantes responsivas dos componentes:

```
- xs (<576px): Componentes em largura total, empilhados
- sm (≥576px): Layout de 2 colunas para formulários
- md (≥768px): Menu lateral visível, layout de 8 colunas
- lg (≥992px): Layout completo de 12 colunas
```

## Variantes de Componentes

Crie variantes para todos os estados e tamanhos dos componentes:

### Estados

- Normal
- Hover
- Ativo
- Foco
- Desabilitado
- Erro

### Tamanhos

- Pequeno (sm)
- Médio (md) - padrão
- Grande (lg)

## Propriedades de Componentes

Configure propriedades de componentes no Figma para facilitar a personalização:

### Botão

- Variante: Primário, Secundário, Terciário
- Tamanho: Pequeno, Médio, Grande
- Estado: Normal, Hover, Ativo, Desabilitado
- Com Ícone: Sim, Não
- Posição do Ícone: Esquerda, Direita

### Campo de Texto

- Variante: Padrão, Pesquisa, Senha
- Tamanho: Pequeno, Médio, Grande
- Estado: Normal, Foco, Erro, Desabilitado
- Com Ícone: Sim, Não
- Posição do Ícone: Esquerda, Direita
- Com Label: Sim, Não
- Com Mensagem: Sim, Não

## Auto Layout

Utilize Auto Layout em todos os componentes para garantir comportamento responsivo e consistente:

- Defina padding conforme tokens de espaçamento
- Configure resizing apropriado (hug/fill)
- Defina alinhamento e distribuição de elementos
- Use constraints para comportamento responsivo

## Nomenclatura de Componentes

Siga um padrão consistente de nomenclatura:

```
[Categoria]/[Componente]/[Variante]
```

Exemplos:

- `Botões/Primário/Normal`
- `Campos/Texto/Com Ícone`
- `Cards/Métrica/Com Gráfico`

## Checklist de Implementação

Para cada componente:

- [ ] Criar todas as variantes necessárias
- [ ] Aplicar tokens de cor, tipografia e espaçamento
- [ ] Configurar Auto Layout apropriado
- [ ] Definir propriedades de componente
- [ ] Testar comportamento responsivo
- [ ] Documentar uso e variações
