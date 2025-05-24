# Análise do Módulo Ferramentas - Importações - ERP Revo

## Estrutura Geral

O módulo "Ferramentas - Importações" do ERP Revo apresenta uma interface para importação de dados em diferentes categorias do sistema. A página está organizada em seções temáticas (Cadastros, Suprimentos, Vendas, Notas Fiscais), cada uma contendo links para diferentes tipos de importações disponíveis.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação, conforme documentado no módulo "Ferramentas - Geral".

### Área de Título e Navegação

A seção superior contém o título da página e links de navegação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Ferramentas</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Ferramentas</h1>
  </div>

  <div class="abas-container">
    <div class="abas-lista">
      <a href="/ferramentas_geral" class="aba-item">
        <span class="aba-texto">Geral</span>
      </a>
      <a href="/ferramentas_importacoes" class="aba-item aba-ativa">
        <span class="aba-texto">Importações</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.cabecalho-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  margin-left: 240px; /* Espaço para o menu lateral */
}

.breadcrumb {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  font-size: 14px;
}

.breadcrumb-item {
  color: #1890ff;
  text-decoration: none;
}

.breadcrumb-item:hover {
  text-decoration: underline;
}

.breadcrumb-separador {
  margin: 0 8px;
  color: #d9d9d9;
}

.breadcrumb-item-atual {
  color: #666666;
}

.cabecalho-titulo {
  margin-bottom: 16px;
}

.titulo-pagina {
  font-size: 24px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.abas-container {
  margin-bottom: 16px;
}

.abas-lista {
  display: flex;
  border-bottom: 1px solid #f0f0f0;
}

.aba-item {
  padding: 12px 16px;
  font-size: 14px;
  font-weight: 500;
  color: #666666;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
}

.aba-item:hover {
  color: #1890ff;
}

.aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.aba-texto {
  display: inline-block;
}
```

### Área de Conteúdo Principal - Categorias de Importação

A área principal da página apresenta as categorias de importação organizadas em seções:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <!-- Seção de Cadastros -->
  <div class="secao-importacao">
    <h2 class="secao-titulo">Cadastros</h2>

    <div class="importacoes-lista">
      <a href="/importacao/contatos" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-contatos"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Contatos</h3>
        </div>
      </a>

      <a href="/importacao/contatos_clientes" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-contatos-clientes"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Contatos dos clientes</h3>
        </div>
      </a>

      <a href="/importacao/produtos" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-produtos"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Produtos</h3>
        </div>
      </a>

      <a href="/importacao/kits_produtos" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-kits"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Kits e Produtos Fabricados</h3>
        </div>
      </a>

      <a href="/importacao/precos_produtos" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-precos"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Preços dos produtos</h3>
        </div>
      </a>
    </div>
  </div>

  <!-- Seção de Suprimentos -->
  <div class="secao-importacao">
    <h2 class="secao-titulo">Suprimentos</h2>

    <div class="importacoes-lista">
      <a href="/importacao/estoque" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-estoque"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Estoque</h3>
        </div>
      </a>

      <a href="/importacao/ordens_compra" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-ordens-compra"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Ordens de Compra</h3>
        </div>
      </a>
    </div>
  </div>

  <!-- Seção de Vendas -->
  <div class="secao-importacao">
    <h2 class="secao-titulo">Vendas</h2>

    <div class="importacoes-lista">
      <a href="/importacao/pedidos_venda" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-pedidos"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Pedidos de Venda</h3>
        </div>
      </a>

      <a href="/importacao/propostas_comerciais" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-propostas"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Propostas Comerciais</h3>
        </div>
      </a>

      <a href="/importacao/informacoes_envio" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-envio"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Atualizar informações de envio</h3>
        </div>
      </a>
    </div>
  </div>

  <!-- Seção de Notas Fiscais -->
  <div class="secao-importacao">
    <h2 class="secao-titulo">Notas Fiscais</h2>

    <div class="importacoes-lista">
      <a href="/importacao/notas_fiscais" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-notas"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Notas Fiscais</h3>
        </div>
      </a>

      <a href="/importacao/notas_servico" class="importacao-item">
        <div class="importacao-icone">
          <span class="icone icone-notas-servico"></span>
        </div>
        <div class="importacao-info">
          <h3 class="importacao-titulo">Notas de Serviço</h3>
        </div>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  margin-left: 240px; /* Espaço para o menu lateral */
  background-color: #f5f5f5;
  min-height: calc(100vh - 120px); /* Altura total menos cabeçalho */
}

.secao-importacao {
  margin-bottom: 32px;
}

.secao-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 16px 0;
  padding-bottom: 8px;
  border-bottom: 1px solid #e8e8e8;
}

.importacoes-lista {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 16px;
}

.importacao-item {
  display: flex;
  align-items: center;
  padding: 16px;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  transition: box-shadow 0.2s ease, transform 0.2s ease;
  text-decoration: none;
  color: inherit;
}

.importacao-item:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.importacao-icone {
  margin-right: 16px;
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f0f7ff;
  border-radius: 8px;
  color: #1890ff;
}

.importacao-info {
  flex: 1;
}

.importacao-titulo {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.icone {
  font-size: 16px;
}

/* Ícones específicos para cada tipo de importação */
.icone-contatos::before {
  content: "\e910"; /* Código do ícone de contatos */
}

.icone-contatos-clientes::before {
  content: "\e911"; /* Código do ícone de contatos de clientes */
}

.icone-produtos::before {
  content: "\e912"; /* Código do ícone de produtos */
}

.icone-kits::before {
  content: "\e913"; /* Código do ícone de kits */
}

.icone-precos::before {
  content: "\e914"; /* Código do ícone de preços */
}

.icone-estoque::before {
  content: "\e915"; /* Código do ícone de estoque */
}

.icone-ordens-compra::before {
  content: "\e916"; /* Código do ícone de ordens de compra */
}

.icone-pedidos::before {
  content: "\e917"; /* Código do ícone de pedidos */
}

.icone-propostas::before {
  content: "\e918"; /* Código do ícone de propostas */
}

.icone-envio::before {
  content: "\e919"; /* Código do ícone de envio */
}

.icone-notas::before {
  content: "\e920"; /* Código do ícone de notas fiscais */
}

.icone-notas-servico::before {
  content: "\e921"; /* Código do ícone de notas de serviço */
}
```

## Interações JavaScript

### Navegação entre Abas

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const abaGeral = document.querySelector('a[href="/ferramentas_geral"]');
  const abaImportacoes = document.querySelector(
    'a[href="/ferramentas_importacoes"]'
  );

  // Função para alternar entre abas
  function alternarAba(event, abaAtiva) {
    event.preventDefault();

    // Remover classe ativa de todas as abas
    document.querySelectorAll(".aba-item").forEach(function (aba) {
      aba.classList.remove("aba-ativa");
    });

    // Adicionar classe ativa à aba clicada
    abaAtiva.classList.add("aba-ativa");

    // Carregar conteúdo correspondente
    const url = abaAtiva.getAttribute("href");

    // Simular navegação SPA
    history.pushState({}, "", url);

    // Carregar conteúdo via AJAX (simulado)
    if (url === "/ferramentas_geral") {
      carregarFerramentasGerais();
    } else if (url === "/ferramentas_importacoes") {
      carregarFerramentasImportacoes();
    }
  }

  // Função para carregar ferramentas gerais
  function carregarFerramentasGerais() {
    // Em um cenário real, aqui seria feita uma requisição AJAX
    console.log("Carregando ferramentas gerais...");

    // Simular carregamento de conteúdo
    const conteudoContainer = document.querySelector(".conteudo-container");
    // Conteúdo seria atualizado aqui
  }

  // Função para carregar ferramentas de importações
  function carregarFerramentasImportacoes() {
    // Em um cenário real, aqui seria feita uma requisição AJAX
    console.log("Carregando ferramentas de importações...");

    // Simular carregamento de conteúdo
    const conteudoContainer = document.querySelector(".conteudo-container");
    // Conteúdo seria atualizado aqui
  }

  // Adicionar event listeners
  if (abaGeral) {
    abaGeral.addEventListener("click", function (event) {
      alternarAba(event, this);
    });
  }

  if (abaImportacoes) {
    abaImportacoes.addEventListener("click", function (event) {
      alternarAba(event, this);
    });
  }
});
```

### Efeitos de Hover nos Itens de Importação

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const importacaoItems = document.querySelectorAll(".importacao-item");

  // Adicionar efeitos de hover
  importacaoItems.forEach(function (item) {
    item.addEventListener("mouseenter", function () {
      this.style.boxShadow = "0 4px 8px rgba(0, 0, 0, 0.1)";
      this.style.transform = "translateY(-2px)";
    });

    item.addEventListener("mouseleave", function () {
      this.style.boxShadow = "0 1px 2px rgba(0, 0, 0, 0.05)";
      this.style.transform = "translateY(0)";
    });
  });
});
```

### Filtro de Importações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const campoBusca = document.getElementById("busca-importacoes");
  const importacaoItems = document.querySelectorAll(".importacao-item");
  const secaoImportacao = document.querySelectorAll(".secao-importacao");

  // Função para filtrar importações
  function filtrarImportacoes() {
    const termoBusca = campoBusca.value.toLowerCase().trim();

    if (!termoBusca) {
      // Se não houver termo de busca, mostrar todos os itens
      importacaoItems.forEach(function (item) {
        item.style.display = "flex";
      });

      secaoImportacao.forEach(function (secao) {
        secao.style.display = "block";
      });

      return;
    }

    // Filtrar itens com base no termo de busca
    importacaoItems.forEach(function (item) {
      const titulo = item
        .querySelector(".importacao-titulo")
        .textContent.toLowerCase();

      if (titulo.includes(termoBusca)) {
        item.style.display = "flex";
      } else {
        item.style.display = "none";
      }
    });

    // Ocultar seções vazias
    secaoImportacao.forEach(function (secao) {
      const itensVisiveis = secao.querySelectorAll(
        '.importacao-item[style="display: flex;"]'
      );

      if (itensVisiveis.length === 0) {
        secao.style.display = "none";
      } else {
        secao.style.display = "block";
      }
    });
  }

  // Adicionar event listener para o campo de busca
  if (campoBusca) {
    campoBusca.addEventListener("input", filtrarImportacoes);
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .importacoes-lista {
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .menu-lateral {
    width: 64px;
    overflow: hidden;
  }

  .menu-texto {
    display: none;
  }

  .menu-icone {
    margin-right: 0;
  }

  .cabecalho-container,
  .conteudo-container {
    margin-left: 64px;
  }

  .importacoes-lista {
    grid-template-columns: 1fr;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .cabecalho-container {
    padding: 12px 16px;
  }

  .titulo-pagina {
    font-size: 20px;
  }

  .secao-titulo {
    font-size: 16px;
  }

  .importacao-item {
    padding: 12px;
  }

  .importacao-icone {
    width: 24px;
    height: 24px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Azul muito claro (background de ícones): #f0f7ff
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (placeholder): #999999
- Cinza muito claro (bordas): #d9d9d9
- Cinza ultra claro (backgrounds): #f5f5f5
- Cinza separador: #f0f0f0
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos grandes: 24px
  - Títulos médios: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

## Fluxos de Navegação

1. **Acesso ao Módulo Importações**:

   - O usuário acessa o módulo "Ferramentas" através do menu lateral
   - Clica na aba "Importações"
   - O sistema exibe a tela de importações com as diferentes categorias

2. **Navegação entre Categorias**:
   - O usuário visualiza as diferentes categorias de importação (Cadastros, Suprimentos, Vendas, Notas Fiscais)
   - Cada categoria contém links p
     (Content truncated due to size limit. Use line ranges to read in chunks)
