# Análise do Módulo Controle de Estoques - ERP Revo

## Estrutura Geral

O módulo "Controle de Estoques" do ERP Revo apresenta uma interface organizada para gerenciamento de estoque de produtos, com uma estrutura que facilita a visualização, pesquisa e manipulação dos itens. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma área de listagem de produtos com seus respectivos níveis de estoque.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Controle de estoques"
- Botão de inventário de estoque
- Botão para gerenciar produtos
- Menu de ações adicionais

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Controle de estoques</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-inventario">
      <span class="icone icone-inventario"></span>
      <span class="texto">Inventário de estoque</span>
    </button>
    <button class="botao botao-primario" id="btn-gerenciar">
      <span class="icone icone-gerenciar"></span>
      <span class="texto">Gerenciar produtos</span>
    </button>
    <div class="dropdown">
      <button class="botao botao-secundario dropdown-toggle" id="btn-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modulo-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.titulo-modulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.acoes-container {
  display: flex;
  gap: 8px;
}

.botao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao .icone {
  margin-right: 8px;
}

.dropdown {
  position: relative;
}

.dropdown-toggle {
  padding-right: 28px;
}

.dropdown-toggle .icone-seta-baixo {
  position: absolute;
  right: 12px;
  top: 50%;
  transform: translateY(-50%);
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar os produtos por diferentes critérios:

- Campo de texto para pesquisa por nome, código (SKU) ou GTIN/EAN
- Botão de busca
- Opções de visualização (lista/grade)

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por nome, código (SKU) ou GTIN/EAN"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="opcoes-visualizacao">
    <button class="botao-visualizacao ativo" data-view="lista">
      <span class="icone icone-lista"></span>
    </button>
    <button class="botao-visualizacao" data-view="grade">
      <span class="icone icone-grade"></span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.barra-pesquisa {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #f5f5f5;
  border-bottom: 1px solid #e0e0e0;
}

.campo-pesquisa {
  flex: 1;
  position: relative;
  max-width: 600px;
}

.input-pesquisa {
  width: 100%;
  padding: 10px 16px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.input-pesquisa::placeholder {
  color: #999999;
}

.botao-busca {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  cursor: pointer;
  color: #666666;
}

.opcoes-visualizacao {
  display: flex;
  gap: 4px;
}

.botao-visualizacao {
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: white;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  cursor: pointer;
}

.botao-visualizacao.ativo {
  background-color: #1890ff;
  color: white;
  border-color: #1890ff;
}
```

### Filtros de Dados

Os filtros permitem refinar a visualização dos produtos por diferentes critérios:

- Filtros avançados
- Opção para limpar filtros
- Filtro por tipo de produto (Todos, Simples, Kits, Matéria-prima)

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtros-principais">
    <a href="#" class="filtro-item" data-filtro="avancado">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
    </a>
  </div>
  <div class="filtros-tipo">
    <a href="#" class="filtro-tipo ativo" data-tipo="todos">
      <span class="texto">Todos</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="simples">
      <span class="texto">Simples</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="kits">
      <span class="texto">Kits</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="materia-prima">
      <span class="texto">Matéria-prima</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.filtros-container {
  display: flex;
  flex-direction: column;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtros-principais {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  background-color: #f5f5f5;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-item:hover {
  background-color: #e6f7ff;
}

.filtro-item .icone {
  margin-right: 6px;
  font-size: 16px;
}

.filtros-tipo {
  display: flex;
  gap: 4px;
}

.filtro-tipo {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  background-color: #ffffff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease, border-color 0.2s ease;
}

.filtro-tipo.ativo {
  background-color: #f5f5f5;
  border-color: #1890ff;
  color: #1890ff;
}
```

### Área de Resultados

A área de resultados exibe os produtos cadastrados ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="resultados-container">
  <!-- Quando há resultados -->
  <div class="tabela-produtos">
    <!-- Conteúdo da tabela de produtos -->
  </div>

  <!-- Quando não há resultados -->
  <div class="sem-resultados">
    <div class="sem-resultados-conteudo">
      <h2 class="sem-resultados-titulo">
        Sua pesquisa não retornou resultados.
      </h2>
      <p class="sem-resultados-descricao">
        Tente outras opções de pesquisa, tipos de produtos ou remova os filtros.
      </p>
      <div class="sem-resultados-acoes">
        <button class="botao botao-primario">alterar pesquisa</button>
        <button class="botao botao-secundario">limpar filtros</button>
      </div>
      <div class="sem-resultados-ilustracao">
        <!-- Ilustração -->
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.resultados-container {
  flex: 1;
  background-color: #ffffff;
  padding: 24px;
  overflow: auto;
}

.sem-resultados {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 400px;
}

.sem-resultados-conteudo {
  max-width: 600px;
  text-align: center;
  padding: 24px;
  border: 1px solid #f0f0f0;
  border-radius: 8px;
  background-color: #ffffff;
}

.sem-resultados-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.sem-resultados-descricao {
  font-size: 14px;
  color: #666666;
  margin-bottom: 24px;
}

.sem-resultados-acoes {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-bottom: 24px;
}

.sem-resultados-ilustracao {
  margin-top: 24px;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Tabela de Produtos com Estoque

Quando há resultados, a tabela exibe os produtos cadastrados com suas informações de estoque:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-produtos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-produto">Produto</th>
        <th class="coluna-sku">SKU</th>
        <th class="coluna-estoque">Estoque</th>
        <th class="coluna-estoque-minimo">Estoque Mínimo</th>
        <th class="coluna-status">Status</th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-produto">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-produto">
          <div class="produto-info">
            <div class="produto-imagem">
              <img src="caminho/para/imagem.jpg" alt="Nome do Produto" />
            </div>
            <div class="produto-detalhes">
              <div class="produto-nome">Nome do Produto</div>
              <div class="produto-categoria">Categoria do Produto</div>
            </div>
          </div>
        </td>
        <td class="coluna-sku">SKU12345</td>
        <td class="coluna-estoque">
          <div class="estoque-info">
            <div class="estoque-valor">10 un</div>
            <div class="estoque-barra">
              <div
                class="estoque-barra-preenchimento"
                style="width: 60%;"
              ></div>
            </div>
          </div>
        </td>
        <td class="coluna-estoque-minimo">5 un</td>
        <td class="coluna-status">
          <span class="badge badge-normal">Normal</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-editar"></span>
          </button>
          <button class="botao-acao">
            <span class="icone icone-mais"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de produtos -->
    </tbody>
  </table>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  overflow-x: auto;
  background-color: #ffffff;
}

.tabela-produtos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos th,
.tabela-produtos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-produto {
  min-width: 250px;
}

.coluna-sku {
  width: 120px;
}

.coluna-estoque {
  width: 150px;
}

.coluna-estoque-minimo {
  width: 120px;
}

.coluna-status {
  width: 100px;
}

.coluna-acoes {
  width: 80px;
  text-align: right;
}

.produto-info {
  display: flex;
  align-items: center;
}

.produto-imagem {
  width: 40px;
  height: 40px;
  border-radius: 4px;
  overflow: hidden;
  margin-right: 12px;
  background-color: #f5f5f5;
}

.produto-imagem img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.produto-detalhes {
  display: flex;
  flex-direction: column;
}

.produto-nome {
  font-weight: 500;
  color: #333333;
}

.produto-categoria {
  font-size: 12px;
  color: #999999;
  margin-top: 2px;
}

.estoque-info {
  display: flex;
  flex-direction: column;
}

.estoque-valor {
  margin-bottom: 4px;
}

.estoque-barra {
  height: 4px;
  background-color: #f5f5f5;
  border-radius: 2px;
  overflow: hidden;
}

.estoque-barra-preenchimento {
  height: 100%;
  background-color: #1890ff;
  border-radius: 2px;
}

.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.badge-normal {
  background-color: #e6f7ff;
  color: #1890ff;
}

.badge-baixo {
  background-color: #fff1f0;
  color: #f5222d;
}

.badge-esgotado {
  background-color: #f5f5f5;
  color: #999999;
}

.botao-acao {
  width: 28px;
  height: 28px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  color: #666666;
  transition: background-color 0.2s ease;
  margin-left: 4px;
}

.botao-acao:hover {
  background-color: #f5f5f5;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar produtos:

```javascript
// Código para pesquisa de produtos
document
  .querySelector(".input-pesquisa")
  .addEventListener("keyup", function (e) {
    if (e.key === "Enter") {
      realizarPesquisa(this.value);
    }
  });

document.querySelector(".botao-busca").addEventListener("click", function () {
  const termoPesquisa = document.querySelector(".input-pesquisa").value;
  realizarPesquisa(termoPesquisa);
});

function realizarPesquisa(termo) {
  // Lógica para filtrar produtos pelo termo de pesquisa
  fetch(`/api/estoques/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaProdutos(data);
    });
}

// Código para alternar entre visualizações (lista/grade)
document.querySelectorAll(".botao-visualizacao").forEach((botao) => {
  botao.addEventListener("click", function () {
    // Remove classe ativo de todos os botões
    document.querySelectorAll(".botao-visualizacao").forEach((b) => {
      b.classList.remove("ativo");
    });

    // Adiciona classe ativo ao botão clicado
    this.classList.add("ativo");

    // Altera o modo de visualização
    const modo = this.getAttribute("data-view");
    alterarModoVisualizacao(modo);
  });
});

function alterarModoVisualizacao(modo) {
  const container = document.querySelector(".resultados-container");

  if (modo === "grade") {
    container.classList.add("modo-grade");
    container.classList.remove("modo-lista");
  } else {
    container.classList.add("modo-lista");
    container.classList.remove("modo-grade");
  }
}
```

### Filtros por Tipo de Produto

Os filtros por tipo permitem visualizar apenas produtos específicos:

```javascript
// Código para filtrar por tipo de produto
document.querySelectorAll(".filtro-tipo").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-tipo").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por tipo
    const tipo = this.getAttribute("data-tipo");
    filtrarPorTipo(tipo);
  });
});

function filtrarPorTipo(tipo) {
  // Lógica para filtrar produtos por tipo
  let url = "/api/estoques";

  if (tipo !== "todos") {
    url += `?tipo=${tipo}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaProdutos(data);
    });
}
```

### Filtros Avançados

O botão de filtros avançados abre um modal com opções adicionais:

```javascript
// Código para filtros avançados
document.querySelector('.filtro-item[data-filtro="avancado"]').addEventListener('click', function(e) {
  e.preventDefault();

  // Abre modal de filtros avançados
  const modal = document.createElement('div');
  modal.classList.add('modal');
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Filtros Avançados</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <form id="form-filtros">
          <div class="form-grupo">
            <label for="categoria">Categoria</label>

(Content truncated due to size limit. Use line ranges to read in chunks)
```
