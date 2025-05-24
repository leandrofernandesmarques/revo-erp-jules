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
document
  .querySelector('.filtro-item[data-filtro="avancado"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre modal de filtros avançados
    const modal = document.createElement("div");
    modal.classList.add("modal");
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
            <select id="categoria" name="categoria">
              <option value="">Todas as categorias</option>
              <option value="eletronicos">Eletrônicos</option>
              <option value="vestuario">Vestuário</option>
              <option value="alimentos">Alimentos</option>
            </select>
          </div>
          <div class="form-grupo">
            <label for="status_estoque">Status de Estoque</label>
            <select id="status_estoque" name="status_estoque">
              <option value="">Todos</option>
              <option value="normal">Normal</option>
              <option value="baixo">Baixo</option>
              <option value="esgotado">Esgotado</option>
            </select>
          </div>
          <div class="form-grupo">
            <label for="fornecedor">Fornecedor</label>
            <select id="fornecedor" name="fornecedor">
              <option value="">Todos os fornecedores</option>
              <option value="1">Fornecedor A</option>
              <option value="2">Fornecedor B</option>
              <option value="3">Fornecedor C</option>
            </select>
          </div>
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="apenas_ativos" name="apenas_ativos">
              <label for="apenas_ativos">Apenas produtos ativos</label>
            </div>
          </div>
        </form>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-limpar-filtros">Limpar Filtros</button>
        <button class="botao botao-primario" id="btn-aplicar-filtros">Aplicar Filtros</button>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal.querySelector("#btn-limpar-filtros").addEventListener("click", () => {
      document.querySelector("#form-filtros").reset();
    });

    modal
      .querySelector("#btn-aplicar-filtros")
      .addEventListener("click", () => {
        // Coleta os dados do formulário
        const form = document.querySelector("#form-filtros");
        const formData = new FormData(form);

        // Converte para objeto
        const filtros = {};
        formData.forEach((value, key) => {
          if (value) {
            filtros[key] = value;
          }
        });

        // Aplica os filtros
        aplicarFiltrosAvancados(filtros);

        // Fecha o modal
        document.body.removeChild(modal);
      });
  });

function aplicarFiltrosAvancados(filtros) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();

  Object.keys(filtros).forEach((key) => {
    params.append(key, filtros[key]);
  });

  // Faz a requisição com os filtros
  fetch(`/api/estoques?${params.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaProdutos(data);
    });
}
```

### Limpar Filtros

O botão de limpar filtros remove todos os filtros aplicados:

```javascript
// Código para limpar filtros
document
  .querySelector('.filtro-item[data-filtro="limpar"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Limpa o campo de pesquisa
    document.querySelector(".input-pesquisa").value = "";

    // Ativa o filtro "Todos"
    document.querySelectorAll(".filtro-tipo").forEach((f) => {
      f.classList.remove("ativo");
    });
    document
      .querySelector('.filtro-tipo[data-tipo="todos"]')
      .classList.add("ativo");

    // Carrega todos os produtos
    fetch("/api/estoques")
      .then((response) => response.json())
      .then((data) => {
        atualizarListaProdutos(data);
      });
  });
```

### Inventário de Estoque

O botão de inventário abre um modal para realizar contagem de estoque:

```javascript
// Código para inventário de estoque
document
  .querySelector("#btn-inventario")
  .addEventListener("click", function () {
    // Abre modal de inventário
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo modal-grande">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Inventário de Estoque</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="inventario-opcoes">
          <div class="opcao-inventario">
            <h3 class="opcao-titulo">Inventário Completo</h3>
            <p class="opcao-descricao">Realize a contagem de todos os produtos do estoque.</p>
            <button class="botao botao-primario" id="btn-inventario-completo">Iniciar Inventário Completo</button>
          </div>
          <div class="opcao-inventario">
            <h3 class="opcao-titulo">Inventário Parcial</h3>
            <p class="opcao-descricao">Selecione categorias ou produtos específicos para contagem.</p>
            <button class="botao botao-secundario" id="btn-inventario-parcial">Iniciar Inventário Parcial</button>
          </div>
        </div>
        <div class="inventario-info">
          <p class="info-texto">
            <span class="icone icone-info"></span>
            O inventário irá gerar um relatório para contagem física dos produtos. Após a contagem, você poderá ajustar os valores no sistema.
          </p>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal.querySelector("#btn-cancelar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-inventario-completo")
      .addEventListener("click", () => {
        iniciarInventarioCompleto();
        document.body.removeChild(modal);
      });

    modal
      .querySelector("#btn-inventario-parcial")
      .addEventListener("click", () => {
        abrirModalInventarioParcial();
        document.body.removeChild(modal);
      });
  });

function iniciarInventarioCompleto() {
  // Redireciona para a página de inventário completo
  window.location.href = "/estoques/inventario/completo";
}

function abrirModalInventarioParcial() {
  // Abre modal para seleção de produtos para inventário parcial
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo modal-grande">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Inventário Parcial - Selecionar Produtos</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="categoria_inventario">Filtrar por Categoria</label>
          <select id="categoria_inventario" name="categoria_inventario">
            <option value="">Todas as categorias</option>
            <option value="eletronicos">Eletrônicos</option>
            <option value="vestuario">Vestuário</option>
            <option value="alimentos">Alimentos</option>
          </select>
        </div>
        <div class="lista-selecao-produtos">
          <!-- Lista de produtos para seleção -->
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-parcial">Cancelar</button>
        <button class="botao botao-primario" id="btn-iniciar-parcial">Iniciar Inventário</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Carrega a lista de produtos
  carregarProdutosParaInventario();

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-parcial").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-iniciar-parcial").addEventListener("click", () => {
    // Coleta os produtos selecionados
    const produtosSelecionados = Array.from(
      document.querySelectorAll(".checkbox-produto:checked")
    ).map((checkbox) => checkbox.value);

    if (produtosSelecionados.length > 0) {
      iniciarInventarioParcial(produtosSelecionados);
      document.body.removeChild(modal);
    } else {
      alert(
        "Selecione pelo menos um produto para iniciar o inventário parcial."
      );
    }
  });

  // Adiciona evento ao filtro de categoria
  modal
    .querySelector("#categoria_inventario")
    .addEventListener("change", function () {
      carregarProdutosParaInventario(this.value);
    });
}

function carregarProdutosParaInventario(categoria = "") {
  // Constrói a URL com os parâmetros
  let url = "/api/produtos";

  if (categoria) {
    url += `?categoria=${categoria}`;
  }

  // Carrega os produtos
  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      const listaContainer = document.querySelector(".lista-selecao-produtos");
      listaContainer.innerHTML = "";

      data.forEach((produto) => {
        const itemHTML = `
          <div class="item-selecao-produto">
            <label class="checkbox-container">
              <input type="checkbox" class="checkbox-produto" value="${produto.id}">
              <span class="checkbox-texto">${produto.nome}</span>
            </label>
            <div class="produto-info-mini">
              <span class="produto-sku">${produto.sku}</span>
              <span class="produto-estoque">${produto.estoque} un</span>
            </div>
          </div>
        `;

        listaContainer.innerHTML += itemHTML;
      });
    });
}

function iniciarInventarioParcial(produtosIds) {
  // Redireciona para a página de inventário parcial com os produtos selecionados
  const idsParam = produtosIds.join(",");
  window.location.href = `/estoques/inventario/parcial?produtos=${idsParam}`;
}
```

### Gerenciar Produtos

O botão de gerenciar produtos permite realizar operações em lote:

```javascript
// Código para gerenciar produtos
document.querySelector("#btn-gerenciar").addEventListener("click", function () {
  // Abre modal de gerenciamento
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Gerenciar Produtos</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="opcoes-gerenciamento">
          <button class="botao-opcao" id="btn-ajustar-estoque">
            <span class="icone icone-ajustar"></span>
            <span class="texto">Ajustar Estoque</span>
          </button>
          <button class="botao-opcao" id="btn-transferir-estoque">
            <span class="icone icone-transferir"></span>
            <span class="texto">Transferir Estoque</span>
          </button>
          <button class="botao-opcao" id="btn-definir-minimo">
            <span class="icone icone-minimo"></span>
            <span class="texto">Definir Estoque Mínimo</span>
          </button>
          <button class="botao-opcao" id="btn-exportar-estoque">
            <span class="icone icone-exportar"></span>
            <span class="texto">Exportar Estoque</span>
          </button>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-gerenciar">Cancelar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-gerenciar")
    .addEventListener("click", () => {
      document.body.removeChild(modal);
    });

  modal.querySelector("#btn-ajustar-estoque").addEventListener("click", () => {
    abrirModalAjustarEstoque();
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-transferir-estoque")
    .addEventListener("click", () => {
      abrirModalTransferirEstoque();
      document.body.removeChild(modal);
    });

  modal.querySelector("#btn-definir-minimo").addEventListener("click", () => {
    abrirModalDefinirEstoqueMinimo();
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-exportar-estoque").addEventListener("click", () => {
    exportarEstoque();
    document.body.removeChild(modal);
  });
});

function abrirModalAjustarEstoque() {
  // Abre modal para ajuste de estoque
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Ajustar Estoque</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="produto_ajuste">Produto</label>
          <select id="produto_ajuste" name="produto_ajuste" required>
            <option value="">Selecione um produto</option>
            <!-- Opções de produtos serão carregadas dinamicamente -->
          </select>
        </div>
        <div class="form-grupo">
          <label for="tipo_ajuste">Tipo de Ajuste</label>
          <select id="tipo_ajuste" name="tipo_ajuste" required>
            <option value="entrada">Entrada de Estoque</option>
            <option value="saida">Saída de Estoque</option>
            <option value="definir">Definir Valor</option>
          </select>
        </div>
        <div class="form-grupo">
          <label for="quantidade_ajuste">Quantidade</label>
          <input type="number" id="quantidade_ajuste" name="quantidade_ajuste" min="0" step="1" required>
        </div>
        <div class="form-grupo">
          <label for="motivo_ajuste">Motivo</label>
          <select id="motivo_ajuste" name="motivo_ajuste" required>
            <option value="contagem">Contagem de Estoque</option>
            <option value="avaria">Avaria/Perda</option>
            <option value="devolucao">Devolução</option>
            <option value="outro">Outro</option>
          </select>
        </div>
        <div class="form-grupo">
          <label for="observacao_ajuste">Observação</label>
          <textarea id="observacao_ajuste" name="observacao_ajuste" rows="3"></textarea>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-ajuste">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar-ajuste">Confirmar Ajuste</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Carrega a lista de produtos
  carregarProdutosParaAjuste();

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-ajuste").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-confirmar-ajuste").addEventListener("click", () => {
    // Coleta os dados do formulário
    const produtoId = document.querySelector("#produto_ajuste").value;
    const tipoAjuste = document.querySelector("#tipo_ajuste").value;
    const quantidade = document.querySelector("#quantidade_ajuste").value;
    const motivo = document.querySelector("#motivo_ajuste").value;
    const observacao = document.querySelector("#observacao_ajuste").value;

    if (produtoId && tipoAjuste && quantidade) {
      // Realiza o ajuste de estoque
      ajustarEstoque(produtoId, tipoAjuste, quantidade, motivo, observacao);
      document.body.removeChild(modal);
    } else {
      alert("Preencha todos os campos obrigatórios.");
    }
  });
}

function carregarProdutosParaAjuste() {
  // Carrega a lista de produtos para o select
  fetch("/api/produtos")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#produto_ajuste");

      data.forEach((produto) => {
        const option = document.createElement("option");
        option.value = produto.id;
        option.textContent = `${produto.nome} (${produto.sku}) - Estoque: ${produto.estoque} un`;
        select.appendChild(option);
      });
    });
}

function ajustarEstoque(produtoId, tipoAjuste, quantidade, motivo, observacao) {
  // Envia a requisição para ajustar o estoque
  fetch("/api/estoques/ajustar", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      produto_id: produtoId,
      tipo_ajuste: tipoAjuste,
      quantidade: quantidade,
      motivo: motivo,
      observacao: observacao,
    }),
  })
    .then((response) => response.json())
    .then((data) => {
      // Exibe mensagem de sucesso
      alert(
        `Estoque ajustado com sucesso! Novo estoque: ${data.novo_estoque} un`
      );

      // Atualiza a lista de produtos
      fetch("/api/estoques")
        .then((response) => response.json())
        .then((data) => {
          atualizarListaProdutos(data);
        });
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao ajustar estoque: ${error.message}`);
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .filtros-tipo {
    flex-wrap: wrap;
  }

  .filtro-tipo {
    flex: 1;
    min-width: 100px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .modulo-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 12px;
    width: 100%;
  }

  .filtros-principais {
    flex-wrap: wrap;
  }

  .filtro-item {
    flex: 1;
    min-width: 120px;
  }

  .coluna-estoque-minimo,
  .coluna-status {
    display: none;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .filtro-item {
    min-width: 100%;
  }

  .coluna-sku {
    display: none;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Vermelho (alerta): #f5222d
- Vermelho claro (background alerta): #fff1f0
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 24px
  - Subtítulos: 18px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Badges de Status

```css
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
```

### Barras de Estoque

```css
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

.estoque-barra-preenchimento.baixo {
  background-color: #f5222d;
}

.estoque-barra-preenchimento.medio {
  background-color: #faad14;
}
```

### Modais

```css
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-conteudo {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 500px;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-conteudo.modal-grande {
  max-width: 800px;
}

.modal-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.modal-titulo {
  margin: 0;
  font-size: 18px;
  font-weight: 500;
  color: #333333;
}

.botao-fechar {
  background: none;
  border: none;
  font-size: 20px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}

.modal-rodape {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  padding: 16px 24px;
  border-top: 1px solid #f0f0f0;
}
```

## Fluxos de Navegação

1. **Listagem de Produtos com Estoque**:

   - A tela inicial exibe todos os produtos cadastrados com seus níveis de estoque
   - Filtros permitem refinar a visualização por tipo, categoria ou status
   - Pesquisa permite localizar produtos específicos por nome, código ou GTIN/EAN

2. **Ajuste de Estoque**:

   - Clique no botão "Gerenciar produtos" e seleção da opção "Ajustar Estoque"
   - Preenchimento do formulário com produto, tipo de ajuste, quantidade e motivo
   - Confirmação do ajuste atualiza o estoque do produto

3. **Inventário de Estoque**:

   - Clique no botão "Inventário de estoque"
   - Seleção entre inventário completo ou parcial
   - Para inventário parcial, seleção dos produtos a serem contados
   - Geração de relatório para contagem física
   - Após contagem, ajuste dos valores no sistema

4. **Transferência de Estoque**:

   - Clique no botão "Gerenciar produtos" e seleção da opção "Transferir Estoque"
   - Seleção do produto, origem, destino e quantidade
   - Confirmação da transferência atualiza o estoque em ambos os locais

5. **Definição de Estoque Mínimo**:
   - Clique no botão "Gerenciar produtos" e seleção da opção "Definir Estoque Mínimo"
   - Seleção do produto e definição do valor mínimo
   - Confirmação atualiza o estoque mínimo do produto

## Conclusão

O módulo "Controle de Estoques" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente do estoque de produtos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, ajustes de estoque e inventário de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária, o vermelho para alertas e tons de cinza para criar contraste e hierarquia visual. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para a gestão de estoque, como ajustes, transferências, definição de estoque mínimo e inventário, atendendo às necessidades de negócios que trabalham com controle de produtos físicos.
