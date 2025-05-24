# Análise do Módulo Notas de Entrada - ERP Revo

## Estrutura Geral

O módulo "Notas de Entrada" do ERP Revo apresenta uma interface organizada para gerenciamento de notas fiscais de entrada, com uma estrutura que facilita a visualização, importação e manipulação dos documentos fiscais. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma área de listagem de notas fiscais com seus respectivos status.

## Componentes Principais

### Alerta de Ambiente

Um alerta no topo da página informa sobre o ambiente atual:

**Estrutura HTML:**

```html
<div class="alerta-ambiente">
  <div class="alerta-icone">
    <span class="icone icone-alerta"></span>
  </div>
  <div class="alerta-mensagem">
    Você está no ambiente para testes de notas fiscais.
    <a href="#" class="alerta-link" id="btn-alterar-ambiente"
      >alterar ambiente</a
    >
    para gerar notas com valor fiscal.
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-ambiente {
  display: flex;
  align-items: center;
  padding: 12px 24px;
  background-color: #fffbe6;
  border: 1px solid #ffe58f;
  margin-bottom: 16px;
}

.alerta-icone {
  margin-right: 12px;
  color: #faad14;
  font-size: 18px;
}

.alerta-mensagem {
  font-size: 14px;
  color: #333333;
}

.alerta-link {
  color: #1890ff;
  text-decoration: none;
  margin: 0 4px;
}

.alerta-link:hover {
  text-decoration: underline;
}
```

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Notas Fiscais de Entrada"
- Botão para importar XML da NFe
- Botão para incluir nota fiscal
- Menu de ações adicionais

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Notas Fiscais de Entrada</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-importar-xml">
      <span class="icone icone-importar"></span>
      <span class="texto">Importar XML da NFe</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
    </a>
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

A barra de pesquisa permite filtrar as notas fiscais:

- Campo de texto para pesquisa por cliente ou número
- Botão de busca
- Filtros de período e data de emissão

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por cliente ou número"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="periodo">
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="data-emissao">
      <span class="icone icone-calendario"></span>
      <span class="texto">data de emissão</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="avancado">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
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

### Filtros por Status

Os filtros permitem visualizar notas fiscais por status:

- Todas
- Pendentes
- Registradas
- Emitidas
- Canceladas

**Estrutura HTML:**

```html
<div class="filtros-status">
  <a href="#" class="filtro-status ativo" data-status="todas">
    <span class="indicador indicador-todas"></span>
    <span class="texto">Todas</span>
  </a>
  <a href="#" class="filtro-status" data-status="pendentes">
    <span class="indicador indicador-pendentes"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="filtro-status" data-status="registradas">
    <span class="indicador indicador-registradas"></span>
    <span class="texto">Registradas</span>
  </a>
  <a href="#" class="filtro-status" data-status="emitidas">
    <span class="indicador indicador-emitidas"></span>
    <span class="texto">Emitidas</span>
  </a>
  <a href="#" class="filtro-status" data-status="canceladas">
    <span class="indicador indicador-canceladas"></span>
    <span class="texto">Canceladas</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.filtros-status {
  display: flex;
  gap: 4px;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtro-status {
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

.filtro-status.ativo {
  background-color: #f5f5f5;
  border-color: #e0e0e0;
}

.filtro-status:hover:not(.ativo) {
  background-color: #f5f5f5;
}

.indicador {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-todas {
  background-color: #999999;
}

.indicador-pendentes {
  background-color: #722ed1;
}

.indicador-registradas {
  background-color: #fa8c16;
}

.indicador-emitidas {
  background-color: #52c41a;
}

.indicador-canceladas {
  background-color: #f5222d;
}
```

### Área de Resultados

A área de resultados exibe as notas fiscais cadastradas ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="resultados-container">
  <!-- Quando há resultados -->
  <div class="tabela-notas">
    <!-- Conteúdo da tabela de notas fiscais -->
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
```

### Tabela de Notas Fiscais

Quando há resultados, a tabela exibe as notas fiscais cadastradas com suas informações:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-notas">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-numero">
          Número
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-serie">
          Série
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-data">
          Data
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-fornecedor">
          Fornecedor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-valor">
          Valor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-status">
          Status
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-nota">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-numero">
          <a href="#/nota/12345" class="link-nota">12345</a>
        </td>
        <td class="coluna-serie">1</td>
        <td class="coluna-data">05/12/2024</td>
        <td class="coluna-fornecedor">FORNECEDOR EXEMPLO LTDA</td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-status">
          <span class="badge badge-registrada">Registrada</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-opcoes"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de notas fiscais -->
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

.tabela-notas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-notas th,
.tabela-notas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-notas th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
  white-space: nowrap;
}

.coluna-selecao {
  width: 40px;
}

.coluna-numero,
.coluna-serie {
  width: 80px;
}

.coluna-data {
  width: 120px;
}

.coluna-fornecedor {
  min-width: 200px;
}

.coluna-valor {
  width: 120px;
}

.coluna-status {
  width: 120px;
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

.link-nota {
  color: #1890ff;
  text-decoration: none;
}

.link-nota:hover {
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

.badge-pendente {
  background-color: #f0f5ff;
  color: #722ed1;
}

.badge-registrada {
  background-color: #fff7e6;
  color: #fa8c16;
}

.badge-emitida {
  background-color: #f6ffed;
  color: #52c41a;
}

.badge-cancelada {
  background-color: #fff1f0;
  color: #f5222d;
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

O módulo permite pesquisar e filtrar notas fiscais:

```javascript
// Código para pesquisa de notas fiscais
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
  // Lógica para filtrar notas pelo termo de pesquisa
  fetch(`/api/notas_entrada/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}

// Código para filtro por período
document
  .querySelector('.filtro-item[data-filtro="periodo"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre dropdown de períodos
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-periodo="hoje">Hoje</a>
    <a href="#" class="dropdown-item" data-periodo="ontem">Ontem</a>
    <a href="#" class="dropdown-item" data-periodo="7dias">Últimos 7 dias</a>
    <a href="#" class="dropdown-item" data-periodo="30dias">Últimos 30 dias</a>
    <a href="#" class="dropdown-item" data-periodo="mes_atual">Mês atual</a>
    <a href="#" class="dropdown-item" data-periodo="mes_anterior">Mês anterior</a>
    <a href="#" class="dropdown-item" data-periodo="personalizado">Período personalizado</a>
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

        const periodo = this.getAttribute("data-periodo");

        if (periodo === "personalizado") {
          abrirModalPeriodoPersonalizado();
        } else {
          filtrarPorPeriodo(periodo);

          // Atualiza o texto do filtro
          document.querySelector(
            '.filtro-item[data-filtro="periodo"] .texto'
          ).textContent = this.textContent;
        }

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !==
          document.querySelector('.filtro-item[data-filtro="periodo"]')
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function abrirModalPeriodoPersonalizado() {
  // Abre modal para seleção de período personalizado
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Período Personalizado</h2>
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
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-periodo">Cancelar</button>
        <button class="botao botao-primario" id="btn-aplicar-periodo">Aplicar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-periodo").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-aplicar-periodo").addEventListener("click", () => {
    // Coleta os dados do formulário
    const dataInicial = document.querySelector("#data_inicial").value;
    const dataFinal = document.querySelector("#data_final").value;

    if (dataInicial && dataFinal) {
      // Aplica o filtro por período personalizado
      filtrarPorPeriodoPersonalizado(dataInicial, dataFinal);

      // Atualiza o texto do filtro
      const dataInicialFormatada = new Date(dataInicial).toLocaleDateString(
        "pt-BR"
      );
      const dataFinalFormatada = new Date(dataFinal).toLocaleDateString(
        "pt-BR"
      );
      document.querySelector(
        '.filtro-item[data-filtro="periodo"] .texto'
      ).textContent = `${dataInicialFormatada} - ${dataFinalFormatada}`;

      // Fecha o modal
      document.body.removeChild(modal);
    } else {
      alert("Preencha as datas inicial e final.");
    }
  });
}

function filtrarPorPeriodo(periodo) {
  // Lógica para filtrar notas por período
  fetch(`/api/notas_entrada?periodo=${periodo}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}

function filtrarPorPeriodoPersonalizado(dataInicial, dataFinal) {
  // Lógica para filtrar notas por período personalizado
  fetch(
    `/api/notas_entrada?data_inicial=${dataInicial}&data_final=${dataFinal}`
  )
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}

// Código para filtro por data de emissão
document
  .querySelector('.filtro-item[data-filtro="data-emissao"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre dropdown de tipos de data
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-tipo-data="emissao">Data de Emissão</a>
    <a href="#" class="dropdown-item" data-tipo-data="entrada">Data de Entrada</a>
    <a href="#" class="dropdown-item" data-tipo-data="registro">Data de Registro</a>
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

        const tipoData = this.getAttribute("data-tipo-data");
        alterarTipoData(tipoData);

        // Atualiza o texto do filtro
        document.querySelector(
          '.filtro-item[data-filtro="data-emissao"] .texto'
        ).textContent = this.textContent.toLowerCase();

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !==
          document.querySelector('.filtro-item[data-filtro="data-emissao"]')
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function alterarTipoData(tipo) {
  // Armazena o tipo de data selecionado
  window.tipoDataSelecionado = tipo;

  // Reaplica os filtros atuais com o novo tipo de data
  const periodoAtual = document.querySelector(
    '.filtro-item[data-filtro="periodo"] .texto'
  ).textContent;

  // Lógica para determinar o período atual e refiltar
  // ...
}

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
            <label for="fornecedor">Fornecedor</label>
            <select id="fornecedor" name="fornecedor">
              <option value="">Todos os fornecedores</option>
              <!-- Opções de fornecedores serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo">
            <label for="status">Status</label>
            <select id="status" name="status">
              <option value="">Todos</option>
              <option value="pendente">Pendente</option>
              <option value="registrada">Registrada</option>
              <option value="emitida">Emitida</option>
              <option value="cancelada">Cancelada</option>
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
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="apenas_xml" name="apenas_xml">
              <label for="apenas_xml">Apenas notas com XML</label>
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

    // Carrega a lista de fornecedores
    carregarFornecedores();

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

function carregarFornecedores() {
  // Carrega a lista de fornecedores para o select
  fetch("/api/fornecedores")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#fornecedor");

      data.forEach((fornecedor) => {
        const option = document.createElement("option");
        option.value = fornecedor.id;
        option.textContent = fornecedor.nome;
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
  fetch(`/api/notas_entrada?${params.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}

// Código para limpar filtros
document
  .querySelector('.filtro-item[data-filtro="limpar"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Limpa o campo de pesquisa
    document.querySelector(".input-pesquisa").value = "";

    // Restaura os textos dos filtros
    document.querySelector(
      '.filtro-item[data-filtro="periodo"] .texto'
    ).textContent = "Últimos 30 dias";
    document.querySelector(
      '.filtro-item[data-filtro="data-emissao"] .texto'
    ).textContent = "data de emissão";

    // Ativa o filtro "Todas"
    document.querySelectorAll(".filtro-status").forEach((f) => {
      f.classList.remove("ativo");
    });
    document
      .querySelector('.filtro-status[data-status="todas"]')
      .classList.add("ativo");

    // Carrega todas as notas
    fetch("/api/notas_entrada")
      .then((response) => response.json())
      .then((data) => {
        atualizarListaNotas(data);
      });
  });
```

### Filtros por Status

Os filtros por status permitem visualizar notas em diferentes estados:

```javascript
// Código para filtrar por status
document.querySelectorAll(".filtro-status").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-status").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por status
    const status = this.getAttribute("data-status");
    filtrarPorStatus(status);
  });
});

function filtrarPorStatus(status) {
  // Lógica para filtrar notas por status
  let url = "/api/notas_entrada";

  if (status !== "todas") {
    url += `?status=${status}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}
```

### Seleção de Notas

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de notas
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
        carregarNotas();
      }
    });
  }
});

function ordenarTabela(coluna, direcao) {
  // Lógica para ordenar a tabela
  fetch(`/api/notas_entrada?ordenar_por=${coluna}&direcao=${direcao}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaNotas(data);
    });
}
```

### Importação de XML

O botão de importação permite carregar XMLs de notas fiscais:

```javascript
// Código para importação de XML
document
  .querySelector("#btn-importar-xml")
  .addEventListener("click", function () {
    // Abre modal de importação
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Importar XML da NFe</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="opcoes-importacao">
          <div class="opcao-importacao">
            <h3 class="opcao-titulo">Arquivo XML</h3>
            <p class="opcao-descricao">Importe um ou mais arquivos XML de notas fiscais.</p>
            <form id="form-upload-xml">
              <div class="area-upload">
                <input type="file" id="arquivo-xml" name="arquivo-xml" accept=".xml" multiple>
                <label for="arquivo-xml" class="label-upload">
                  <span class="icone icone-upload"></span>
                  <span class="texto">Selecionar arquivos XML</span>
                </label>
              </div>
              <div class="arquivos-selecionados"></div>
            </form>
          </div>
          <div class="opcao-importacao">
            <h3 class="opcao-titulo">Importar da Pasta</h3>
            <p class="opcao-descricao">Configure uma pasta para importação automática de XMLs.</p>
            <button class="botao botao-secundario" id="btn-configurar-pasta">
              <span class="icone icone-pasta"></span>
              <span class="texto">Configurar Pasta</span>
            </button>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-importacao">Cancelar</button>
        <button class="botao botao-primario" id="btn-importar">Importar</button>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-cancelar-importacao")
      .addEventListener("click", () => {
        document.body.removeChild(modal);
      });

    // Exibe os arquivos selecionados
    modal.querySelector("#arquivo-xml").addEventListener("change", function () {
      const arquivosSelecionados = document.querySelector(
        ".arquivos-selecionados"
      );
      arquivosSelecionados.innerHTML = "";

      if (this.files.length > 0) {
        const lista = document.createElement("ul");
        lista.classList.add("lista-arquivos");

        Array.from(this.files).forEach((file) => {
          const item = document.createElement("li");
          item.classList.add("item-arquivo");
          item.innerHTML = `
          <span class="icone icone-xml"></span>
          <span class="nome-arquivo">${file.name}</span>
          <span class="tamanho-arquivo">(${formatarTamanho(file.size)})</span>
        `;
          lista.appendChild(item);
        });

        arquivosSelecionados.appendChild(lista);
      }
    });

    modal
      .querySelector("#btn-configurar-pasta")
      .addEventListener("click", () => {
        abrirModalConfigurarPasta();
      });

    modal.querySelector("#btn-importar").addEventListener("click", () => {
      const arquivos = document.querySelector("#arquivo-xml").files;

      if (arquivos.length > 0) {
        importarArquivosXML(arquivos);
      } else {
        alert("Selecione pelo menos um arquivo XML para importar.");
      }
    });
  });

function formatarTamanho(bytes) {
  if (bytes === 0) return "0 Bytes";

  const k = 1024;
  const sizes = ["Bytes", "KB", "MB", "GB"];
  const i = Math.floor(Math.log(bytes) / Math.log(k));

  return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + " " + sizes[i];
}

function importarArquivosXML(arquivos) {
  // Cria um FormData para envio dos arquivos
  const formData = new FormData();

  Array.from(arquivos).forEach((file) => {
    formData.append("arquivos", file);
  });

  // Exibe modal de progresso
  const modalProgresso = document.createElement("div");
  modalProgresso.classList.add("modal");
  modalProgresso.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Importando XMLs</h2>
      </div>
      <div class="modal-corpo">
        <div class="progresso-container">
          <div class="progresso-texto">Processando arquivos...</div>
          <div class="progresso-barra">
            <div class="progresso-preenchimento" style="width: 0%"></div>
          </div>
          <div class="progresso-status">0/${arquivos.length} concluídos</div>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modalProgresso);

  // Envia os arquivos para o servidor
  fetch("/api/notas_entrada/importar-xml", {
    method: "POST",
    body: formData,
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao importar XMLs");
    })
    .then((data) => {
      // Remove o modal de progresso
      document.body.removeChild(modalProgresso);

      // Exibe modal de resultado
      const modalResultado = document.createElement("div");
      modalResultado.classList.add("modal");
      modalResultado.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Importação Concluída</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="resultado-importacao">
            <div class="resultado-item">
              <span class="resultado-label">Total de arquivos:</span>
              <span class="resultado-valor">${data.total}</span>
            </div>
            <div class="resultado-item">
              <span class="resultado-label">Importados com sucesso:</span>
              <span class="resultado-valor">${data.sucesso}</span>
            </div>
            <div class="resultado-item">
              <span class="resultado-label">Falhas:</span>
              <span class="resultado-valor">${data.falhas}</span>
            </div>
          </div>
          ${
            data.falhas > 0
              ? `
            <div class="falhas-container">
              <h3 class="falhas-titulo">Detalhes das falhas:</h3>
              <ul class="falhas-lista">
                ${data.detalhes_falhas
                  .map(
                    (falha) => `
                  <li class="falha-item">
                    <span class="falha-arquivo">${falha.arquivo}</span>
                    <span class="falha-mensagem">${falha.mensagem}</span>
                  </li>
                `
                  )
                  .join("")}
              </ul>
            </div>
          `
              : ""
          }
        </div>
        <div class="modal-rodape">
          <button class="botao botao-primario" id="btn-fechar-resultado">Fechar</button>
        </div>
      </div>
    `;

      document.body.appendChild(modalResultado);

      // Adiciona eventos aos botões do modal
      modalResultado
        .querySelector(".botao-fechar")
        .addEventListener("click", () => {
          document.body.removeChild(modalResultado);

          // Atualiza a lista de notas
          carregarNotas();
        });

      modalResultado
        .querySelector("#btn-fechar-resultado")
        .addEventListener("click", () => {
          document.body.removeChild(modalResultado);

          // Atualiza a lista de notas
          carregarNotas();
        });
    })
    .catch((error) => {
      // Remove o modal de progresso
      document.body.removeChild(modalProgresso);

      // Exibe mensagem de erro
      alert(`Erro ao importar XMLs: ${error.message}`);
    });
}

function abrirModalConfigurarPasta() {
  // Abre modal para configuração de pasta
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Configurar Pasta de Importação</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="pasta_importacao">Pasta de Importação</label>
          <div class="campo-pasta">
            <input type="text" id="pasta_importacao" name="pasta_importacao" placeholder="Caminho da pasta" readonly>
            <button class="botao botao-secundario" id="btn-selecionar-pasta">
              <span class="icone icone-pasta"></span>
              <span class="texto">Selecionar</span>
            </button>
          </div>
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input type="checkbox" id="importacao_automatica" name="importacao_automatica">
            <label for="importacao_automatica">Importar automaticamente novos arquivos</label>
          </div>
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input type="checkbox" id="mover_apos_importacao" name="mover_apos_importacao">
            <label for="mover_apos_importacao">Mover arquivos após importação</label>
          </div>
        </div>
        <div class="form-grupo pasta-destino" style="display: none;">
          <label for="pasta_destino">Pasta de Destino</label>
          <div class="campo-pasta">
            <input type="text" id="pasta_destino" name="pasta_destino" placeholder="Caminho da pasta" readonly>
            <button class="botao botao-secundario" id="btn-selecionar-destino">
              <span class="icone icone-pasta"></span>
              <span class="texto">Selecionar</span>
            </button>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-pasta">Cancelar</button>
        <button class="botao botao-primario" id="btn-salvar-pasta">Salvar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-pasta").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  // Exibe/oculta campo de pasta de destino
  modal
    .querySelector("#mover_apos_importacao")
    .addEventListener("change", function () {
      const pastaDestino = modal.querySelector(".pasta-destino");

      if (this.checked) {
        pastaDestino.style.display = "block";
      } else {
        pastaDestino.style.display = "none";
      }
    });

  modal.querySelector("#btn-selecionar-pasta").addEventListener("click", () => {
    // Simulação de seleção de pasta
    modal.querySelector("#pasta_importacao").value = "C:\\XMLs\\Importacao";
  });

  modal
    .querySelector("#btn-selecionar-destino")
    .addEventListener("click", () => {
      // Simulação de seleção de pasta
      modal.querySelector("#pasta_destino").value = "C:\\XMLs\\Processados";
    });

  modal.querySelector("#btn-salvar-pasta").addEventListener("click", () => {
    // Coleta os dados do formulário
    const pastaImportacao = modal.querySelector("#pasta_importacao").value;
    const importacaoAutomatica = modal.querySelector(
      "#importacao_automatica"
    ).checked;
    const moverAposImportacao = modal.querySelector(
      "#mover_apos_importacao"
    ).checked;
    const pastaDestino = modal.querySelector("#pasta_destino").value;

    if (pastaImportacao) {
      // Salva as configurações
      salvarConfiguracaoPasta(
        pastaImportacao,
        importacaoAutomatica,
        moverAposImportacao,
        pastaDestino
      );

      // Fecha o modal
      document.body.removeChild(modal);
    } else {
      alert("Selecione a pasta de importação.");
    }
  });
}

function salvarConfiguracaoPasta(pasta, automatica, mover, destino) {
  // Envia as configurações para o servidor
  fetch("/api/notas_entrada/configurar-pasta", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      pasta_importacao: pasta,
      importacao_automatica: automatica,
      mover_apos_importacao: mover,
      pasta_destino: destino,
    }),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar configurações");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Configurações salvas com sucesso!");
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao salvar configurações: ${error.message}`);
    });
}
```

### Inclusão de Nova Nota Fiscal

O botão de inclusão redireciona para o formulário de cadastro:

```javascript
// Código para inclusão de nova nota fiscal
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/notas_entrada/novo";
});
```

### Menu de Ações Adicionais

O menu de ações adicionais oferece opções extras:

```javascript
// Código para menu de ações adicionais
document.querySelector("#btn-acoes").addEventListener("click", function () {
  // Verifica se o dropdown já está aberto
  const dropdownExistente = document.querySelector(".dropdown-menu");

  if (dropdownExistente) {
    // Remove o dropdown existente
    document.body.removeChild(dropdownExistente);
    return;
  }

  // Cria o dropdown
  const dropdown = document.createElement("div");
  dropdown.classList.add("dropdown-menu");
  dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-acao="exportar">
      <span class="icone icone-exportar"></span>
      <span class="texto">Exportar notas</span>
    </a>
    <a href="#" class="dropdown-item" data-acao="manifestar">
      <span class="icone icone-manifestar"></span>
      <span class="texto">Manifestação do destinatário</span>
    </a>
    <div class="dropdown-divider"></div>
    <a href="#" class="dropdown-item" data-acao="configuracoes">
      <span class="icone icone-configuracoes"></span>
      <span class="texto">Configurações</span>
    </a>
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

      const acao = this.getAttribute("data-acao");
      executarAcao(acao);

      // Remove o dropdown
      document.body.removeChild(dropdown);
    });
  });

  // Fecha o dropdown ao clicar fora
  document.addEventListener("click", function fecharDropdown(e) {
    if (
      !dropdown.contains(e.target) &&
      e.target !== document.querySelector("#btn-acoes")
    ) {
      document.body.removeChild(dropdown);
      document.removeEventListener("click", fecharDropdown);
    }
  });
});

function executarAcao(acao) {
  switch (acao) {
    case "exportar":
      abrirModalExportacao();
      break;
    case "manifestar":
      abrirModalManifestacao();
      break;
    case "configuracoes":
      window.location.href = "/notas_entrada/configuracoes";
      break;
  }
}
```

### Alteração de Ambiente

O link para alterar ambiente permite trocar entre ambiente de testes e produção:

```javascript
// Código para alteração de ambiente
document
  .querySelector("#btn-alterar-ambiente")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre modal de confirmação
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Alterar Ambiente</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <p class="modal-descricao">
          Você está prestes a alterar o ambiente de <strong>testes</strong> para <strong>produção</strong>.
        </p>
        <p class="modal-aviso">
          <span class="icone icone-alerta"></span>
          No ambiente de produção, as notas fiscais geradas terão valor fiscal e serão transmitidas para a SEFAZ.
        </p>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-ambiente">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar-ambiente">Alterar para Produção</button>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-cancelar-ambiente")
      .addEventListener("click", () => {
        document.body.removeChild(modal);
      });

    modal
      .querySelector("#btn-confirmar-ambiente")
      .addEventListener("click", () => {
        // Altera o ambiente
        alterarAmbiente();

        // Fecha o modal
        document.body.removeChild(modal);
      });
  });

function alterarAmbiente() {
  // Envia a solicitação para alterar o ambiente
  fetch("/api/notas_entrada/alterar-ambiente", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      ambiente: "producao",
    }),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao alterar ambiente");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Ambiente alterado para produção com sucesso!");

      // Recarrega a página
      window.location.reload();
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao alterar ambiente: ${error.message}`);
    });
}
```

## Formulário de Cadastro de Nota Fiscal

Quando o usuário clica em "Incluir nota fiscal", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Nova Nota Fiscal de Entrada</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-nota">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações da Nota</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="numero">Número *</label>
            <input type="text" id="numero" name="numero" required />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="serie">Série *</label>
            <input type="text" id="serie" name="serie" required />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="data_emissao">Data de Emissão *</label>
            <input type="date" id="data_emissao" name="data_emissao" required />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="data_entrada">Data de Entrada *</label>
            <input type="date" id="data_entrada" name="data_entrada" required />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="fornecedor">Fornecedor *</label>
            <select id="fornecedor" name="fornecedor" required>
              <option value="">Selecione...</option>
              <!-- Opções de fornecedores serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_total">Valor Total *</label>
            <input
              type="text"
              id="valor_total"
              name="valor_total"
              placeholder="0,00"
              required
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="observacoes">Observações</label>
            <textarea id="observacoes" name="observacoes" rows="3"></textarea>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Produtos</h2>
        <div class="form-linha">
          <button
            type="button"
            class="botao botao-secundario"
            id="btn-adicionar-produto"
          >
            <span class="icone icone-adicionar"></span>
            <span class="texto">Adicionar Produto</span>
          </button>
        </div>
        <div class="tabela-produtos-container">
          <table class="tabela-produtos-nota">
            <thead>
              <tr>
                <th class="coluna-produto">Produto</th>
                <th class="coluna-quantidade">Quantidade</th>
                <th class="coluna-valor">Valor Unitário</th>
                <th class="coluna-desconto">Desconto</th>
                <th class="coluna-subtotal">Subtotal</th>
                <th class="coluna-acoes"></th>
              </tr>
            </thead>
            <tbody id="produtos-nota">
              <!-- Produtos serão adicionados dinamicamente -->
            </tbody>
          </table>
        </div>
        <div class="form-linha totais-nota">
          <div class="totais-item">
            <span class="totais-label">Subtotal:</span>
            <span class="totais-valor" id="subtotal-nota">R$ 0,00</span>
          </div>
          <div class="totais-item">
            <span class="totais-label">Descontos:</span>
            <span class="totais-valor" id="descontos-nota">R$ 0,00</span>
          </div>
          <div class="totais-item totais-item-destaque">
            <span class="totais-label">Total:</span>
            <span class="totais-valor" id="total-nota">R$ 0,00</span>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Impostos</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="base_calculo_icms">Base de Cálculo ICMS</label>
            <input
              type="text"
              id="base_calculo_icms"
              name="base_calculo_icms"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_icms">Valor ICMS</label>
            <input
              type="text"
              id="valor_icms"
              name="valor_icms"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="base_calculo_icms_st">Base de Cálculo ICMS ST</label>
            <input
              type="text"
              id="base_calculo_icms_st"
              name="base_calculo_icms_st"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_icms_st">Valor ICMS ST</label>
            <input
              type="text"
              id="valor_icms_st"
              name="valor_icms_st"
              placeholder="0,00"
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_ipi">Valor IPI</label>
            <input
              type="text"
              id="valor_ipi"
              name="valor_ipi"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_pis">Valor PIS</label>
            <input
              type="text"
              id="valor_pis"
              name="valor_pis"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_cofins">Valor COFINS</label>
            <input
              type="text"
              id="valor_cofins"
              name="valor_cofins"
              placeholder="0,00"
            />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_frete">Valor Frete</label>
            <input
              type="text"
              id="valor_frete"
              name="valor_frete"
              placeholder="0,00"
            />
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

.tabela-produtos-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.tabela-produtos-nota {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos-nota th,
.tabela-produtos-nota td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos-nota th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-produto {
  min-width: 250px;
}

.coluna-quantidade,
.coluna-valor,
.coluna-desconto,
.coluna-subtotal {
  width: 120px;
}

.coluna-acoes {
  width: 80px;
  text-align: right;
}

.totais-nota {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 8px;
}

.totais-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.totais-label {
  font-size: 14px;
  color: #666666;
}

.totais-valor {
  font-size: 14px;
  color: #333333;
  min-width: 100px;
  text-align: right;
}

.totais-item-destaque .totais-label,
.totais-item-destaque .totais-valor {
  font-size: 16px;
  font-weight: 500;
  color: #1890ff;
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .filtros-status {
    flex-wrap: wrap;
  }

  .filtro-status {
    flex: 1;
    min-width: 120px;
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

  .filtros-rapidos {
    margin-top: 12px;
  }

  .coluna-serie,
  .coluna-data {
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
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .filtro-status {
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
- Roxo (indicador pendentes): #722ed1
- Laranja (indicador registradas): #fa8c16
- Verde (indicador emitidas): #52c41a
- Vermelho (indicador canceladas): #f5222d
- Amarelo (alerta): #faad14
- Amarelo claro (background alerta): #fffbe6
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

### Indicadores de Status

```css
.indicador {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-todas {
  background-color: #999999;
}

.indicador-pendentes {
  background-color: #722ed1;
}

.indicador-registradas {
  background-color: #fa8c16;
}

.indicador-emitidas {
  background-color: #52c41a;
}

.indicador-canceladas {
  background-color: #f5222d;
}
```

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

.badge-pendente {
  background-color: #f0f5ff;
  color: #722ed1;
}

.badge-registrada {
  background-color: #fff7e6;
  color: #fa8c16;
}

.badge-emitida {
  background-color: #f6ffed;
  color: #52c41a;
}

.badge-cancelada {
  background-color: #fff1f0;
  color: #f5222d;
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

### Dropdowns

```css
.dropdown-menu {
  position: absolute;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  z-index: 1000;
  min-width: 160px;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
}

.dropdown-divider {
  height: 1px;
  background-color: #e0e0e0;
  margin: 4px 0;
}
```

## Fluxos de Navegação

1. **Listagem de Notas Fiscais**:

   - A tela inicial exibe todas as notas fiscais cadastradas
   - Filtros permitem refinar a visualização por status, período ou outros critérios
   - Pesquisa permite localizar notas específicas por cliente ou número

2. **Importação de XML**:

   - Clique no botão "Importar XML da NFe" abre modal de importação
   - Seleção de arquivos XML para upload
   - Processamento dos arquivos e exibição de resultados
   - Configuração de pasta para importação automática

3. **Cadastro de Nova Nota Fiscal**:

   - Clique no botão "Incluir nota fiscal" redireciona para o formulário de cadastro
   - Preenchimento do formulário com dados da nota e adição de produtos
   - Salvamento adiciona a nota à listagem

4. **Alteração de Ambiente**:
   - Clique no link "alterar ambiente" abre modal de confirmação
   - Confirmação altera o ambiente de testes para produção
   - Notas geradas em produção têm valor fiscal e são transmitidas para a SEFAZ

## Conclusão

O módulo "Notas de Entrada" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente de notas fiscais de entrada. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, importação de XML e cadastro de notas de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para indicar os diferentes status das notas. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para a gestão de notas fiscais de entrada, como importação de XML, cadastro manual, alteração de ambiente e configurações avançadas, atendendo às necessidades de negócios que trabalham com documentos fiscais de entrada.
