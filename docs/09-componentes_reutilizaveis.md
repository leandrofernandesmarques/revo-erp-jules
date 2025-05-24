# Componentes Reutilizáveis e Grids - ERP Revo

Este documento detalha a estrutura e especificações dos componentes reutilizáveis e grids para a recriação visual do ERP Revo no Figma, baseado no design system definido.

## Sistema de Grid

### Grid Base

- **Tipo**: Grid de 12 colunas
- **Largura Máxima**: 1200px
- **Gutters**: 24px (espaço entre colunas)
- **Margens Laterais**: 24px (em telas grandes)
- **Comportamento Responsivo**:
  - **Extra Grande (≥1200px)**: 12 colunas, gutter 24px, margem 24px
  - **Grande (≥992px)**: 12 colunas, gutter 20px, margem 20px
  - **Médio (≥768px)**: 8 colunas, gutter 16px, margem 16px
  - **Pequeno (≥576px)**: 4 colunas, gutter 16px, margem 16px
  - **Extra Pequeno (<576px)**: 4 colunas, gutter 8px, margem 8px

### Layout Base

- **Menu Lateral**: Largura fixa de 240px (expandido) ou 64px (recolhido)
- **Área de Conteúdo**: Largura flexível (viewport - menu lateral)
- **Estrutura Vertical**:
  - **Cabeçalho**: Altura fixa de 64px
  - **Área de Filtros**: Altura variável, mínimo de 56px
  - **Conteúdo Principal**: Altura flexível (viewport - cabeçalho - filtros)

## Componentes de Navegação

### Menu Lateral

**Variantes**:

- **Expandido**: Largura 240px, exibe texto e ícones
- **Recolhido**: Largura 64px, exibe apenas ícones

**Subcomponentes**:

1. **Logo Container**:

   - Altura: 64px
   - Padding: 16px
   - Alinhamento: Centro

2. **Item de Menu**:

   - Altura: 40px
   - Padding: 12px 16px
   - Ícone: 20px, alinhado à esquerda
   - Texto: 14px, peso 400, cor #333333
   - Espaçamento entre ícone e texto: 12px

   **Estados**:

   - **Normal**: Background transparente
   - **Hover**: Background rgba(0, 0, 0, 0.05)
   - **Ativo**: Background #e6f7ff, border-left 3px solid #1890ff, texto #1890ff
   - **Expandido**: Mostra texto e ícone
   - **Recolhido**: Mostra apenas ícone, tooltip no hover

3. **Grupo de Menu**:

   - Título do Grupo: 12px, peso 500, cor #999999, texto em maiúsculas
   - Padding: 8px 16px
   - Margin-top: 16px

4. **Submenu**:

   - Item de Submenu: Mesmo que Item de Menu, mas com padding-left 36px
   - Indicador de Submenu: Ícone de seta à direita do texto

5. **Toggle de Expansão**:
   - Posição: Parte inferior do menu
   - Altura: 40px
   - Padding: 12px 16px
   - Switch: 40px x 20px
   - Texto: 14px, peso 400, cor #666666

### Cabeçalho

**Variantes**:

- **Padrão**: Com breadcrumbs e título
- **Simples**: Apenas com título
- **Detalhado**: Com breadcrumbs, título e subtítulo

**Subcomponentes**:

1. **Container**:

   - Altura: 64px
   - Padding: 16px 24px
   - Background: #ffffff
   - Border-bottom: 1px solid #e0e0e0
   - Display: Flex, justify-content: space-between

2. **Área de Navegação**:

   - Breadcrumbs: 14px, peso 400, cor #666666
   - Separador: "/", margin 0 8px
   - Título: 20px, peso 500, cor #333333
   - Subtítulo (opcional): 14px, peso 400, cor #666666

3. **Ações Rápidas**:
   - Container: Display flex, gap 8px
   - Botão de Ícone: 32px x 32px, border-radius 50%
   - Ícones: 20px, cor #666666

### Abas de Navegação

**Variantes**:

- **Horizontal**: Abas alinhadas horizontalmente
- **Vertical**: Abas alinhadas verticalmente (para painéis laterais)

**Subcomponentes**:

1. **Container**:

   - Border-bottom: 1px solid #e0e0e0
   - Display: Flex

2. **Item de Aba**:

   - Padding: 12px 16px
   - Texto: 14px, peso 400
   - Cursor: Pointer

   **Estados**:

   - **Normal**: Cor #666666
   - **Hover**: Cor #1890ff
   - **Ativo**: Cor #1890ff, border-bottom 2px solid #1890ff

### Breadcrumbs

**Variantes**:

- **Padrão**: Com separadores "/"
- **Com Ícones**: Inclui ícones antes de cada item

**Subcomponentes**:

1. **Container**:

   - Display: Flex, align-items: center

2. **Item**:

   - Texto: 14px, peso 400, cor #666666
   - Ícone (opcional): 14px, cor #666666, margin-right 4px

   **Estados**:

   - **Normal**: Cor #666666
   - **Hover**: Cor #1890ff
   - **Último Item**: Cor #333333, não clicável

3. **Separador**:
   - Texto: "/"
   - Margin: 0 8px
   - Cor: #999999

### Paginação

**Variantes**:

- **Padrão**: Números de página e navegação
- **Simples**: Apenas botões anterior/próximo

**Subcomponentes**:

1. **Container**:

   - Display: Flex, align-items: center
   - Padding: 12px 0
   - Gap: 8px

2. **Item de Página**:

   - Tamanho: 32px x 32px
   - Border-radius: 4px
   - Texto: 14px, peso 400
   - Display: Flex, justify-content: center, align-items: center

   **Estados**:

   - **Normal**: Background transparente, cor #666666
   - **Hover**: Background #f5f5f5
   - **Ativo**: Background #1890ff, cor #ffffff

3. **Botão Anterior/Próximo**:

   - Tamanho: 32px x 32px
   - Border-radius: 4px
   - Ícone: 14px

   **Estados**:

   - **Normal**: Background transparente, cor #666666
   - **Hover**: Background #f5f5f5
   - **Desabilitado**: Cor #d9d9d9, cursor not-allowed

## Componentes de Entrada

### Botões

**Variantes**:

1. **Primário**:

   - Background: #1890ff
   - Texto: #ffffff, 14px, peso 500
   - Border-radius: 4px
   - Padding: 8px 16px
   - Altura: 32px

   **Estados**:

   - **Normal**: Background #1890ff
   - **Hover**: Background mais escuro 10%
   - **Ativo**: Background mais escuro 15%
   - **Desabilitado**: Opacidade 50%
   - **Com Ícone**: Ícone à esquerda ou direita do texto
   - **Apenas Ícone**: Padding igual em todos os lados

2. **Secundário**:

   - Background: #ffffff
   - Texto: #1890ff, 14px, peso 500
   - Border: 1px solid #1890ff
   - Border-radius: 4px
   - Padding: 8px 16px
   - Altura: 32px

   **Estados**:

   - **Normal**: Background #ffffff, border #1890ff
   - **Hover**: Background #e6f7ff
   - **Ativo**: Background #d9f0ff
   - **Desabilitado**: Opacidade 50%
   - **Com Ícone**: Ícone à esquerda ou direita do texto
   - **Apenas Ícone**: Padding igual em todos os lados

3. **Terciário**:

   - Background: #f5f5f5
   - Texto: #333333, 14px, peso 400
   - Border: none
   - Border-radius: 4px
   - Padding: 8px 16px
   - Altura: 32px

   **Estados**:

   - **Normal**: Background #f5f5f5
   - **Hover**: Background #e8e8e8
   - **Ativo**: Background #d9d9d9
   - **Desabilitado**: Opacidade 50%
   - **Com Ícone**: Ícone à esquerda ou direita do texto
   - **Apenas Ícone**: Padding igual em todos os lados

4. **Link**:

   - Background: transparente
   - Texto: #1890ff, 14px, peso 400
   - Padding: 0

   **Estados**:

   - **Normal**: Cor #1890ff
   - **Hover**: Cor mais escura 10%, text-decoration underline
   - **Ativo**: Cor mais escura 15%
   - **Desabilitado**: Opacidade 50%

5. **Perigo**:

   - Background: #f5222d
   - Texto: #ffffff, 14px, peso 500
   - Border-radius: 4px
   - Padding: 8px 16px
   - Altura: 32px

   **Estados**:

   - **Normal**: Background #f5222d
   - **Hover**: Background mais escuro 10%
   - **Ativo**: Background mais escuro 15%
   - **Desabilitado**: Opacidade 50%

**Tamanhos**:

- **Pequeno**: Altura 24px, padding 4px 8px, texto 12px
- **Médio** (padrão): Altura 32px, padding 8px 16px, texto 14px
- **Grande**: Altura 40px, padding 12px 20px, texto 16px

### Campos de Texto

**Variantes**:

1. **Padrão**:

   - Altura: 32px
   - Padding: 8px 12px
   - Border: 1px solid #e0e0e0
   - Border-radius: 4px
   - Texto: 14px, peso 400, cor #333333
   - Placeholder: 14px, peso 400, cor #999999

   **Estados**:

   - **Normal**: Border #e0e0e0
   - **Hover**: Border #1890ff
   - **Foco**: Border #1890ff, box-shadow 0 0 0 2px rgba(24, 144, 255, 0.2)
   - **Erro**: Border #f5222d
   - **Desabilitado**: Background #f5f5f5, opacidade 50%
   - **Com Ícone**: Ícone à esquerda ou direita
   - **Com Prefixo/Sufixo**: Texto ou elemento adicional antes/depois do input

2. **Pesquisa**:

   - Altura: 32px
   - Padding: 8px 12px
   - Border: 1px solid #e0e0e0
   - Border-radius: 4px
   - Texto: 14px, peso 400, cor #333333
   - Ícone de Lupa: À direita

   **Estados**:

   - Mesmos do campo padrão
   - **Com Botão de Limpar**: Aparece quando há texto

3. **Área de Texto**:

   - Min-height: 80px
   - Padding: 8px 12px
   - Border: 1px solid #e0e0e0
   - Border-radius: 4px
   - Texto: 14px, peso 400, cor #333333
   - Resize: Vertical

   **Estados**:

   - Mesmos do campo padrão

**Tamanhos**:

- **Pequeno**: Altura 24px, padding 4px 8px, texto 12px
- **Médio** (padrão): Altura 32px, padding 8px 12px, texto 14px
- **Grande**: Altura 40px, padding 12px 16px, texto 14px

### Select

**Variantes**:

1. **Padrão**:

   - Altura: 32px
   - Padding: 8px 12px
   - Border: 1px solid #e0e0e0
   - Border-radius: 4px
   - Texto: 14px, peso 400, cor #333333
   - Ícone de Seta: À direita

   **Estados**:

   - **Normal**: Border #e0e0e0
   - **Hover**: Border #1890ff
   - **Foco**: Border #1890ff, box-shadow 0 0 0 2px rgba(24, 144, 255, 0.2)
   - **Erro**: Border #f5222d
   - **Desabilitado**: Background #f5f5f5, opacidade 50%
   - **Aberto**: Border #1890ff, ícone de seta invertido

2. **Múltipla Seleção**:

   - Altura: Min-height 32px
   - Padding: 4px 8px
   - Border: 1px solid #e0e0e0
   - Border-radius: 4px
   - Tags: Dentro do campo para itens selecionados

   **Estados**:

   - Mesmos do select padrão

**Dropdown**:

- Background: #ffffff
- Border: 1px solid #e0e0e0
- Border-radius: 4px
- Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15)
- Max-height: 256px
- Overflow: Auto

**Item de Dropdown**:

- Padding: 8px 12px
- Texto: 14px, peso 400, cor #333333
- Altura: 32px
- **Estados**:
  - **Normal**: Background transparente
  - **Hover**: Background #f5f5f5
  - **Selecionado**: Background #e6f7ff, cor #1890ff
  - **Desabilitado**: Cor #d9d9d9, cursor not-allowed

### Checkbox

**Variantes**:

1. **Padrão**:

   - Tamanho: 16px x 16px
   - Border: 1px solid #e0e0e0
   - Border-radius: 2px

   **Estados**:

   - **Normal**: Border #e0e0e0, background #ffffff
   - **Hover**: Border #1890ff
   - **Selecionado**: Background #1890ff, ícone de check branco
   - **Desabilitado**: Background #f5f5f5, opacidade 50%
   - **Selecionado e Desabilitado**: Background #1890ff opacidade 50%

2. **Com Texto**:

   - Checkbox: Mesmo que o padrão
   - Texto: 14px, peso 400, cor #333333
   - Gap: 8px

   **Estados**:

   - Mesmos do checkbox padrão

### Radio Button

**Variantes**:

1. **Padrão**:

   - Tamanho: 16px x 16px
   - Border: 1px solid #e0e0e0
   - Border-radius: 50%

   **Estados**:

   - **Normal**: Border #e0e0e0, background #ffffff
   - **Hover**: Border #1890ff
   - **Selecionado**: Border #1890ff, círculo interno #1890ff
   - **Desabilitado**: Background #f5f5f5, opacidade 50%
   - **Selecionado e Desabilitado**: Border e círculo #1890ff opacidade 50%

2. **Com Texto**:

   - Radio: Mesmo que o padrão
   - Texto: 14px, peso 400, cor #333333
   - Gap: 8px

   **Estados**:

   - Mesmos do radio padrão

3. **Grupo de Radio**:
   - Display: Flex
   - Gap: 24px
   - Orientação: Horizontal ou vertical

### Switch

**Variantes**:

1. **Padrão**:

   - Tamanho: 40px x 20px
   - Border-radius: 10px
   - Bolinha: 16px x 16px, border-radius 50%

   **Estados**:

   - **Desligado**: Background #e0e0e0, bolinha branca à esquerda
   - **Ligado**: Background #1890ff, bolinha branca à direita
   - **Desabilitado**: Opacidade 50%

2. **Com Texto**:

   - Switch: Mesmo que o padrão
   - Texto: 14px, peso 400, cor #333333
   - Gap: 8px

   **Estados**:

   - Mesmos do switch padrão

3. **Pequeno**:
   - Tamanho: 28px x 16px
   - Bolinha: 12px x 12px

### Slider

**Variantes**:

1. **Padrão**:

   - Altura da Trilha: 4px
   - Border-radius da Trilha: 2px
   - Tamanho do Handle: 14px x 14px
   - Border-radius do Handle: 50%

   **Estados**:

   - **Normal**: Trilha #e0e0e0, parte preenchida #1890ff, handle #ffffff com borda #1890ff
   - **Hover do Handle**: Box-shadow 0 0 0 4px rgba(24, 144, 255, 0.2)
   - **Arrastando**: Handle maior 16px x 16px
   - **Desabilitado**: Opacidade 50%

2. **Com Marcadores**:

   - Mesmo que o padrão
   - Marcadores: Pequenos traços na trilha
   - Valores: Texto 12px abaixo dos marcadores

3. **Com Input**:
   - Mesmo que o padrão
   - Campo de texto à direita para entrada direta do valor

### DatePicker

**Variantes**:

1. **Padrão**:

   - Campo: Mesmo que campo de texto padrão
   - Ícone: Calendário à direita

   **Estados**:

   - Mesmos do campo de texto padrão

2. **Range**:
   - Dois campos conectados
   - Separador entre os campos

**Calendário Dropdown**:

- Background: #ffffff
- Border: 1px solid #e0e0e0
- Border-radius: 4px
- Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15)
- Padding: 12px

**Cabeçalho do Calendário**:

- Mês/Ano: 14px, peso 500, cor #333333
- Botões de Navegação: Ícones de seta

**Dias da Semana**:

- Texto: 12px, peso 400, cor #999999
- Padding: 8px 0

**Células de Dia**:

- Tamanho: 24px x 24px
- Texto: 14px, peso 400
- Border-radius: 2px
- **Estados**:
  - **Normal**: Background transparente, cor #333333
  - **Hover**: Background #f5f5f5
  - **Selecionado**: Background #1890ff, cor #ffffff
  - **Hoje**: Border 1px solid #1890ff
  - **Desabilitado**: Cor #d9d9d9

## Componentes de Exibição

### Cards

**Variantes**:

1. **Padrão**:

   - Background: #ffffff
   - Border-radius: 8px
   - Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1)
   - Padding: 16px

   **Subcomponentes**:

   - **Cabeçalho**: Padding-bottom 12px, border-bottom 1px solid #f0f0f0
   - **Conteúdo**: Padding-top 16px
   - **Rodapé**: Padding-top 12px, border-top 1px solid #f0f0f0, margin-top 16px

2. **Métrica**:

   - Background: #ffffff
   - Border-radius: 8px
   - Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1)

   **Subcomponentes**:

   - **Cabeçalho**: Padding 16px, border-bottom 1px solid #f0f0f0
   - **Valor Principal**: Font-size 24px, peso 500, padding 16px 16px 8px 16px
   - **Gráfico**: Altura 120px, padding 0 16px 16px 16px
   - **Rodapé**: Padding 12px 16px, border-top 1px solid #f0f0f0, texto centralizado

3. **Ação**:

   - Mesmo que o card padrão
   - Cursor: Pointer
   - Transição: box-shadow 0.2s ease, transform 0.2s ease

   **Estados**:

   - **Hover**: Box-shadow 0 4px 12px rgba(0, 0, 0, 0.15), transform translateY(-2px)
   - **Ativo**: Box-shadow 0 2px 8px rgba(0, 0, 0, 0.1), transform translateY(0)

### Tabelas

**Variantes**:

1. **Padrão**:

   - Background: #ffffff
   - Border: 1px solid #e0e0e0
   - Border-radius: 8px (apenas na tabela, não nas células)

   **Subcomponentes**:

   - **Cabeçalho**: Background #f5f5f5, texto 14px peso 500, padding 12px 16px, border-bottom 1px solid #e0e0e0
   - **Células**: Texto 14px peso 400, padding 12px 16px, border-bottom 1px solid #f0f0f0
   - **Linhas**: Hover background #f5f5f5, selecionada background #e6f7ff
   - **Rodapé**: Padding 12px 16px, border-top 1px solid #e0e0e0

2. **Compacta**:

   - Mesmo que a tabela padrão
   - Células: Padding 8px 16px
   - Texto: 12px

3. **Com Ações**:

   - Mesmo que a tabela padrão
   - Coluna de ações à direita
   - Botões de ação: Ícones ou texto

4. **Expansível**:
   - Mesmo que a tabela padrão
   - Ícone de expansão à esquerda
   - Área expansível abaixo da linha

### Listas

**Variantes**:

1. **Padrão**:

   - Background: #ffffff
   - Border: 1px solid #e0e0e0
   - Border-radius: 8px

   **Subcomponentes**:

   - **Item**: Padding 12px 16px, border-bottom 1px solid #f0f0f0
   - **Último Item**: Sem border-bottom
   - **Estados**: Hover background #f5f5f5, selecionado background #e6f7ff

2. **Com Ações**:

   - Mesmo que a lista padrão
   - Botões de ação à direita

3. **Com Ícones**:

   - Mesmo que a lista padrão
   - Ícone à esquerda do texto

4. **Com Avatares**:
   - Mesmo que a lista padrão
   - Avatar à esquerda do texto
   - Texto: Título e subtítulo

### Tabs

**Variantes**:

1. **Padrão**:

   - Border-bottom: 1px solid #e0e0e0

   **Subcomponentes**:

   - **Tab**: Padding 12px 16px, texto 14px peso 400
   - **Estados**: Normal cor #666666, hover cor #1890ff, ativo cor #1890ff com border-bottom 2px solid #1890ff

2. **Com Ícones**:

   - Mesmo que tabs padrão
   - Ícone acima do texto

3. **Com Cards**:

   - Tabs dentro de cards
   - Border-bottom do card-header

4. **Vertical**:
   - Tabs alinhadas verticalmente
   - (Content truncated due to size limit. Use line ranges to read in chunks)
