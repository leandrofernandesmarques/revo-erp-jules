# Análise do Módulo Embalagens - ERP Revo

## Estrutura Geral

O módulo "Embalagens" do ERP Revo apresenta uma interface organizada para gerenciamento de embalagens utilizadas para envio de produtos, com uma estrutura que facilita a visualização, cadastro e manipulação dos itens. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma tabela de dados com informações das embalagens cadastradas.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Embalagens de produtos"
- Botão para criar embalagens dos Correios
- Botão de inclusão de nova embalagem

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Embalagens de produtos</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-criar-correios">
      <span class="icone icone-correios"></span>
      <span class="texto">Criar embalagens Correios</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir embalagem</span>
    </a>
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
  text-decoration: none;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao .icone {
  margin-right: 8px;
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar as embalagens:

- Campo de texto para pesquisa
- Botão de busca
- Filtro por embalagem

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input type="text" placeholder="Pesquisa..." class="input-pesquisa" />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="embalagem">
      <span class="icone icone-filtro"></span>
      <span class="texto">por embalagem</span>
    </a>
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

.filtros-rapidos {
  display: flex;
  gap: 8px;
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
```

### Tabela de Embalagens

A tabela exibe as embalagens cadastradas com suas informações principais:

- Checkbox para seleção
- Código/ID da embalagem
- Descrição
- Tipo
- Dimensões
- Peso

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-embalagens">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-id">ID</th>
        <th class="coluna-descricao">Descrição</th>
        <th class="coluna-tipo">Tipo</th>
        <th class="coluna-dimensoes">Dimensões</th>
        <th class="coluna-peso">Peso</th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-embalagem">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-id">
          <div class="embalagem-tag">19</div>
        </td>
        <td class="coluna-descricao">Caixa de Encomenda Flex</td>
        <td class="coluna-tipo">Pacote / Caixa</td>
        <td class="coluna-dimensoes">26,00cm x 21,00cm x 1,00cm</td>
        <td class="coluna-peso">0,09 Kg</td>
      </tr>
      <tr class="linha-embalagem">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-id">
          <div class="embalagem-tag">20</div>
        </td>
        <td class="coluna-descricao">Caixa de Encomenda Flex</td>
        <td class="coluna-tipo">Pacote / Caixa</td>
        <td class="coluna-dimensoes">26,00cm x 21,00cm x 2,00cm</td>
        <td class="coluna-peso">0,18 Kg</td>
      </tr>
      <!-- Outras linhas de embalagens -->
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

.tabela-embalagens {
  width: 100%;
  border-collapse: collapse;
}

.tabela-embalagens th,
.tabela-embalagens td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-embalagens th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-id {
  width: 60px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-tipo {
  width: 150px;
}

.coluna-dimensoes {
  width: 200px;
}

.coluna-peso {
  width: 100px;
}

.embalagem-tag {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #722ed1;
  color: white;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}
```

### Paginação

A paginação permite navegar entre as páginas de resultados:

**Estrutura HTML:**

```html
<div class="paginacao">
  <div class="paginacao-info">
    <span class="paginacao-total">74 embalagens</span>
  </div>
  <div class="paginacao-controles">
    <a href="#" class="paginacao-pagina ativo">01</a>
    <a href="#" class="paginacao-pagina">02</a>
    <a href="#" class="paginacao-proxima">
      <span class="icone icone-seta-direita"></span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #e0e0e0;
}

.paginacao-total {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  gap: 4px;
}

.paginacao-pagina {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.paginacao-pagina.ativo {
  background-color: #1890ff;
  color: white;
}

.paginacao-pagina:hover:not(.ativo) {
  background-color: #f5f5f5;
}

.paginacao-proxima {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.paginacao-proxima:hover {
  background-color: #f5f5f5;
}
```

### Botão Voltar ao Topo

Um botão fixo permite voltar ao topo da página:

**Estrutura HTML:**

```html
<button class="botao-voltar-topo" title="Voltar ao topo">
  <span class="icone icone-seta-cima"></span>
</button>
```

**Estilos CSS:**

```css
.botao-voltar-topo {
  position: fixed;
  bottom: 24px;
  right: 24px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #1890ff;
  color: white;
  border: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background-color 0.2s ease;
  z-index: 100;
}

.botao-voltar-topo:hover {
  background-color: #40a9ff;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar embalagens:

```javascript
// Código para pesquisa de embalagens
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
  // Lógica para filtrar embalagens pelo termo de pesquisa
  fetch(`/api/embalagens/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaEmbalagens(data);
    });
}

// Código para filtro por embalagem
document
  .querySelector('.filtro-item[data-filtro="embalagem"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre dropdown de tipos de embalagem
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-tipo="todos">Todos os tipos</a>
    <a href="#" class="dropdown-item" data-tipo="caixa">Caixas</a>
    <a href="#" class="dropdown-item" data-tipo="envelope">Envelopes</a>
    <a href="#" class="dropdown-item" data-tipo="pacote">Pacotes</a>
  `;

    // Posiciona o dropdown
    const rect = this.getBoundingClientRect();
    dropdown.style.top = `${rect.bottom}px`;
    dropdown.style.left = `${rect.left}px`;

    // Adiciona ao DOM
    document.body.appendChild(dropdown);

    // Adiciona eventos aos itens do dropdown
    dropdown.querySelectorAll(".dropdown-item").forEach((item) => {
      item.addEventListener("click", function (e) {
        e.preventDefault();

        const tipo = this.getAttribute("data-tipo");
        filtrarPorTipo(tipo);

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !==
          document.querySelector('.filtro-item[data-filtro="embalagem"]')
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function filtrarPorTipo(tipo) {
  // Lógica para filtrar embalagens por tipo
  let url = "/api/embalagens";

  if (tipo !== "todos") {
    url += `?tipo=${tipo}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaEmbalagens(data);
    });
}
```

### Seleção de Embalagens

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de embalagens
const checkboxTodos = document.querySelector(".checkbox-selecionar-todos");
const checkboxesIndividuais = document.querySelectorAll(".checkbox-selecionar");

checkboxTodos.addEventListener("change", function () {
  const isChecked = this.checked;

  // Marca ou desmarca todos os checkboxes individuais
  checkboxesIndividuais.forEach((checkbox) => {
    checkbox.checked = isChecked;
  });

  // Atualiza o estado de seleção
  atualizarEstadoSelecao();
});

checkboxesIndividuais.forEach((checkbox) => {
  checkbox.addEventListener("change", function () {
    // Verifica se todos estão marcados para atualizar o checkbox geral
    const todosMarcados = Array.from(checkboxesIndividuais).every(
      (cb) => cb.checked
    );
    checkboxTodos.checked = todosMarcados;

    // Atualiza o estado de seleção
    atualizarEstadoSelecao();
  });
});

function atualizarEstadoSelecao() {
  const selecionados = Array.from(checkboxesIndividuais).filter(
    (cb) => cb.checked
  );

  // Atualiza a interface com base na quantidade de itens selecionados
  if (selecionados.length > 0) {
    // Exibe barra de ações em lote
    exibirBarraAcoesLote(selecionados.length);
  } else {
    // Oculta barra de ações em lote
    ocultarBarraAcoesLote();
  }
}
```

### Inclusão de Nova Embalagem

O botão de inclusão redireciona para o formulário de cadastro:

```javascript
// Código para inclusão de nova embalagem
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/embalagens/novo";
});
```

### Criação de Embalagens dos Correios

O botão para criar embalagens dos Correios abre um modal com opções:

```javascript
// Código para criar embalagens dos Correios
document
  .querySelector("#btn-criar-correios")
  .addEventListener("click", function () {
    // Abre modal de opções
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Criar Embalagens dos Correios</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <p class="modal-descricao">
          Selecione os tipos de embalagens dos Correios que deseja criar automaticamente:
        </p>
        <div class="opcoes-checkbox">
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_caixa" name="tipos[]" value="caixa" checked>
            <label for="tipo_caixa">Caixas</label>
          </div>
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_envelope" name="tipos[]" value="envelope" checked>
            <label for="tipo_envelope">Envelopes</label>
          </div>
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_pacote" name="tipos[]" value="pacote" checked>
            <label for="tipo_pacote">Pacotes</label>
          </div>
        </div>
        <p class="modal-aviso">
          As embalagens criadas terão as dimensões oficiais dos Correios.
        </p>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar">Criar Embalagens</button>
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

    modal.querySelector("#btn-confirmar").addEventListener("click", () => {
      // Coleta os tipos selecionados
      const tiposSelecionados = Array.from(
        modal.querySelectorAll('input[name="tipos[]"]:checked')
      ).map((input) => input.value);

      // Cria as embalagens
      criarEmbalagensCorreios(tiposSelecionados);

      // Fecha o modal
      document.body.removeChild(modal);
    });
  });

function criarEmbalagensCorreios(tipos) {
  // Envia a solicitação para criar as embalagens
  fetch("/api/embalagens/criar-correios", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({ tipos }),
  })
    .then((response) => response.json())
    .then((data) => {
      // Exibe mensagem de sucesso
      alert(
        `${data.quantidade} embalagens dos Correios foram criadas com sucesso!`
      );

      // Atualiza a lista de embalagens
      window.location.reload();
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert("Erro ao criar embalagens dos Correios. Tente novamente.");
    });
}
```

### Paginação

A paginação permite navegar entre as páginas de resultados:

```javascript
// Código para paginação
document.querySelectorAll(".paginacao-pagina").forEach((link) => {
  link.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os links
    document.querySelectorAll(".paginacao-pagina").forEach((l) => {
      l.classList.remove("ativo");
    });

    // Adiciona classe ativo ao link clicado
    this.classList.add("ativo");

    // Carrega a página selecionada
    const pagina = this.textContent.trim();
    carregarPagina(pagina);
  });
});

document
  .querySelector(".paginacao-proxima")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Encontra o link ativo atual
    const linkAtivo = document.querySelector(".paginacao-pagina.ativo");
    const paginaAtual = parseInt(linkAtivo.textContent.trim());

    // Calcula a próxima página
    const proximaPagina = paginaAtual + 1;

    // Verifica se existe um link para a próxima página
    const proximoLink = document.querySelector(
      `.paginacao-pagina:not(.ativo):nth-child(${proximaPagina})`
    );

    if (proximoLink) {
      // Remove classe ativo do link atual
      linkAtivo.classList.remove("ativo");

      // Adiciona classe ativo ao próximo link
      proximoLink.classList.add("ativo");

      // Carrega a próxima página
      carregarPagina(proximaPagina.toString());
    }
  });

function carregarPagina(pagina) {
  // Lógica para carregar a página selecionada
  fetch(`/api/embalagens?pagina=${pagina}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaEmbalagens(data);
    });
}
```

### Botão Voltar ao Topo

O botão permite voltar ao topo da página:

```javascript
// Código para botão voltar ao topo
const botaoVoltarTopo = document.querySelector(".botao-voltar-topo");

// Exibe ou oculta o botão conforme o scroll
window.addEventListener("scroll", function () {
  if (window.pageYOffset > 300) {
    botaoVoltarTopo.style.display = "flex";
  } else {
    botaoVoltarTopo.style.display = "none";
  }
});

// Ação de voltar ao topo
botaoVoltarTopo.addEventListener("click", function () {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
});
```

## Formulário de Cadastro de Embalagem

Quando o usuário clica em "Incluir embalagem", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Nova Embalagem</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-embalagem">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Básicas</h2>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="descricao">Descrição *</label>
            <input
              type="text"
              id="descricao"
              name="descricao"
              placeholder="Descrição da embalagem"
              required
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="tipo">Tipo *</label>
            <select id="tipo" name="tipo" required>
              <option value="">Selecione...</option>
              <option value="caixa">Caixa</option>
              <option value="envelope">Envelope</option>
              <option value="pacote">Pacote</option>
              <option value="outro">Outro</option>
            </select>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Dimensões</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="comprimento">Comprimento (cm) *</label>
            <input
              type="text"
              id="comprimento"
              name="comprimento"
              placeholder="0,00"
              required
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="largura">Largura (cm) *</label>
            <input
              type="text"
              id="largura"
              name="largura"
              placeholder="0,00"
              required
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="altura">Altura (cm) *</label>
            <input
              type="text"
              id="altura"
              name="altura"
              placeholder="0,00"
              required
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="peso">Peso (kg)</label>
            <input type="text" id="peso" name="peso" placeholder="0,00" />
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Configurações Adicionais</h2>
        <div class="form-linha">
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input
                type="checkbox"
                id="padrao_correios"
                name="padrao_correios"
              />
              <label for="padrao_correios">Embalagem padrão dos Correios</label>
            </div>
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="ativo" name="ativo" checked />
              <label for="ativo">Embalagem ativa</label>
            </div>
          </div>
        </div>
      </div>
    </form>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  background-color: #ffffff;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.formulario-titulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.formulario-acoes {
  display: flex;
  gap: 8px;
}

.formulario-corpo {
  padding: 24px;
}

.form-secao {
  margin-bottom: 32px;
  padding-bottom: 24px;
  border-bottom: 1px solid #f0f0f0;
}

.form-secao:last-child {
  border-bottom: none;
  margin-bottom: 0;
  padding-bottom: 0;
}

.form-secao-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 16px 0;
}

.form-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 16px;
}

.form-grupo {
  flex: 1;
  min-width: 200px;
}

.form-grupo-pequeno {
  flex: 0 0 120px;
}

.form-grupo-medio {
  flex: 0 0 200px;
}

.form-grupo label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input,
.form-grupo select {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input:focus,
.form-grupo select:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.opcao-checkbox {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.opcao-checkbox input {
  margin-right: 6px;
  width: auto;
}

.opcao-checkbox label {
  margin-bottom: 0;
  cursor: pointer;
}
```

## Interações JavaScript do Formulário

```javascript
// Código para manipulação do formulário
document.addEventListener("DOMContentLoaded", function () {
  // Máscaras para campos numéricos
  const camposNumericos = document.querySelectorAll(
    "#comprimento, #largura, #altura, #peso"
  );
  camposNumericos.forEach((campo) => {
    campo.addEventListener("input", function (e) {
      let valor = e.target.value.replace(/[^\d,]/g, "");
      valor = valor.replace(/,/g, ".");

      // Limita a duas casas decimais
      const partes = valor.split(".");
      if (partes.length > 1) {
        partes[1] = partes[1].substring(0, 2);
        valor = partes.join(".");
      }

      e.target.value = valor;
    });
  });

  // Botão cancelar
  const btnCancelar = document.querySelector("#btn-cancelar");
  if (btnCancelar) {
    btnCancelar.addEventListener("click", function () {
      // Confirma se há alterações não salvas
      if (formularioAlterado()) {
        if (confirm("Há alterações não salvas. Deseja realmente sair?")) {
          window.location.href = "/embalagens";
        }
      } else {
        window.location.href = "/embalagens";
      }
    });
  }

  // Botão salvar
  const btnSalvar = document.querySelector("#btn-salvar");
  if (btnSalvar) {
    btnSalvar.addEventListener("click", function () {
      const form = document.querySelector("#form-embalagem");
      if (form.checkValidity()) {
        salvarEmbalagem();
      } else {
        form.reportValidity();
      }
    });
  }
});

function formularioAlterado() {
  // Verifica se houve alterações no formulário
  const form = document.querySelector("#form-embalagem");
  const formData = new FormData(form);

  // Compara com os valores originais
  // Implementação depende da lógica de negócio

  return false; // Placeholder
}

function salvarEmbalagem() {
  const form = document.querySelector("#form-embalagem");
  const formData = new FormData(form);

  // Converte para objeto
  const embalagem = {};
  formData.forEach((value, key) => {
    if (key === "padrao_correios" || key === "ativo") {
      embalagem[key] = value === "on";
    } else {
      embalagem[key] = value;
    }
  });

  // Envia para a API
  fetch("/api/embalagens", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(embalagem),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar embalagem");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Embalagem salva com sucesso!");

      // Redireciona para a listagem
      window.location.href = "/embalagens";
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao salvar embalagem: ${error.message}`);
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .form-linha {
    flex-direction: column;
    gap: 16px;
  }

  .form-grupo,
  .form-grupo-pequeno,
  .form-grupo-medio {
    flex: 1;
    width: 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 12px;
    width: 100%;
  }

  .formulario-corpo {
    padding: 16px;
  }

  .coluna-dimensoes {
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

  .coluna-tipo {
    display: none;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Roxo (tags): #722ed1
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

### Tags de Identificação

```css
.embalagem-tag {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #722ed1;
  color: white;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
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

.modal-descricao {
  margin-bottom: 16px;
  font-size: 14px;
  color: #333333;
}

.modal-aviso {
  margin-top: 16px;
  font-size: 12px;
  color: #666666;
  font-style: italic;
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

1. **Listagem de Embalagens**:

   - A tela inicial exibe todas as embalagens cadastradas
   - Filtros permitem refinar a visualização por tipo
   - Pesquisa permite localizar embalagens específicas
   - Paginação permite navegar entre as páginas de resultados

2. **Cadastro de Nova Embalagem**:

   - Clique no botão "Incluir embalagem" redireciona para o formulário de cadastro
   - Preenchimento do formulário com dados da embalagem
   - Salvamento adiciona a embalagem à listagem

3. **Criação de Embalagens dos Correios**:
   - Clique no botão "Criar embalagens Correios" abre modal com opções
   - Seleção dos tipos de embalagens a serem criadas
   - Confirmação cria automaticamente as embalagens com dimensões padrão dos Correios

## Conclusão

O módulo "Embalagens" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente das embalagens utilizadas para envio de produtos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, cadastro e manipulação de dados de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária, o roxo para as tags de identificação e tons de cinza para criar contraste e hierarquia visual. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para a gestão de embalagens, como a criação automática de embalagens padrão dos Correios, atendendo às necessidades de negócios que trabalham com envio de produtos.
