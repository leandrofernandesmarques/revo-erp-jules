# Análise do Módulo Relatórios - ERP Revo

## Estrutura Geral

O módulo "Relatórios" do ERP Revo apresenta uma interface organizada para acesso aos diversos relatórios disponíveis no sistema, agrupados por categorias. A tela é composta por um cabeçalho com o título da seção, filtros por categoria e uma lista de relatórios disponíveis com suas respectivas descrições.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação:

- Título "Relatórios de Cadastros"
- Botão para acessar outros relatórios

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Relatórios de Cadastros</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-outros-relatorios">
      <span class="icone icone-relatorio"></span>
      <span class="texto">outros relatórios</span>
    </button>
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

.botao-secundario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao .icone {
  margin-right: 8px;
}
```

### Filtros por Categoria

Os filtros permitem selecionar a categoria de relatórios a serem exibidos:

**Estrutura HTML:**

```html
<div class="filtros-categoria">
  <a href="#" class="filtro-categoria ativo" data-categoria="produtos">
    <span class="texto">produtos</span>
  </a>
  <!-- Outras categorias de relatórios -->
</div>
```

**Estilos CSS:**

```css
.filtros-categoria {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtro-categoria {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  background-color: #ffffff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease, border-color 0.2s ease;
}

.filtro-categoria.ativo {
  background-color: #fff7e6;
  border-color: #fa8c16;
  color: #fa8c16;
}

.filtro-categoria:hover:not(.ativo) {
  background-color: #f5f5f5;
}
```

### Lista de Relatórios

A lista exibe os relatórios disponíveis na categoria selecionada:

**Estrutura HTML:**

```html
<div class="lista-relatorios">
  <a href="#" class="item-relatorio">
    <div class="relatorio-conteudo">
      <h2 class="relatorio-titulo">Relatório de Preços dos Produtos</h2>
      <p class="relatorio-descricao">
        Impressão da lista de preços agrupada por tags.
      </p>
    </div>
  </a>
  <!-- Outros relatórios -->
</div>
```

**Estilos CSS:**

```css
.lista-relatorios {
  padding: 16px 24px;
}

.item-relatorio {
  display: block;
  padding: 16px;
  margin-bottom: 16px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: #ffffff;
  text-decoration: none;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.item-relatorio:hover {
  border-color: #1890ff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.09);
}

.relatorio-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.relatorio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}
```

## Interações JavaScript

### Filtros por Categoria

Os filtros permitem alternar entre diferentes categorias de relatórios:

```javascript
// Código para filtros de categoria
document.querySelectorAll(".filtro-categoria").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-categoria").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Carrega os relatórios da categoria selecionada
    const categoria = this.getAttribute("data-categoria");
    carregarRelatoriosCategoria(categoria);
  });
});

function carregarRelatoriosCategoria(categoria) {
  // Lógica para carregar relatórios da categoria selecionada
  fetch(`/api/relatorios?categoria=${categoria}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaRelatorios(data);
    });
}

function atualizarListaRelatorios(relatorios) {
  const container = document.querySelector(".lista-relatorios");
  container.innerHTML = "";

  relatorios.forEach((relatorio) => {
    const itemHTML = `
      <a href="#/relatorio/${relatorio.id}" class="item-relatorio">
        <div class="relatorio-conteudo">
          <h2 class="relatorio-titulo">${relatorio.titulo}</h2>
          <p class="relatorio-descricao">${relatorio.descricao}</p>
        </div>
      </a>
    `;

    container.innerHTML += itemHTML;
  });
}
```

### Acesso a Outros Relatórios

O botão "outros relatórios" permite acessar relatórios de outros módulos:

```javascript
// Código para botão de outros relatórios
document
  .querySelector("#btn-outros-relatorios")
  .addEventListener("click", function () {
    // Abre dropdown de módulos
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-modulo="cadastros">Cadastros</a>
    <a href="#" class="dropdown-item" data-modulo="vendas">Vendas</a>
    <a href="#" class="dropdown-item" data-modulo="financeiro">Financeiro</a>
    <a href="#" class="dropdown-item" data-modulo="estoque">Estoque</a>
    <a href="#" class="dropdown-item" data-modulo="producao">Produção</a>
  `;

    // Posiciona o dropdown
    const rect = this.getBoundingClientRect();
    dropdown.style.top = `${rect.bottom}px`;
    dropdown.style.right = `${window.innerWidth - rect.right}px`;

    // Adiciona ao DOM
    document.body.appendChild(dropdown);

    // Adiciona eventos aos itens do dropdown
    dropdown.querySelectorAll(".dropdown-item").forEach((item) => {
      item.addEventListener("click", function (e) {
        e.preventDefault();

        const modulo = this.getAttribute("data-modulo");
        navegarParaModuloRelatorios(modulo);

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !== document.querySelector("#btn-outros-relatorios")
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function navegarParaModuloRelatorios(modulo) {
  // Redireciona para a página de relatórios do módulo selecionado
  window.location.href = `/relatorios_Revo?id=${getModuloId(
    modulo
  )}&nome=${modulo}`;
}

function getModuloId(modulo) {
  // Retorna o ID do módulo com base no nome
  const modulos = {
    cadastros: 1,
    vendas: 2,
    financeiro: 3,
    estoque: 4,
    producao: 5,
  };

  return modulos[modulo] || 1;
}
```

### Acesso aos Relatórios

Ao clicar em um relatório, o sistema abre uma tela de configuração:

```javascript
// Código para acesso aos relatórios
document.addEventListener("click", function (e) {
  const itemRelatorio = e.target.closest(".item-relatorio");

  if (itemRelatorio) {
    e.preventDefault();

    // Extrai o ID do relatório da URL
    const href = itemRelatorio.getAttribute("href");
    const id = href.split("/").pop();

    // Abre a tela de configuração do relatório
    abrirConfiguracaoRelatorio(id);
  }
});

function abrirConfiguracaoRelatorio(id) {
  // Carrega os dados do relatório
  fetch(`/api/relatorios/${id}`)
    .then((response) => response.json())
    .then((relatorio) => {
      // Cria o modal de configuração
      const modal = document.createElement("div");
      modal.classList.add("modal");
      modal.innerHTML = `
        <div class="modal-conteudo">
          <div class="modal-cabecalho">
            <h2 class="modal-titulo">${relatorio.titulo}</h2>
            <button class="botao-fechar">&times;</button>
          </div>
          <div class="modal-corpo">
            <form id="form-relatorio">
              ${gerarCamposConfiguracao(relatorio.campos)}
            </form>
          </div>
          <div class="modal-rodape">
            <div class="formato-opcoes">
              <label class="formato-label">Formato:</label>
              <div class="opcoes-radio">
                <label class="opcao-radio">
                  <input type="radio" name="formato" value="pdf" checked>
                  <span class="texto">PDF</span>
                </label>
                <label class="opcao-radio">
                  <input type="radio" name="formato" value="excel">
                  <span class="texto">Excel</span>
                </label>
                <label class="opcao-radio">
                  <input type="radio" name="formato" value="csv">
                  <span class="texto">CSV</span>
                </label>
              </div>
            </div>
            <div class="acoes-relatorio">
              <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
              <button class="botao botao-primario" id="btn-gerar">Gerar Relatório</button>
            </div>
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

      modal.querySelector("#btn-gerar").addEventListener("click", () => {
        // Coleta os dados do formulário
        const form = document.querySelector("#form-relatorio");
        const formData = new FormData(form);

        // Adiciona o formato selecionado
        const formato = modal.querySelector(
          'input[name="formato"]:checked'
        ).value;
        formData.append("formato", formato);

        // Gera o relatório
        gerarRelatorio(id, formData);

        // Fecha o modal
        document.body.removeChild(modal);
      });
    });
}

function gerarCamposConfiguracao(campos) {
  let html = "";

  campos.forEach((campo) => {
    switch (campo.tipo) {
      case "texto":
        html += `
          <div class="form-grupo">
            <label for="${campo.id}">${campo.label}</label>
            <input type="${campo.tipo === "numero" ? "number" : "text"}" id="${
          campo.id
        }" name="${campo.id}" ${campo.required ? "required" : ""}>
          </div>
        `;
        break;
      case "select":
        html += `
          <div class="form-grupo">
            <label for="${campo.id}">${campo.label}</label>
            <select id="${campo.id}" name="${campo.id}" ${
          campo.required ? "required" : ""
        }>
              <option value="">Selecione...</option>
              ${campo.opcoes
                .map(
                  (opcao) =>
                    `<option value="${opcao.valor}">${opcao.texto}</option>`
                )
                .join("")}
            </select>
          </div>
        `;
        break;
      case "data":
        html += `
          <div class="form-grupo">
            <label for="${campo.id}">${campo.label}</label>
            <input type="date" id="${campo.id}" name="${campo.id}" ${
          campo.required ? "required" : ""
        }>
          </div>
        `;
        break;
      case "checkbox":
        html += `
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="${campo.id}" name="${campo.id}">
              <label for="${campo.id}">${campo.label}</label>
            </div>
          </div>
        `;
        break;
    }
  });

  return html;
}

function gerarRelatorio(id, formData) {
  // Converte FormData para objeto
  const params = {};
  formData.forEach((value, key) => {
    params[key] = value;
  });

  // Constrói a URL com os parâmetros
  const queryString = Object.keys(params)
    .map(
      (key) => `${encodeURIComponent(key)}=${encodeURIComponent(params[key])}`
    )
    .join("&");

  // Abre a URL em uma nova janela/aba
  window.open(`/relatorios/gerar/${id}?${queryString}`, "_blank");
}
```

## Tela de Configuração de Relatório

Quando o usuário clica em um relatório, é aberto um modal para configuração:

**Estrutura HTML:**

```html
<div class="modal">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Relatório de Preços dos Produtos</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <form id="form-relatorio">
        <div class="form-grupo">
          <label for="tag">Tag</label>
          <select id="tag" name="tag">
            <option value="">Todas as tags</option>
            <option value="promocao">Promoção</option>
            <option value="lancamento">Lançamento</option>
            <option value="destaque">Destaque</option>
          </select>
        </div>
        <div class="form-grupo">
          <label for="ordenacao">Ordenação</label>
          <select id="ordenacao" name="ordenacao">
            <option value="nome">Nome</option>
            <option value="preco">Preço</option>
            <option value="codigo">Código</option>
          </select>
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input
              type="checkbox"
              id="mostrar_estoque"
              name="mostrar_estoque"
            />
            <label for="mostrar_estoque">Mostrar quantidade em estoque</label>
          </div>
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input
              type="checkbox"
              id="mostrar_imagens"
              name="mostrar_imagens"
            />
            <label for="mostrar_imagens">Incluir imagens dos produtos</label>
          </div>
        </div>
      </form>
    </div>
    <div class="modal-rodape">
      <div class="formato-opcoes">
        <label class="formato-label">Formato:</label>
        <div class="opcoes-radio">
          <label class="opcao-radio">
            <input type="radio" name="formato" value="pdf" checked />
            <span class="texto">PDF</span>
          </label>
          <label class="opcao-radio">
            <input type="radio" name="formato" value="excel" />
            <span class="texto">Excel</span>
          </label>
          <label class="opcao-radio">
            <input type="radio" name="formato" value="csv" />
            <span class="texto">CSV</span>
          </label>
        </div>
      </div>
      <div class="acoes-relatorio">
        <button class="botao botao-secundario" id="btn-cancelar">
          Cancelar
        </button>
        <button class="botao botao-primario" id="btn-gerar">
          Gerar Relatório
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

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
  max-width: 600px;
  max-height: 90vh;
  overflow-y: auto;
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
  font-size
(Content truncated due to size limit. Use line ranges to read in chunks)
```
