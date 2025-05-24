# Design System - ERP Revo

Este documento define o design system completo para a recriação visual do ERP Revo no Figma, baseado na documentação técnica extraída do sistema original.

## Paleta de Cores

### Cores Primárias

- **Azul Primário**: `#1890ff` - Utilizado em botões primários, links e elementos de destaque
- **Azul Secundário**: `#e6f7ff` - Utilizado em backgrounds de itens selecionados e hovers

### Cores Neutras

- **Preto**: `#000000` - Utilizado raramente, apenas em textos com ênfase especial
- **Cinza Escuro**: `#333333` - Utilizado em textos principais
- **Cinza Médio**: `#666666` - Utilizado em textos secundários e subtextos
- **Cinza Claro**: `#999999` - Utilizado em textos terciários, placeholders e legendas
- **Cinza Muito Claro**: `#f5f5f5` - Utilizado em backgrounds secundários
- **Cinza Borda**: `#e0e0e0` - Utilizado em bordas e separadores
- **Cinza Borda Leve**: `#f0f0f0` - Utilizado em bordas internas de cards
- **Branco**: `#ffffff` - Utilizado em backgrounds principais

### Cores de Estado

- **Sucesso**: `#52c41a` - Verde utilizado para indicar sucesso ou status positivo
- **Alerta**: `#faad14` - Amarelo utilizado para indicar avisos ou atenção
- **Erro**: `#f5222d` - Vermelho utilizado para indicar erros ou problemas
- **Informação**: `#1890ff` - Azul utilizado para indicar informações (mesmo que o primário)

## Tipografia

### Família de Fonte

- **Principal**: Roboto, sans-serif
- **Alternativa**: Arial, Helvetica, sans-serif (fallback)

### Tamanhos de Fonte

- **Título Principal (h1)**: 20px, peso 500
- **Título Secundário (h2)**: 18px, peso 500
- **Título Terciário (h3)**: 16px, peso 500
- **Texto Normal**: 14px, peso 400
- **Texto Pequeno**: 12px, peso 400
- **Texto Muito Pequeno**: 11px, peso 400

### Pesos de Fonte

- **Regular**: 400
- **Médio**: 500
- **Negrito**: 700

### Estilos de Texto

- **Título de Página**: 20px, peso 500, cor #333333
- **Título de Card**: 16px, peso 500, cor #333333
- **Subtítulo**: 14px, peso 500, cor #666666
- **Texto de Parágrafo**: 14px, peso 400, cor #333333
- **Texto Secundário**: 14px, peso 400, cor #666666
- **Legenda**: 12px, peso 400, cor #999999
- **Link**: 14px, peso 400, cor #1890ff, sem sublinhado (sublinhado apenas no hover)
- **Breadcrumb**: 14px, peso 400, cor #666666

## Espaçamento e Grid

### Sistema de Grid

- **Colunas**: 12 colunas
- **Largura Máxima**: 1200px
- **Gutters**: 24px (espaço entre colunas)
- **Margens Laterais**: 24px (em telas grandes)

### Sistema de Espaçamento

- **4px**: Espaçamento mínimo entre elementos relacionados
- **8px**: Espaçamento padrão entre elementos relacionados
- **12px**: Espaçamento médio entre elementos
- **16px**: Espaçamento padrão para padding interno de componentes
- **24px**: Espaçamento grande entre seções
- **32px**: Espaçamento entre grupos de conteúdo
- **48px**: Espaçamento entre seções principais

### Layout Base

- **Menu Lateral**: Largura de 240px (expandido) ou 64px (recolhido)
- **Cabeçalho**: Altura de 64px
- **Área de Filtros**: Altura variável, mínimo de 56px
- **Área de Conteúdo**: Ocupando o espaço restante

## Componentes

### Botões

#### Botão Primário

- **Background**: #1890ff
- **Texto**: #ffffff, 14px, peso 500
- **Padding**: 8px 16px
- **Border-radius**: 4px
- **Estados**:
  - **Hover**: Escurecer 10%
  - **Ativo**: Escurecer 15%
  - **Desabilitado**: Opacidade 50%

#### Botão Secundário

- **Background**: #ffffff
- **Texto**: #1890ff, 14px, peso 500
- **Borda**: 1px solid #1890ff
- **Padding**: 8px 16px
- **Border-radius**: 4px
- **Estados**:
  - **Hover**: Background #e6f7ff
  - **Ativo**: Background #d9f0ff
  - **Desabilitado**: Opacidade 50%

#### Botão Terciário

- **Background**: #f5f5f5
- **Texto**: #333333, 14px, peso 400
- **Padding**: 8px 16px
- **Border-radius**: 4px
- **Estados**:
  - **Hover**: Background #e8e8e8
  - **Ativo**: Background #d9d9d9
  - **Desabilitado**: Opacidade 50%

#### Botão de Ícone

- **Background**: Transparente
- **Ícone**: #666666, 20px
- **Padding**: 8px
- **Border-radius**: 4px
- **Estados**:
  - **Hover**: Background #f5f5f5
  - **Ativo**: Background #e8e8e8
  - **Desabilitado**: Opacidade 50%

### Campos de Formulário

#### Campo de Texto

- **Altura**: 32px
- **Padding**: 8px 12px
- **Border**: 1px solid #e0e0e0
- **Border-radius**: 4px
- **Texto**: 14px, peso 400, cor #333333
- **Placeholder**: 14px, peso 400, cor #999999
- **Estados**:
  - **Hover**: Border 1px solid #1890ff
  - **Foco**: Border 1px solid #1890ff, box-shadow 0 0 0 2px rgba(24, 144, 255, 0.2)
  - **Erro**: Border 1px solid #f5222d
  - **Desabilitado**: Background #f5f5f5, opacidade 50%

#### Select

- **Altura**: 32px
- **Padding**: 8px 12px
- **Border**: 1px solid #e0e0e0
- **Border-radius**: 4px
- **Texto**: 14px, peso 400, cor #333333
- **Ícone de Seta**: 12px, cor #999999
- **Estados**:
  - **Hover**: Border 1px solid #1890ff
  - **Foco**: Border 1px solid #1890ff, box-shadow 0 0 0 2px rgba(24, 144, 255, 0.2)
  - **Desabilitado**: Background #f5f5f5, opacidade 50%

#### Checkbox

- **Tamanho**: 16px x 16px
- **Border**: 1px solid #e0e0e0
- **Border-radius**: 2px
- **Estados**:
  - **Selecionado**: Background #1890ff, ícone de check branco
  - **Hover**: Border 1px solid #1890ff
  - **Desabilitado**: Background #f5f5f5, opacidade 50%

#### Radio Button

- **Tamanho**: 16px x 16px
- **Border**: 1px solid #e0e0e0
- **Border-radius**: 50%
- **Estados**:
  - **Selecionado**: Border 1px solid #1890ff, círculo interno #1890ff
  - **Hover**: Border 1px solid #1890ff
  - **Desabilitado**: Background #f5f5f5, opacidade 50%

#### Switch

- **Tamanho**: 40px x 20px
- **Border-radius**: 10px
- **Estados**:
  - **Desligado**: Background #e0e0e0, bolinha branca à esquerda
  - **Ligado**: Background #1890ff, bolinha branca à direita
  - **Desabilitado**: Opacidade 50%

### Cards

#### Card Padrão

- **Background**: #ffffff
- **Border-radius**: 8px
- **Box-shadow**: 0 2px 8px rgba(0, 0, 0, 0.1)
- **Estrutura**:
  - **Cabeçalho**: Padding 16px, border-bottom 1px solid #f0f0f0
  - **Conteúdo**: Padding 16px
  - **Rodapé**: Padding 12px 16px, border-top 1px solid #f0f0f0

#### Card de Métrica

- **Background**: #ffffff
- **Border-radius**: 8px
- **Box-shadow**: 0 2px 8px rgba(0, 0, 0, 0.1)
- **Estrutura**:
  - **Cabeçalho**: Padding 16px, border-bottom 1px solid #f0f0f0
  - **Conteúdo**: Padding 16px, valor principal 24px peso 500
  - **Gráfico**: Altura 120px
  - **Rodapé**: Padding 12px 16px, border-top 1px solid #f0f0f0, link centralizado

### Tabelas

#### Tabela Padrão

- **Background**: #ffffff
- **Border**: 1px solid #e0e0e0
- **Border-radius**: 8px (apenas na tabela, não nas células)
- **Cabeçalho**:
  - **Background**: #f5f5f5
  - **Texto**: 14px, peso 500, cor #333333
  - **Padding**: 12px 16px
  - **Border-bottom**: 1px solid #e0e0e0
- **Células**:
  - **Texto**: 14px, peso 400, cor #333333
  - **Padding**: 12px 16px
  - **Border-bottom**: 1px solid #f0f0f0
- **Linhas**:
  - **Hover**: Background #f5f5f5
  - **Selecionada**: Background #e6f7ff
- **Paginação**:
  - **Padding**: 12px 16px
  - **Border-top**: 1px solid #e0e0e0
  - **Texto**: 14px, peso 400, cor #666666

### Navegação

#### Menu Lateral

- **Background**: #f5f5f5
- **Largura**: 240px (expandido) ou 64px (recolhido)
- **Border-right**: 1px solid #e0e0e0
- **Item de Menu**:
  - **Padding**: 12px 16px
  - **Texto**: 14px, peso 400, cor #333333
  - **Ícone**: 20px, cor #666666, margem-direita 12px
  - **Estados**:
    - **Hover**: Background rgba(0, 0, 0, 0.05)
    - **Ativo**: Background #e6f7ff, border-left 3px solid #1890ff
- **Submenu**:
  - **Padding-left**: 36px (16px + 20px para alinhamento com ícone)
  - **Texto**: 14px, peso 400, cor #666666
  - **Estados**:
    - **Hover**: Background rgba(0, 0, 0, 0.05)
    - **Ativo**: Background #e6f7ff, cor texto #1890ff

#### Breadcrumbs

- **Texto**: 14px, peso 400, cor #666666
- **Separador**: Caractere "/", margem 0 8px, cor #999999
- **Link**: 14px, peso 400, cor #666666
- **Link Hover**: Cor #1890ff
- **Último Item**: 14px, peso 400, cor #333333 (não é link)

#### Abas

- **Border-bottom**: 1px solid #e0e0e0
- **Item de Aba**:
  - **Padding**: 12px 16px
  - **Texto**: 14px, peso 400, cor #666666
  - **Estados**:
    - **Hover**: Cor #1890ff
    - **Ativo**: Cor #1890ff, border-bottom 2px solid #1890ff

#### Paginação

- **Texto**: 14px, peso 400, cor #666666
- **Item de Página**:
  - **Tamanho**: 32px x 32px
  - **Border-radius**: 4px
  - **Texto**: 14px, peso 400, cor #666666
  - **Estados**:
    - **Hover**: Background #f5f5f5
    - **Ativo**: Background #1890ff, cor #ffffff

### Notificações e Alertas

#### Toast

- **Background**: #ffffff
- **Border-radius**: 4px
- **Box-shadow**: 0 2px 8px rgba(0, 0, 0, 0.15)
- **Padding**: 12px 16px
- **Texto**: 14px, peso 400, cor #333333
- **Ícone**: 16px, cor variável conforme tipo
- **Tipos**:
  - **Sucesso**: Ícone verde #52c41a
  - **Erro**: Ícone vermelho #f5222d
  - **Aviso**: Ícone amarelo #faad14
  - **Informação**: Ícone azul #1890ff

#### Modal

- **Background**: #ffffff
- **Border-radius**: 8px
- **Box-shadow**: 0 4px 12px rgba(0, 0, 0, 0.15)
- **Estrutura**:
  - **Cabeçalho**: Padding 16px 24px, border-bottom 1px solid #f0f0f0
  - **Conteúdo**: Padding 24px
  - **Rodapé**: Padding 16px 24px, border-top 1px solid #f0f0f0
- **Overlay**: Background rgba(0, 0, 0, 0.45)

#### Tooltip

- **Background**: rgba(0, 0, 0, 0.75)
- **Border-radius**: 4px
- **Padding**: 8px 12px
- **Texto**: 12px, peso 400, cor #ffffff
- **Seta**: 8px, mesma cor do background

### Elementos de Filtro

#### Filtro de Período

- **Background**: #f5f5f5
- **Border-radius**: 4px
- **Padding**: 8px 12px
- **Texto**: 14px, peso 400, cor #333333
- **Ícone**: 16px, cor #666666, margem-direita 8px
- **Estados**:
  - **Hover**: Background #e8e8e8
  - **Ativo**: Background #e6f7ff, cor #1890ff

#### Filtro Avançado

- **Background**: #f5f5f5
- **Border-radius**: 4px
- **Padding**: 8px 12px
- **Texto**: 14px, peso 400, cor #333333
- **Ícone**: 16px, cor #666666, margem-direita 8px
- **Estados**:
  - **Hover**: Background #e8e8e8
  - **Ativo**: Background #e6f7ff, cor #1890ff

### Indicadores

#### Badge

- **Background**: #f5f5f5
- **Border-radius**: 10px
- **Padding**: 0 8px
- **Altura**: 20px
- **Texto**: 12px, peso 400, cor #666666
- **Tipos**:
  - **Primário**: Background #e6f7ff, cor #1890ff
  - **Sucesso**: Background #f6ffed, cor #52c41a
  - **Aviso**: Background #fffbe6, cor #faad14
  - **Erro**: Background #fff1f0, cor #f5222d

#### Tag

- **Background**: #f5f5f5
- **Border-radius**: 4px
- **Padding**: 4px 8px
- **Texto**: 12px, peso 400, cor #666666
- **Estados**:
  - **Removível**: Ícone X à direita
  - **Hover do X**: Cor #333333

#### Status

- **Indicador**: Círculo 8px, cor variável
- **Texto**: 14px, peso 400, cor variável
- **Tipos**:
  - **Ativo**: Cor #52c41a
  - **Inativo**: Cor #999999
  - **Erro**: Cor #f5222d
  - **Processando**: Cor #1890ff

## Ícones

### Sistema de Ícones

- **Tamanho Base**: 20px x 20px
- **Estilo**: Linha fina (stroke 1.5px)
- **Cor Base**: #666666
- **Alinhamento**: Centralizado na área de 20px x 20px

### Ícones Comuns

- **Início**: Ícone de casa
- **Dashboard**: Ícone de gráfico
- **Cadastros**: Ícone de documento
- **Vendas**: Ícone de carrinho de compras
- **Finanças**: Ícone de cifrão
- **Configurações**: Ícone de engrenagem
- **Usuário**: Ícone de pessoa
- **Notificações**: Ícone de sino
- **Ajuda**: Ícone de interrogação
- **Pesquisa**: Ícone de lupa
- **Filtro**: Ícone de funil
- **Adicionar**: Ícone de mais
- **Editar**: Ícone de lápis
- **Excluir**: Ícone de lixeira
- **Expandir**: Ícone de seta para baixo
- **Recolher**: Ícone de seta para cima
- **Próximo**: Ícone de seta para direita
- **Anterior**: Ícone de seta para esquerda
- **Fechar**: Ícone de X
- **Sucesso**: Ícone de check
- **Erro**: Ícone de X em círculo
- **Aviso**: Ícone de exclamação
- **Informação**: Ícone de i em círculo

## Efeitos e Animações

### Transições

- **Hover**: 0.2s ease
- **Fade**: 0.3s ease
- **Expansão/Recolhimento**: 0.3s ease

### Sombras

- **Card**: 0 2px 8px rgba(0, 0, 0, 0.1)
- **Modal**: 0 4px 12px rgba(0, 0, 0, 0.15)
- **Dropdown**: 0 2px 8px rgba(0, 0, 0, 0.15)
- **Tooltip**: 0 2px 8px rgba(0, 0, 0, 0.15)

### Focus

- **Outline**: 0 0 0 2px rgba(24, 144, 255, 0.2)

## Responsividade

### Breakpoints

- **Extra Pequeno**: < 576px (dispositivos móveis)
- **Pequeno**: >= 576px (dispositivos móveis em paisagem)
- **Médio**: >= 768px (tablets)
- **Grande**: >= 992px (desktops)
- **Extra Grande**: >= 1200px (desktops grandes)

### Comportamentos Responsivos

- **Menu Lateral**: Recolhe automaticamente em telas < 992px, oculto em telas < 768px (acessível via botão de menu)
- **Grid**: Ajusta número de colunas conforme tamanho da tela
- **Cards**: Em telas pequenas, ocupam 100% da largura
- **Tabelas**: Rolagem horizontal em telas pequenas
- **Formulários**: Campos ocupam 100% da largura em telas pequenas

## Princípios de Design

### Hierarquia Visual

- Usar tamanhos de fonte, pesos e cores para estabelecer hierarquia clara
- Elementos mais importantes devem ter maior contraste e destaque
- Agrupar informações relacionadas visualmente

### Consistência

- Manter padrões consistentes em toda a interface
- Usar os mesmos componentes para funções similares
- Manter espaçamento e alinhamento consistentes

### Feedback

- Fornecer feedback visual para todas as interações
- Usar estados de hover, foco e ativo para indicar interatividade
- Usar animações sutis para indicar transições

### Eficiência

- Minimizar o número de cliques para tarefas comuns
- Usar atalhos e padrões reconhecíveis
- Priorizar conteúdo mais importante e frequentemente acessado

## Aplicação no Figma

### Organização de Arquivos

- **Página de Design System**: Contém todos os componentes, cores, tipografia e estilos
- **Página de Templates**: Contém layouts base para diferentes tipos de página
- **Páginas de Módulos**: Uma página para cada módulo principal (Dashboard, Cadastros, Vendas, etc.)
- **Página de Protótipos**: Contém fluxos interativos para demonstração

### Componentes no Figma

- Criar componentes para todos os elementos reutilizáveis
- Usar variantes para diferentes estados (normal, hover, ativo, desabilitado)
- Usar propriedades de componente para personalização
- Organizar componentes em seções lógicas

### Estilos no Figma

- Criar estilos de cor para todas as cores do sistema
- Criar estilos de texto para todos os estilos tipográficos
- Criar estilos de efeito para sombras e outros efeitos
- Criar estilos de grade para layouts consistentes

### Nomenclatura

- **Componentes**: [Categoria]/[Nome]/[Variante]
  - Exemplo: "Botões/Primário/Normal"
- **Estilos de Cor**: [Categoria]/[Nome]
  - Exemplo: "Primárias/Azul"
- **Estilos de Texto**: [Categoria]/[Nome]
  - Exemplo: "Títulos/H1"
- **Estilos de Efeito**: [Categoria]/[Nome]
  - Exemplo: "Sombras/Card"
