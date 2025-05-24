# Análise do Módulo CRM - ERP Revo

## Estrutura Geral

O módulo "CRM" do ERP Revo apresenta uma interface organizada para gestão do relacionamento com os clientes. A tela é composta por um cabeçalho com título e descrição, botões de ação principais, uma barra de pesquisa com filtros e uma área de visualização dos assuntos/oportunidades.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção, uma breve descrição e botões de ação:

- Título "CRM"
- Descrição "Gestão do relacionamento com os clientes"
- Botão para incluir novo assunto

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">CRM</h1>
    <p class="descricao-modulo">Gestão do relacionamento com os clientes</p>
  </div>
  <div class="acoes-container">
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir assunto</span>
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

.descricao-modulo {
  font-size: 14px;
  color: #666666;
  margin: 4px 0 0 0;
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

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao .icone {
  margin-right: 8px;
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar os assuntos/oportunidades:

- Campo de texto para pesquisa por contato, CPF/CNPJ ou descrição
- Botão de busca
- Opções de visualização (Lista, por estágio)
- Filtros de período e outros filtros avançados

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por contato, CPF/CNPJ ou descrição"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="opcoes-visualizacao">
    <a href="#" class="opcao-item ativo" data-visualizacao="lista">
      <span class="icone icone-lista"></span>
      <span class="texto">Lista</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="estagio">
      <span class="icone icone-estagio"></span>
      <span class="texto">por estágio</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="periodo">
      <span class="icone icone-calendario"></span>
      <span class="texto">por período</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="filtros">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
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

.opcoes-visualizacao {
  display: flex;
  gap: 8px;
}

.opcao-item {
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

.opcao-item.ativo {
  background-color: #e6f7ff;
  border-color: #91d5ff;
  color: #1890ff;
}

.opcao-item:hover:not(.ativo) {
  background-color: #f0f0f0;
}

.opcao-item .icone {
  margin-right: 6px;
  font-size: 16px;
}
```

### Filtros por Situação

Os filtros permitem visualizar assuntos/oportunidades por situação:

- Todos
- Com ações pendentes
- Encerrados
- Com estrela
- Arquivados

**Estrutura HTML:**

```html
<div class="filtros-situacao">
  <a href="#" class="filtro-situacao ativo" data-situacao="todos">
    <span class="texto">Todos</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="pendentes">
    <span class="texto">Com ações pendentes</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="encerrados">
    <span class="texto">Encerrados</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="estrela">
    <span class="texto">Com estrela</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="arquivados">
    <span class="texto">Arquivados</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.filtros-situacao {
  display: flex;
  gap: 4px;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtro-situacao {
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

.filtro-situacao.ativo {
  background-color: #f6ffed;
  border-color: #b7eb8f;
  color: #52c41a;
}

.filtro-situacao:hover:not(.ativo) {
  background-color: #f5f5f5;
}
```

### Área de Resultados

A área de resultados exibe os assuntos/oportunidades cadastrados ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="resultados-container">
  <!-- Quando há resultados -->
  <div class="tabela-assuntos">
    <!-- Conteúdo da tabela de assuntos -->
  </div>

  <!-- Quando não há resultados -->
  <div class="sem-resultados">
    <div class="sem-resultados-conteudo">
      <h2 class="sem-resultados-titulo">
        Sua pesquisa não retornou resultados.
      </h2>
      <p class="sem-resultados-descricao">
        Tente outras opções de pesquisa, situações ou remova os filtros.
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

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}
```

### Tabela de Assuntos

Quando há resultados, a tabela exibe os assuntos/oportunidades cadastrados:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-assuntos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-estrela"></th>
        <th class="coluna-contato">
          Contato
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-descricao">
          Descrição
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-estagio">
          Estágio
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-valor">
          Valor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-data">
          Data
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-responsavel">
          Responsável
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-assunto">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-estrela">
          <button class="botao-estrela">
            <span class="icone icone-estrela-vazia"></span>
          </button>
        </td>
        <td class="coluna-contato">
          <a href="#/contato/12345" class="link-contato"
            >Empresa Exemplo Ltda</a
          >
        </td>
        <td class="coluna-descricao">
          <a href="#/assunto/67890" class="link-assunto"
            >Proposta de serviços de consultoria</a
          >
        </td>
        <td class="coluna-estagio">
          <span class="badge badge-estagio">Negociação</span>
        </td>
        <td class="coluna-valor">R$ 5.000,00</td>
        <td class="coluna-data">05/12/2024</td>
        <td class="coluna-responsavel">João Silva</td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-opcoes"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de assuntos -->
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

.tabela-assuntos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-assuntos th,
.tabela-assuntos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-assuntos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
  white-space: nowrap;
}

.coluna-selecao {
  width: 40px;
}

.coluna-estrela {
  width: 40px;
}

.coluna-contato,
.coluna-responsavel {
  width: 150px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-estagio {
  width: 120px;
}

.coluna-valor,
.coluna-data {
  width: 100px;
}

.coluna-acoes {
  width: 60px;
  text-align: right;
}

.icone-ordenacao {
  display: inline-block;
  width: 12px;
  height: 12px;
  margin-left: 4px;
  vertical-align: middle;
  background-image: url("path/to/sort-icon.svg");
  background-repeat: no-repeat;
  background-position: center;
}

.link-contato,
.link-assunto {
  color: #1890ff;
  text-decoration: none;
}

.link-contato:hover,
.link-assunto:hover {
  text-decoration: underline;
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

.badge-estagio {
  background-color: #e6f7ff;
  color: #1890ff;
}

.botao-estrela {
  width: 24px;
  height: 24px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: none;
  cursor: pointer;
  color: #d9d9d9;
  transition: color 0.2s ease;
}

.botao-estrela:hover {
  color: #faad14;
}

.botao-estrela .icone-estrela-cheia {
  color: #faad14;
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
}

.botao-acao:hover {
  background-color: #f5f5f5;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar assuntos/oportunidades:

```javascript
// Código para pesquisa de assuntos
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
  // Lógica para filtrar assuntos pelo termo de pesquisa
  fetch(`/api/crm/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaAssuntos(data);
    });
}

// Código para opções de visualização
document.querySelectorAll(".opcao-item").forEach((opcao) => {
  opcao.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todas as opções
    document.querySelectorAll(".opcao-item").forEach((op) => {
      op.classList.remove("ativo");
    });

    // Adiciona classe ativo à opção clicada
    this.classList.add("ativo");

    // Altera a visualização
    const visualizacao = this.getAttribute("data-visualizacao");
    alterarVisualizacao(visualizacao);
  });
});

function alterarVisualizacao(tipo) {
  switch (tipo) {
    case "lista":
      // Exibe visualização em lista
      document.querySelector(".tabela-container").style.display = "block";
      document.querySelector(".visualizacao-estagio").style.display = "none";
      break;
    case "estagio":
      // Exibe visualização por estágio (kanban)
      document.querySelector(".tabela-container").style.display = "none";
      document.querySelector(".visualizacao-estagio").style.display = "block";
      carregarVisualizacaoEstagio();
      break;
    case "periodo":
      // Abre modal de seleção de período
      abrirModalPeriodo();
      break;
    case "filtros":
      // Abre modal de filtros avançados
      abrirModalFiltros();
      break;
  }
}

function abrirModalPeriodo() {
  // Abre modal para seleção de período
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Filtrar por Período</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="data_inicial">Data Inicial</label>
          <input type="date" id="data_inicial" name="data_inicial">
        </div>
        <div class="form-grupo">
          <label for="data_final">Data Final</label>
          <input type="date" id="data_final" name="data_final">
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input type="checkbox" id="apenas_periodo" name="apenas_periodo">
            <label for="apenas_periodo">Apenas assuntos criados neste período</label>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-limpar-periodo">Limpar</button>
        <button class="botao botao-primario" id="btn-aplicar-periodo">Aplicar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-limpar-periodo").addEventListener("click", () => {
    document.querySelector("#data_inicial").value = "";
    document.querySelector("#data_final").value = "";
    document.querySelector("#apenas_periodo").checked = false;
  });

  modal.querySelector("#btn-aplicar-periodo").addEventListener("click", () => {
    // Coleta os dados do formulário
    const dataInicial = document.querySelector("#data_inicial").value;
    const dataFinal = document.querySelector("#data_final").value;
    const apenasPeriodo = document.querySelector("#apenas_periodo").checked;

    // Aplica o filtro por período
    filtrarPorPeriodo(dataInicial, dataFinal, apenasPeriodo);

    // Fecha o modal
    document.body.removeChild(modal);
  });
}

function filtrarPorPeriodo(dataInicial, dataFinal, apenasPeriodo) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();

  if (dataInicial) {
    params.append("data_inicial", dataInicial);
  }

  if (dataFinal) {
    params.append("data_final", dataFinal);
  }

  if (apenasPeriodo) {
    params.append("apenas_periodo", "true");
  }

  // Faz a requisição com os filtros
  fetch(`/api/crm?${params.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaAssuntos(data);
    });
}

function abrirModalFiltros() {
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
            <label for="contato">Contato</label>
            <select id="contato" name="contato">
              <option value="">Todos os contatos</option>
              <!-- Opções de contatos serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo">
            <label for="estagio">Estágio</label>
            <select id="estagio" name="estagio">
              <option value="">Todos</option>
              <option value="prospeccao">Prospecção</option>
              <option value="qualificacao">Qualificação</option>
              <option value="proposta">Proposta</option>
              <option value="negociacao">Negociação</option>
              <option value="fechamento">Fechamento</option>
            </select>
          </div>
          <div class="form-grupo">
            <label for="responsavel">Responsável</label>
            <select id="responsavel" name="responsavel">
              <option value="">Todos</option>
              <!-- Opções de responsáveis serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo">
            <label for="valor_minimo">Valor Mínimo</label>
            <input type="text" id="valor_minimo" name="valor_minimo" placeholder="0,00">
          </div>
          <div class="form-grupo">
            <label for="valor_maximo">Valor Máximo</label>
            <input type="text" id="valor_maximo" name="valor_maximo" placeholder="0,00">
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

  // Carrega as opções de contatos e responsáveis
  carregarOpcoesContatos();
  carregarOpcoesResponsaveis();

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-limpar-filtros").addEventListener("click", () => {
    document.querySelector("#form-filtros").reset();
  });

  modal.querySelector("#btn-aplicar-filtros").addEventListener("click", () => {
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
}

function carregarOpcoesContatos() {
  // Carrega a lista de contatos para o select
  fetch("/api/contatos")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#contato");

      data.forEach((contato) => {
        const option = document.createElement("option");
        option.value = contato.id;
        option.textContent = contato.nome;
        select.appendChild(option);
      });
    });
}

function carregarOpcoesResponsaveis() {
  // Carrega a lista de responsáveis para o select
  fetch("/api/usuarios")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#responsavel");

      data.forEach((usuario) => {
        const option = document.createElement("option");
        option.value = usuario.id;
        option.textContent = usuario.nome;
        select.appendChild(option);
      });
    });
}

function aplicarFiltrosAvancados(filtros) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();

  Object.keys(filtros).forEach((key) => {
    params.append(key, filtros[key]);
  });

  // Faz a requisição com os filtros
  fetch(`/api/crm?${params.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaAssuntos(data);
    });
}
```

### Filtros por Situação

Os filtros por situação permitem visualizar assuntos em diferentes estados:

```javascript
// Código para filtrar por situação
document.querySelectorAll(".filtro-situacao").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-situacao").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por situação
    const situacao = this.getAttribute("data-situacao");
    filtrarPorSituacao(situacao);
  });
});

function filtrarPorSituacao(situacao) {
  // Lógica para filtrar assuntos por situação
  let url = "/api/crm";

  if (situacao !== "todos") {
    url += `?situacao=${situacao}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaAssuntos(data);
    });
}
```

### Seleção de Assuntos

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de assuntos
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

function exibirBarraAcoesLote(quantidade) {
  // Cria a barra de ações em lote se não existir
  if (!document.querySelector(".barra-acoes-lote")) {
    const barra = document.createElement("div");
    barra.classList.add("barra-acoes-lote");
    barra.innerHTML = `
      <div class="barra-acoes-info">
        <span class="barra-acoes-quantidade">${quantidade} ${
      quantidade === 1 ? "item selecionado" : "itens selecionados"
    }</span>
      </div>
      <div class="barra-acoes-botoes">
        <button class="botao botao-secundario" data-acao="alterar-estagio">
          <span class="icone icone-estagio"></span>
          <span class="texto">Alterar estágio</span>
        </button>
        <button class="botao botao-secundario" data-acao="alterar-responsavel">
          <span class="icone icone-responsavel"></span>
          <span class="texto">Alterar responsável</span>
        </button>
        <button class="botao botao-secundario" data-acao="arquivar">
          <span class="icone icone-arquivar"></span>
          <span class="texto">Arquivar</span>
        </button>
        <button class="botao botao-secundario" data-acao="excluir">
          <span class="icone icone-excluir"></span>
          <span class="texto">Excluir</span>
        </button>
      </div>
    `;

    document
      .querySelector(".resultados-container")
      .insertAdjacentElement("beforebegin", barra);

    // Adiciona eventos aos botões da barra
    barra.querySelectorAll(".botao").forEach((botao) => {
      botao.addEventListener("click", function () {
        const acao = this.getAttribute("data-acao");
        executarAcaoEmLote(acao);
      });
    });
  } else {
    // Atualiza a quantidade de itens selecionados
    document.querySelector(
      ".barra-acoes-quantidade"
    ).textContent = `${quantidade} ${
      quantidade === 1 ? "item selecionado" : "itens selecionados"
    }`;
  }
}

function ocultarBarraAcoesLote() {
  const barra = document.querySelector(".barra-acoes-lote");

  if (barra) {
    barra.remove();
  }
}

function executarAcaoEmLote(acao) {
  // Obtém os IDs dos assuntos selecionados
  const assuntosSelecionados = Array.from(
    document.querySelectorAll(".checkbox-selecionar:checked")
  ).map((checkbox) => {
    const linha = checkbox.closest("tr");
    return linha.getAttribute("data-assunto-id");
  });

  switch (acao) {
    case "alterar-estagio":
      abrirModalAlterarEstagio(assuntosSelecionados);
      break;
    case "alterar-responsavel":
      abrirModalAlterarResponsavel(assuntosSelecionados);
      break;
    case "arquivar":
      confirmarArquivarAssuntos(assuntosSelecionados);
      break;
    case "excluir":
      confirmarExcluirAssuntos(assuntosSelecionados);
      break;
  }
}
```

### Ordenação de Colunas

As colunas da tabela podem ser ordenadas:

```javascript
// Código para ordenação de colunas
document.querySelectorAll('th[class^="coluna-"]').forEach((coluna) => {
  if (coluna.querySelector(".icone-ordenacao")) {
    coluna.addEventListener("click", function () {
      // Obtém o nome da coluna a partir da classe
      const classeColuna = Array.from(this.classList).find((classe) =>
        classe.startsWith("coluna-")
      );
      const nomeColuna = classeColuna.replace("coluna-", "");

      // Verifica se já está ordenado e em qual direção
      const direcaoAtual = this.getAttribute("data-ordem") || "nenhuma";
      let novaDirecao;

      if (direcaoAtual === "nenhuma") {
        novaDirecao = "asc";
      } else if (direcaoAtual === "asc") {
        novaDirecao = "desc";
      } else {
        novaDirecao = "nenhuma";
      }

      // Remove a ordenação de todas as colunas
      document.querySelectorAll('th[class^="coluna-"]').forEach((col) => {
        col.removeAttribute("data-ordem");
        col.querySelector(".icone-ordenacao")?.classList.remove("asc", "desc");
      });

      // Aplica a nova ordenação
      if (novaDirecao !== "nenhuma") {
        this.setAttribute("data-ordem", novaDirecao);
        this.querySelector(".icone-ordenacao").classList.add(novaDirecao);

        // Ordena a tabela
        ordenarTabela(nomeColuna, novaDirecao);
      } else {
        // Restaura a ordem original
        carregarAssuntos();
      }
    });
  }
});

function ordenarTabela(coluna, direcao) {
  // Lógica para ordenar a tabela
  fetch(`/api/crm?ordenar_por=${coluna}&direcao=${direcao}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaAssuntos(data);
    });
}
```

### Inclusão de Novo Assunto

O botão de inclusão redireciona para o formulário de cadastro:

```javascript
// Código para inclusão de novo assunto
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/crm/novo";
});
```

### Marcação com Estrela

Os assuntos podem ser marcados com estrela para destaque:

```javascript
// Código para marcação com estrela
document.querySelectorAll(".botao-estrela").forEach((botao) => {
  botao.addEventListener("click", function () {
    const linha = this.closest("tr");
    const assuntoId = linha.getAttribute("data-assunto-id");
    const icone = this.querySelector(".icone");

    // Verifica se já está marcado com estrela
    const marcado = icone.classList.contains("icone-estrela-cheia");

    // Alterna o estado da estrela
    if (marcado) {
      icone.classList.remove("icone-estrela-cheia");
      icone.classList.add("icone-estrela-vazia");
      removerEstrela(assuntoId);
    } else {
      icone.classList.remove("icone-estrela-vazia");
      icone.classList.add("icone-estrela-cheia");
      adicionarEstrela(assuntoId);
    }
  });
});

function adicionarEstrela(assuntoId) {
  // Lógica para adicionar estrela ao assunto
  fetch(`/api/crm/${assuntoId}/estrela`, {
    method: "POST",
  })
    .then((response) => {
      if (!response.ok) {
        throw new Error("Erro ao adicionar estrela");
      }
    })
    .catch((error) => {
      console.error(error);
      // Reverte a alteração visual em caso de erro
      const icone = document.querySelector(
        `tr[data-assunto-id="${assuntoId}"] .botao-estrela .icone`
      );
      icone.classList.remove("icone-estrela-cheia");
      icone.classList.add("icone-estrela-vazia");
    });
}

function removerEstrela(assuntoId) {
  // Lógica para remover estrela do assunto
  fetch(`/api/crm/${assuntoId}/estrela`, {
    method: "DELETE",
  })
    .then((response) => {
      if (!response.ok) {
        throw new Error("Erro ao remover estrela");
      }
    })
    .catch((error) => {
      console.error(error);
      // Reverte a alteração visual em caso de erro
      const icone = document.querySelector(
        `tr[data-assunto-id="${assuntoId}"] .botao-estrela .icone`
      );
      icone.classList.remove("icone-estrela-vazia");
      icone.classList.add("icone-estrela-cheia");
    });
}
```

### Menu de Ações

O menu de ações oferece opções para cada assunto:

```javascript
// Código para menu de ações
document.querySelectorAll(".botao-acao").forEach((botao) => {
  botao.addEventListener("click", function (e) {
    e.stopPropagation();

    // Fecha outros menus abertos
    document.querySelectorAll(".menu-acoes").forEach((menu) => {
      menu.remove();
    });

    // Obtém o ID do assunto
    const linha = this.closest("tr");
    const assuntoId = linha.getAttribute("data-assunto-id");

    // Cria o menu de ações
    const menu = document.createElement("div");
    menu.classList.add("menu-acoes");
    menu.innerHTML = `
      <a href="#/assunto/${assuntoId}" class="menu-item">
        <span class="icone icone-visualizar"></span>
        <span class="texto">Visualizar</span>
      </a>
      <a href="#/assunto/${assuntoId}/editar" class="menu-item">
        <span class="icone icone-editar"></span>
        <span class="texto">Editar</span>
      </a>
      <div class="menu-divider"></div>
      <a href="#" class="menu-item" data-acao="alterar-estagio" data-assunto-id="${assuntoId}">
        <span class="icone icone-estagio"></span>
        <span class="texto">Alterar estágio</span>
      </a>
      <a href="#" class="menu-item" data-acao="alterar-responsavel" data-assunto-id="${assuntoId}">
        <span class="icone icone-responsavel"></span>
        <span class="texto">Alterar responsável</span>
      </a>
      <div class="menu-divider"></div>
      <a href="#" class="menu-item" data-acao="arquivar" data-assunto-id="${assuntoId}">
        <span class="icone icone-arquivar"></span>
        <span class="texto">Arquivar</span>
      </a>
      <a href="#" class="menu-item" data-acao="excluir" data-assunto-id="${assuntoId}">
        <span class="icone icone-excluir"></span>
        <span class="texto">Excluir</span>
      </a>
    `;

    // Posiciona o menu
    const rect = this.getBoundingClientRect();
    menu.style.top = `${rect.bottom}px`;
    menu.style.right = `${window.innerWidth - rect.right}px`;

    // Adiciona ao DOM
    document.body.appendChild(menu);

    // Adiciona eventos aos itens do menu
    menu.querySelectorAll(".menu-item[data-acao]").forEach((item) => {
      item.addEventListener("click", function (e) {
        e.preventDefault();

        const acao = this.getAttribute("data-acao");
        const assuntoId = this.getAttribute("data-assunto-id");

        executarAcao(acao, assuntoId);

        // Remove o menu
        menu.remove();
      });
    });

    // Fecha o menu ao clicar fora
    document.addEventListener("click", function fecharMenu(e) {
      if (!menu.contains(e.target) && e.target !== botao) {
        menu.remove();
        document.removeEventListener("click", fecharMenu);
      }
    });
  });
});

function executarAcao(acao, assuntoId) {
  switch (acao) {
    case "alterar-estagio":
      abrirModalAlterarEstagio([assuntoId]);
      break;
    case "alterar-responsavel":
      abrirModalAlterarResponsavel([assuntoId]);
      break;
    case "arquivar":
      confirmarArquivarAssuntos([assuntoId]);
      break;
    case "excluir":
      confirmarExcluirAssuntos([assuntoId]);
      break;
  }
}
```

## Formulário de Cadastro de Assunto

Quando o usuário clica em "Incluir assunto", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Novo Assunto</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-assunto">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Básicas</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="contato">Contato *</label>
            <select id="contato" name="contato" required>
              <option value="">Selecione...</option>
              <!-- Opções de contatos serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="data">Data *</label>
            <input type="date" id="data" name="data" required />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="descricao">Descrição *</label>
            <input type="text" id="descricao" name="descricao" required />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="estagio">Estágio *</label>
            <select id="estagio" name="estagio" required>
              <option value="">Selecione...</option>
              <option value="prospeccao">Prospecção</option>
              <option value="qualificacao">Qualificação</option>
              <option value="proposta">Proposta</option>
              <option value="negociacao">Negociação</option>
              <option value="fechamento">Fechamento</option>
            </select>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor">Valor</label>
            <input type="text" id="valor" name="valor" placeholder="0,00" />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="responsavel">Responsável *</label>
            <select id="responsavel" name="responsavel" required>
              <option value="">Selecione...</option>
              <!-- Opções de responsáveis serão carregadas dinamicamente -->
            </select>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Detalhes</h2>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="observacoes">Observações</label>
            <textarea id="observacoes" name="observacoes" rows="4"></textarea>
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="criar_acao" name="criar_acao" />
              <label for="criar_acao">Criar ação para este assunto</label>
            </div>
          </div>
        </div>
        <div class="form-linha acao-detalhes" style="display: none;">
          <div class="form-grupo form-grupo-medio">
            <label for="acao_tipo">Tipo de Ação *</label>
            <select id="acao_tipo" name="acao_tipo">
              <option value="">Selecione...</option>
              <option value="ligacao">Ligação</option>
              <option value="email">E-mail</option>
              <option value="reuniao">Reunião</option>
              <option value="visita">Visita</option>
              <option value="outro">Outro</option>
            </select>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="acao_data">Data *</label>
            <input type="date" id="acao_data" name="acao_data" />
          </div>
        </div>
        <div class="form-linha acao-detalhes" style="display: none;">
          <div class="form-grupo">
            <label for="acao_descricao">Descrição da Ação *</label>
            <input type="text" id="acao_descricao" name="acao_descricao" />
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
  flex: 0 0 150px;
}

.form-grupo-medio {
  flex: 0 0 300px;
}

.form-grupo label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input,
.form-grupo select,
.form-grupo textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input:focus,
.form-grupo select:focus,
.form-grupo textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.opcao-checkbox {
  display: flex;
  align-items: center;
}

.opcao-checkbox input[type="checkbox"] {
  margin-right: 8px;
  width: auto;
}

.opcao-checkbox label {
  margin-bottom: 0;
}
```

## Interações JavaScript do Formulário

```javascript
// Código para manipulação do formulário de assunto
document.addEventListener("DOMContentLoaded", function () {
  // Carrega a lista de contatos e responsáveis
  carregarOpcoesContatos();
  carregarOpcoesResponsaveis();

  // Define a data atual como padrão
  document.querySelector("#data").valueAsDate = new Date();

  // Exibe/oculta campos de ação
  document.querySelector("#criar_acao").addEventListener("change", function () {
    const acoesDetalhes = document.querySelectorAll(".acao-detalhes");

    if (this.checked) {
      acoesDetalhes.forEach((div) => {
        div.style.display = "flex";
      });

      // Define a data atual como padrão para a ação
      document.querySelector("#acao_data").valueAsDate = new Date();
    } else {
      acoesDetalhes.forEach((div) => {
        div.style.display = "none";
      });
    }
  });

  // Formata valores monetários
  const formatarValor = (input) => {
    input.addEventListener("input", function () {
      let valor = this.value.replace(/\D/g, "");
      valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
      this.value = valor;
    });
  };

  formatarValor(document.querySelector("#valor"));

  // Botão cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      // Confirma se há alterações não salvas
      if (formularioAlterado()) {
        if (confirm("Há alterações não salvas. Deseja realmente sair?")) {
          window.location.href = "/crm";
        }
      } else {
        window.location.href = "/crm";
      }
    });

  // Botão salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector("#form-assunto");

    // Valida campos obrigatórios
    if (validarFormulario()) {
      salvarAssunto();
    }
  });
});

function carregarOpcoesContatos() {
  // Carrega a lista de contatos para o select
  fetch("/api/contatos")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#contato");

      data.forEach((contato) => {
        const option = document.createElement("option");
        option.value = contato.id;
        option.textContent = contato.nome;
        select.appendChild(option);
      });
    });
}

function carregarOpcoesResponsaveis() {
  // Carrega a lista de responsáveis para o select
  fetch("/api/usuarios")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#responsavel");

      data.forEach((usuario) => {
        const option = document.createElement("option");
        option.value = usuario.id;
        option.textContent = usuario.nome;
        select.appendChild(option);
      });
    });
}

function validarFormulario() {
  const form = document.querySelector("#form-assunto");

  // Verifica campos obrigatórios básicos
  if (
    !form.contato.value ||
    !form.data.value ||
    !form.descricao.value ||
    !form.estagio.value ||
    !form.responsavel.value
  ) {
    alert("Preencha todos os campos obrigatórios.");
    return false;
  }

  // Verifica campos obrigatórios da ação, se estiver marcada
  if (form.criar_acao.checked) {
    if (
      !form.acao_tipo.value ||
      !form.acao_data.value ||
      !form.acao_descricao.value
    ) {
      alert("Preencha todos os campos obrigatórios da ação.");
      return false;
    }
  }

  return true;
}

function formularioAlterado() {
  // Verifica se houve alterações no formulário
  const form = document.querySelector("#form-assunto");

  return (
    form.contato.value !== "" ||
    form.descricao.value !== "" ||
    form.estagio.value !== "" ||
    form.valor.value !== "" ||
    form.responsavel.value !== "" ||
    form.observacoes.value !== "" ||
    form.criar_acao.checked
  );
}

function salvarAssunto() {
  // Coleta os dados do formulário
  const form = document.querySelector("#form-assunto");

  const assunto = {
    contato_id: form.contato.value,
    data: form.data.value,
    descricao: form.descricao.value,
    estagio: form.estagio.value,
    valor: form.valor.value.replace(",", "."),
    responsavel_id: form.responsavel.value,
    observacoes: form.observacoes.value,
  };

  // Adiciona dados da ação, se estiver marcada
  if (form.criar_acao.checked) {
    assunto.acao = {
      tipo: form.acao_tipo.value,
      data: form.acao_data.value,
      descricao: form.acao_descricao.value,
    };
  }

  // Envia para a API
  fetch("/api/crm", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(assunto),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar assunto");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Assunto salvo com sucesso!");

      // Redireciona para a listagem
      window.location.href = "/crm";
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao salvar assunto: ${error.message}`);
    });
}
```

## Visualização por Estágio (Kanban)

Quando o usuário seleciona a visualização por estágio, é exibido um quadro kanban:

**Estrutura HTML:**

```html
<div class="visualizacao-estagio">
  <div class="kanban-container">
    <div class="kanban-coluna" data-estagio="prospeccao">
      <div class="kanban-cabecalho">
        <h2 class="kanban-titulo">Prospecção</h2>
        <span class="kanban-contador">0</span>
      </div>
      <div class="kanban-corpo">
        <!-- Cartões serão adicionados dinamicamente -->
      </div>
    </div>
    <div class="kanban-coluna" data-estagio="qualificacao">
      <div class="kanban-cabecalho">
        <h2 class="kanban-titulo">Qualificação</h2>
        <span class="kanban-contador">0</span>
      </div>
      <div class="kanban-corpo">
        <!-- Cartões serão adicionados dinamicamente -->
      </div>
    </div>
    <div class="kanban-coluna" data-estagio="proposta">
      <div class="kanban-cabecalho">
        <h2 class="kanban-titulo">Proposta</h2>
        <span class="kanban-contador">0</span>
      </div>
      <div class="kanban-corpo">
        <!-- Cartões serão adicionados dinamicamente -->
      </div>
    </div>
    <div class="kanban-coluna" data-estagio="negociacao">
      <div class="kanban-cabecalho">
        <h2 class="kanban-titulo">Negociação</h2>
        <span class="kanban-contador">0</span>
      </div>
      <div class="kanban-corpo">
        <!-- Cartões serão adicionados dinamicamente -->
      </div>
    </div>
    <div class="kanban-coluna" data-estagio="fechamento">
      <div class="kanban-cabecalho">
        <h2 class="kanban-titulo">Fechamento</h2>
        <span class="kanban-contador">0</span>
      </div>
      <div class="kanban-corpo">
        <!-- Cartões serão adicionados dinamicamente -->
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.visualizacao-estagio {
  display: none;
  padding: 16px;
  background-color: #f0f2f5;
  overflow-x: auto;
}

.kanban-container {
  display: flex;
  gap: 16px;
  min-height: 600px;
}

.kanban-coluna {
  flex: 0 0 300px;
  background-color: #f5f5f5;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
}

.kanban-cabecalho {
  padding: 12px 16px;
  background-color: #f5f5f5;
  border-bottom: 1px solid #e0e0e0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.kanban-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.kanban-contador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  border-radius: 12px;
  background-color: #e0e0e0;
  color: #666666;
  font-size: 12px;
  font-weight: 500;
}

.kanban-corpo {
  flex: 1;
  padding: 8px;
  overflow-y: auto;
}

.kanban-cartao {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  margin-bottom: 8px;
  padding: 12px;
  cursor: pointer;
  transition: box-shadow 0.2s ease;
}

.kanban-cartao:hover {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.kanban-cartao-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 8px;
}

.kanban-cartao-titulo {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.kanban-cartao-estrela {
  color: #faad14;
  font-size: 16px;
}

.kanban-cartao-contato {
  font-size: 12px;
  color: #666666;
  margin-bottom: 8px;
}

.kanban-cartao-rodape {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 8px;
}

.kanban-cartao-valor {
  font-size: 12px;
  font-weight: 500;
  color: #333333;
}

.kanban-cartao-responsavel {
  font-size: 12px;
  color: #666666;
}
```

## Interações JavaScript do Kanban

```javascript
// Código para visualização por estágio (kanban)
function carregarVisualizacaoEstagio() {
  // Carrega os assuntos para o kanban
  fetch("/api/crm")
    .then((response) => response.json())
    .then((data) => {
      // Limpa as colunas
      document.querySelectorAll(".kanban-corpo").forEach((coluna) => {
        coluna.innerHTML = "";
      });

      // Agrupa os assuntos por estágio
      const assuntosPorEstagio = {
        prospeccao: [],
        qualificacao: [],
        proposta: [],
        negociacao: [],
        fechamento: [],
      };

      data.forEach((assunto) => {
        if (assuntosPorEstagio[assunto.estagio]) {
          assuntosPorEstagio[assunto.estagio].push(assunto);
        }
      });

      // Adiciona os cartões às colunas
      Object.keys(assuntosPorEstagio).forEach((estagio) => {
        const coluna = document.querySelector(
          `.kanban-coluna[data-estagio="${estagio}"]`
        );
        const corpo = coluna.querySelector(".kanban-corpo");
        const contador = coluna.querySelector(".kanban-contador");

        // Atualiza o contador
        contador.textContent = assuntosPorEstagio[estagio].length;

        // Adiciona os cartões
        assuntosPorEstagio[estagio].forEach((assunto) => {
          const cartao = criarCartaoKanban(assunto);
          corpo.appendChild(cartao);
        });
      });

      // Configura o drag and drop
      configurarDragAndDrop();
    });
}

function criarCartaoKanban(assunto) {
  const cartao = document.createElement("div");
  cartao.classList.add("kanban-cartao");
  cartao.setAttribute("data-assunto-id", assunto.id);
  cartao.setAttribute("draggable", "true");

  cartao.innerHTML = `
    <div class="kanban-cartao-cabecalho">
      <h3 class="kanban-cartao-titulo">${assunto.descricao}</h3>
      ${
        assunto.estrela
          ? '<span class="kanban-cartao-estrela icone-estrela-cheia"></span>'
          : ""
      }
    </div>
    <div class="kanban-cartao-contato">${assunto.contato_nome}</div>
    <div class="kanban-cartao-rodape">
      <div class="kanban-cartao-valor">R$ ${parseFloat(assunto.valor)
        .toFixed(2)
        .replace(".", ",")}</div>
      <div class="kanban-cartao-responsavel">${assunto.responsavel_nome}</div>
    </div>
  `;

  // Adiciona evento de clique para visualizar o assunto
  cartao.addEventListener("click", function () {
    window.location.href = `/crm/assunto/${assunto.id}`;
  });

  return cartao;
}

function configurarDragAndDrop() {
  const cartoes = document.querySelectorAll(".kanban-cartao");
  const colunas = document.querySelectorAll(".kanban-corpo");

  cartoes.forEach((cartao) => {
    cartao.addEventListener("dragstart", function (e) {
      e.dataTransfer.setData(
        "text/plain",
        cartao.getAttribute("data-assunto-id")
      );
      cartao.classList.add("arrastando");
    });

    cartao.addEventListener("dragend", function () {
      cartao.classList.remove("arrastando");
    });
  });

  colunas.forEach((coluna) => {
    coluna.addEventListener("dragover", function (e) {
      e.preventDefault();
      coluna.classList.add("destino-arrasto");
    });

    coluna.addEventListener("dragleave", function () {
      coluna.classList.remove("destino-arrasto");
    });

    coluna.addEventListener("drop", function (e) {
      e.preventDefault();
      coluna.classList.remove("destino-arrasto");

      const assuntoId = e.dataTransfer.getData("text/plain");
      const novoEstagio = coluna
        .closest(".kanban-coluna")
        .getAttribute("data-estagio");

      // Move o cartão para a nova coluna
      alterarEstagioAssunto(assuntoId, novoEstagio);
    });
  });
}

function alterarEstagioAssunto(assuntoId, novoEstagio) {
  // Envia a alteração para a API
  fetch(`/api/crm/${assuntoId}/estagio`, {
    method: "PUT",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({ estagio: novoEstagio }),
  })
    .then((response) => {
      if (response.ok) {
        // Recarrega a visualização
        carregarVisualizacaoEstagio();
      } else {
        throw new Error("Erro ao alterar estágio");
      }
    })
    .catch((error) => {
      console.error(error);
      alert("Erro ao alterar estágio do assunto.");
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .filtros-situacao {
    flex-wrap: wrap;
  }

  .filtro-situacao {
    flex: 1;
    min-width: 120px;
  }

  .kanban-coluna {
    flex: 0 0 250px;
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

  .barra-pesquisa {
    flex-direction: column;
    align-items: stretch;
  }

  .opcoes-visualizacao {
    margin-top: 12px;
  }

  .coluna-estagio,
  .coluna-data,
  .coluna-responsavel {
    display: none;
  }

  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 12px;
    width: 100%;
  }

  .form-grupo-medio,
  .form-grupo-pequeno {
    flex: 1 1 100%;
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

  .filtro-situacao {
    min-width: 100%;
  }

  .coluna-valor {
    display: none;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Verde (filtro ativo): #52c41a
- Verde claro (background filtro ativo): #f6ffed
- Verde muito claro (borda filtro ativo): #b7eb8f
- Amarelo (estrela): #faad14
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
  - Títulos de cartões: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Badges

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

.badge-estagio {
  background-color: #e6f7ff;
  color: #1890ff;
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

.modal-rodape {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  padding: 16px 24px;
  border-top: 1px solid #f0f0f0;
}
```

### Menus de Ações

```css
.menu-acoes {
  position: absolute;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  z-index: 1000;
  min-width: 160px;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 8px 16px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.menu-item:hover {
  background-color: #f5f5f5;
}

.menu-item .icone {
  margin-right: 8px;
  font-size: 16px;
}

.menu-divider {
  height: 1px;
  background-color: #e0e0e0;
  margin: 4px 0;
}
```

## Fluxos de Navegação

1. **Listagem de Assuntos**:

   - A tela inicial exibe todos os assuntos cadastrados
   - Filtros permitem refinar a visualização por situação, período ou outros critérios
   - Pesquisa permite localizar assuntos específicos por contato, CPF/CNPJ ou descrição

2. **Visualização por Estágio (Kanban)**:

   - Exibe os assuntos organizados por estágio em colunas
   - Permite arrastar e soltar para alterar o estágio de um assunto
   - Clique em um cartão redireciona para a visualização detalhada do assunto

3. **Cadastro de Novo Assunto**:

   - Clique no botão "Incluir assunto" redireciona para o formulário de cadastro
   - Preenchimento do formulário com dados do assunto e opção de criar ação
   - Salvamento adiciona o assunto à listagem

4. **Ações em Lote**:
   - Seleção de múltiplos assuntos exibe barra de ações em lote
   - Opções para alterar estágio, alterar responsável, arquivar ou excluir
   - Confirmação antes de executar ações irreversíveis

## Conclusão

O módulo "CRM" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão do relacionamento com os clientes. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, visualização por estágio (kanban) e cadastro de assuntos de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para indicar diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para a gestão de relacionamento com clientes, como cadastro de assuntos, acompanhamento por estágio, criação de ações e visualização em formato kanban, atendendo às necessidades de negócios que trabalham com vendas e relacionamento com clientes.
