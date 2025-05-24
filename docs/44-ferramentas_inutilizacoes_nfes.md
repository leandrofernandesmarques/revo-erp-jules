# Análise do Módulo Ferramentas - Inutilizações de NFes

## Visão Geral

O subitem "Inutilizações de NFes" do módulo Ferramentas do ERP Revo oferece funcionalidades para gerenciamento de inutilizações de numeração de Notas Fiscais Eletrônicas (NFes). Esta seção permite aos usuários registrar, consultar e gerenciar números de NFes que precisam ser inutilizados por algum motivo, como erros de emissão ou cancelamentos.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <a href="/ferramentas_geral">ferramentas</a>
    <span class="separator">/</span>
    <span class="current">números inutilizados</span>
  </div>
  <h1>Números inutilizados</h1>
</div>
```

### Barra de Ações

```html
<div class="actions-bar">
  <div class="actions-container">
    <button type="button" class="btn btn-primary" id="btn-inutilizar">
      <i class="icon-plus"></i> inutilizar numeração
    </button>

    <div class="dropdown">
      <button
        type="button"
        class="btn btn-outline dropdown-toggle"
        id="btn-actions"
      >
        Ações <i class="icon-chevron-down"></i>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item" data-action="export-csv"
          >Exportar CSV</a
        >
        <a href="#" class="dropdown-item" data-action="export-pdf"
          >Exportar PDF</a
        >
        <a href="#" class="dropdown-item" data-action="print">Imprimir</a>
      </div>
    </div>
  </div>
</div>
```

### Barra de Filtros

```html
<div class="filters-bar">
  <div class="search-container">
    <input
      type="text"
      class="search-input"
      placeholder="Pesquise pelo número do protocolo ou de série"
    />
    <button type="button" class="search-button">
      <i class="icon-search"></i>
    </button>
    <button type="button" class="filter-button">
      <i class="icon-filter"></i>
    </button>
  </div>

  <div class="filters-container">
    <a href="#" class="filter-link">
      <i class="icon-calendar"></i> por periodo
    </a>
    <a href="#" class="filter-link"> <i class="icon-document"></i> modelo </a>
    <a href="#" class="filter-link"> <i class="icon-clock"></i> data e hora </a>
  </div>
</div>
```

### Conteúdo Principal (Estado Vazio)

```html
<div class="content-container">
  <div class="empty-state">
    <div class="empty-state-icon">
      <img
        src="/assets/images/empty-state-nfe.svg"
        alt="Nenhum registro encontrado"
      />
    </div>
    <div class="empty-state-message">
      <h3>Nenhum registro encontrado</h3>
      <p>Nenhum registro foi encontrado.</p>
    </div>
  </div>
</div>
```

### Rodapé de Ajuda

```html
<div class="help-footer">
  <p>Ficou com alguma dúvida?</p>
  <a href="/ajuda/inutilizacao_nfe" class="help-link"> Ajuda do Sistema ERP </a>
</div>
```

### Menu Lateral

```html
<div class="sidebar">
  <div class="logo">
    <a href="/inicio"><img src="/assets/logo-Revo.svg" alt="Logo Revo" /></a>
  </div>
  <div class="menu-container">
    <ul class="menu">
      <li>
        <a href="/inicio"><i class="icon-home"></i> Início</a>
      </li>
      <li>
        <a href="/indice"><i class="icon-list"></i> Índice</a>
      </li>
      <li>
        <a href="/dashboard"><i class="icon-dashboard"></i> Dashboard</a>
      </li>
      <li>
        <a href="/agenda"><i class="icon-calendar"></i> Agenda</a>
      </li>
      <li>
        <a href="/minha_conta"><i class="icon-user"></i> Minha conta</a>
      </li>
      <li>
        <a href="/integracoes"><i class="icon-link"></i> Integrações</a>
      </li>
      <li>
        <a href="/upgrade_plano"
          ><i class="icon-upgrade"></i> Upgrade de plano</a
        >
      </li>
      <li>
        <a href="/sobre_versao"><i class="icon-info"></i> Sobre a versão</a>
      </li>
      <li>
        <a href="/ajuda_erp"><i class="icon-help"></i> Ajuda do ERP</a>
      </li>
      <li class="active">
        <a href="/ferramentas_geral"><i class="icon-tools"></i> Ferramentas</a>
      </li>
      <li>
        <a href="/loja_extensoes"
          ><i class="icon-store"></i> Loja de extensões</a
        >
      </li>
      <li>
        <a href="/shopping_servicos"
          ><i class="icon-shopping"></i> Shopping de Serviços</a
        >
      </li>
    </ul>
  </div>
</div>
```

## Estilos CSS

### Cores Principais

```css
:root {
  --primary-color: #0077b6;
  --secondary-color: #4361ee;
  --accent-color: #ff5a5f;
  --background-color: #f8f9fa;
  --text-color: #333333;
  --border-color: #e0e0e0;
  --success-color: #28a745;
  --warning-color: #ffc107;
  --danger-color: #dc3545;
  --light-gray: #f1f3f5;
  --section-divider: #eaeaea;
}
```

### Estilos do Cabeçalho

```css
.header {
  padding: 20px 30px;
  background-color: #fff;
  border-bottom: 1px solid var(--border-color);
}

.breadcrumb {
  font-size: 14px;
  color: #666;
  margin-bottom: 10px;
}

.breadcrumb a {
  color: var(--primary-color);
  text-decoration: none;
}

.breadcrumb .separator {
  margin: 0 5px;
}

.breadcrumb .current {
  font-weight: 500;
}

h1 {
  font-size: 24px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0;
}
```

### Estilos da Barra de Ações

```css
.actions-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 30px;
  background-color: #fff;
  border-bottom: 1px solid var(--border-color);
}

.actions-container {
  display: flex;
  align-items: center;
  gap: 10px;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-toggle {
  display: flex;
  align-items: center;
  gap: 5px;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 1000;
  display: none;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.dropdown-menu.show {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 15px;
  color: var(--text-color);
  text-decoration: none;
  white-space: nowrap;
}

.dropdown-item:hover {
  background-color: var(--light-gray);
}
```

### Estilos da Barra de Filtros

```css
.filters-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 30px;
  background-color: #fff;
  border-bottom: 1px solid var(--border-color);
}

.search-container {
  display: flex;
  align-items: center;
  width: 300px;
  position: relative;
}

.search-input {
  width: 100%;
  padding: 8px 12px;
  padding-right: 80px;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 14px;
}

.search-button {
  position: absolute;
  right: 40px;
  top: 0;
  height: 100%;
  width: 40px;
  background: transparent;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.filter-button {
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 40px;
  background: transparent;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.filters-container {
  display: flex;
  align-items: center;
}

.filter-link {
  display: flex;
  align-items: center;
  padding: 8px 12px;
  margin-right: 10px;
  color: var(--text-color);
  text-decoration: none;
  font-size: 14px;
  border-radius: 4px;
  transition: all 0.2s ease;
}

.filter-link:hover {
  background-color: var(--light-gray);
}

.filter-link.active {
  background-color: var(--light-gray);
  color: var(--primary-color);
  font-weight: 500;
}

.filter-link i {
  margin-right: 5px;
}
```

### Estilos do Conteúdo Principal (Estado Vazio)

```css
.content-container {
  padding: 30px;
  background-color: var(--background-color);
  min-height: calc(100vh - 180px);
}

.empty-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  background-color: #fff;
  border-radius: 8px;
  padding: 40px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  max-width: 600px;
  margin: 0 auto;
}

.empty-state-icon {
  margin-bottom: 20px;
}

.empty-state-icon img {
  width: 120px;
  height: auto;
}

.empty-state-message h3 {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.empty-state-message p {
  font-size: 14px;
  color: #666;
  margin: 0;
}
```

### Estilos do Rodapé de Ajuda

```css
.help-footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px 0;
  background-color: var(--background-color);
  border-top: 1px solid var(--border-color);
  text-align: center;
}

.help-footer p {
  font-size: 14px;
  color: #666;
  margin: 0 0 5px 0;
}

.help-link {
  color: var(--primary-color);
  text-decoration: none;
  font-size: 14px;
}

.help-link:hover {
  text-decoration: underline;
}
```

### Estilos do Menu Lateral

```css
.sidebar {
  width: 250px;
  background-color: #fff;
  border-right: 1px solid var(--border-color);
  height: 100vh;
  position: fixed;
  left: 0;
  top: 0;
}

.logo {
  padding: 20px;
  text-align: center;
  border-bottom: 1px solid var(--border-color);
}

.logo img {
  max-width: 120px;
}

.menu-container {
  padding: 15px 0;
}

.menu {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu li {
  margin-bottom: 2px;
}

.menu li a {
  display: flex;
  align-items: center;
  padding: 12px 20px;
  color: var(--text-color);
  text-decoration: none;
  transition: all 0.2s ease;
}

.menu li.active a {
  background-color: var(--light-gray);
  color: var(--primary-color);
  border-left: 3px solid var(--primary-color);
}

.menu li a i {
  margin-right: 10px;
  font-size: 18px;
}

.menu li a:hover {
  background-color: var(--light-gray);
}
```

## Interações JavaScript

### Dropdown de Ações

```javascript
// Código para gerenciar o dropdown de ações
document.querySelector("#btn-actions").addEventListener("click", function () {
  const dropdownMenu = this.nextElementSibling;
  dropdownMenu.classList.toggle("show");
});

// Fechar dropdown ao clicar fora dele
document.addEventListener("click", function (e) {
  if (!e.target.matches("#btn-actions") && !e.target.closest("#btn-actions")) {
    const dropdowns = document.querySelectorAll(".dropdown-menu");
    dropdowns.forEach((dropdown) => {
      if (dropdown.classList.contains("show")) {
        dropdown.classList.remove("show");
      }
    });
  }
});

// Gerenciar ações do dropdown
document.querySelectorAll(".dropdown-item").forEach((item) => {
  item.addEventListener("click", function (e) {
    e.preventDefault();

    const action = this.getAttribute("data-action");

    switch (action) {
      case "export-csv":
        exportToCSV();
        break;
      case "export-pdf":
        exportToPDF();
        break;
      case "print":
        printList();
        break;
    }
  });
});

function exportToCSV() {
  // Função para exportar dados para CSV
  console.log("Exportando para CSV...");

  // Implementação da exportação para CSV
  // ...
}

function exportToPDF() {
  // Função para exportar dados para PDF
  console.log("Exportando para PDF...");

  // Implementação da exportação para PDF
  // ...
}

function printList() {
  // Função para imprimir a lista
  console.log("Imprimindo lista...");

  // Implementação da impressão
  window.print();
}
```

### Pesquisa e Filtros

```javascript
// Código para gerenciar a pesquisa de inutilizações
document.querySelector(".search-input").addEventListener("keyup", function (e) {
  if (e.key === "Enter") {
    searchInutilizacoes(this.value);
  }
});

document.querySelector(".search-button").addEventListener("click", function () {
  const searchTerm = document.querySelector(".search-input").value;
  searchInutilizacoes(searchTerm);
});

function searchInutilizacoes(term) {
  // Função para pesquisar inutilizações com base no termo informado
  console.log("Pesquisando inutilizações com o termo:", term);

  // Aqui seria implementada a lógica para filtrar as inutilizações
  // e atualizar a lista exibida na interface

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/nfe-inutilizacoes/search?term=${encodeURIComponent(term)}`)
    .then((response) => response.json())
    .then((data) => {
      updateInutilizacoesList(data);
    })
    .catch((error) => {
      console.error("Erro ao pesquisar inutilizações:", error);
    });
}

// Código para gerenciar os filtros
document.querySelectorAll(".filter-link").forEach((filter) => {
  filter.addEventListener("click", function (e) {
    e.preventDefault();

    // Remover classe active de todos os filtros
    document.querySelectorAll(".filter-link").forEach((item) => {
      item.classList.remove("active");
    });

    // Adicionar classe active ao filtro clicado
    this.classList.add("active");

    // Aplicar o filtro selecionado
    const filterType = this.textContent.trim();
    applyFilter(filterType);
  });
});

function applyFilter(filterType) {
  // Função para aplicar o filtro selecionado
  console.log("Aplicando filtro:", filterType);

  switch (filterType) {
    case "por periodo":
      // Exibir seletor de período
      showPeriodSelector();
      break;
    case "modelo":
      // Exibir seletor de modelo
      showModelSelector();
      break;
    case "data e hora":
      // Ordenar por data e hora
      sortByDateTime();
      break;
  }
}

function showPeriodSelector() {
  // Função para exibir o seletor de período
  const modal = document.createElement("div");
  modal.className = "modal";
  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Selecionar Período</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label for="start-date">Data Inicial</label>
          <input type="date" id="start-date" class="form-control" />
        </div>
        <div class="form-group">
          <label for="end-date">Data Final</label>
          <input type="date" id="end-date" class="form-control" />
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="cancel-period">Cancelar</button>
        <button class="btn btn-primary" id="apply-period">Aplicar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#cancel-period").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#apply-period").addEventListener("click", () => {
    const startDate = document.querySelector("#start-date").value;
    const endDate = document.querySelector("#end-date").value;

    if (startDate && endDate) {
      fetchInutilizacoes({ startDate, endDate });
    }

    document.body.removeChild(modal);
  });
}

function showModelSelector() {
  // Função para exibir o seletor de modelo
  const modal = document.createElement("div");
  modal.className = "modal";
  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Selecionar Modelo</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label>Modelo</label>
          <div class="radio-group">
            <label>
              <input type="radio" name="modelo" value="55" checked> NFe (55)
            </label>
            <label>
              <input type="radio" name="modelo" value="65"> NFCe (65)
            </label>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="cancel-model">Cancelar</button>
        <button class="btn btn-primary" id="apply-model">Aplicar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#cancel-model").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#apply-model").addEventListener("click", () => {
    const modelo = document.querySelector('input[name="modelo"]:checked').value;
    fetchInutilizacoes({ modelo });
    document.body.removeChild(modal);
  });
}

function sortByDateTime() {
  // Função para ordenar por data e hora
  fetchInutilizacoes({ sort: "datetime" });
}

function fetchInutilizacoes(filters) {
  // Função para buscar inutilizações com base nos filtros
  console.log("Buscando inutilizações com filtros:", filters);

  // Construir query string com os filtros
  const queryParams = new URLSearchParams();

  Object.entries(filters).forEach(([key, value]) => {
    queryParams.append(key, value);
  });

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/nfe-inutilizacoes?${queryParams.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      updateInutilizacoesList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar inutilizações:", error);
    });
}

function updateInutilizacoesList(inutilizacoes) {
  // Função para atualizar a lista de inutilizações na interface
  const contentContainer = document.querySelector(".content-container");

  if (inutilizacoes.length === 0) {
    // Exibir estado vazio
    contentContainer.innerHTML = `
      <div class="empty-state">
        <div class="empty-state-icon">
          <img src="/assets/images/empty-state-nfe.svg" alt="Nenhum registro encontrado" />
        </div>
        <div class="empty-state-message">
          <h3>Nenhum registro encontrado</h3>
          <p>Nenhum registro foi encontrado.</p>
        </div>
      </div>
    `;
  } else {
    // Construir e exibir a lista de inutilizações
    let html = `
      <div class="inutilizacoes-list">
        <table class="table">
          <thead>
            <tr>
              <th>Protocolo</th>
              <th>Modelo</th>
              <th>Série</th>
              <th>Numeração</th>
              <th>Data/Hora</th>
              <th>Justificativa</th>
              <th>Ações</th>
            </tr>
          </thead>
          <tbody>
    `;

    inutilizacoes.forEach((item) => {
      html += `
        <tr>
          <td>${item.protocolo}</td>
          <td>${item.modelo}</td>
          <td>${item.serie}</td>
          <td>${item.numeracao_inicial} a ${item.numeracao_final}</td>
          <td>${item.data_hora}</td>
          <td>${item.justificativa}</td>
          <td>
            <button class="btn btn-sm btn-outline" data-id="${item.id}" data-action="view">
              <i class="icon-eye"></i>
            </button>
            <button class="btn btn-sm btn-outline" data-id="${item.id}" data-action="download">
              <i class="icon-download"></i>
            </button>
          </td>
        </tr>
      `;
    });

    html += `
          </tbody>
        </table>
      </div>
    `;

    contentContainer.innerHTML = html;

    // Adicionar event listeners para as ações
    document.querySelectorAll("[data-action]").forEach((button) => {
      button.addEventListener("click", function () {
        const action = this.getAttribute("data-action");
        const id = this.getAttribute("data-id");

        switch (action) {
          case "view":
            viewInutilizacao(id);
            break;
          case "download":
            downloadInutilizacao(id);
            break;
        }
      });
    });
  }
}
```

### Modal de Inutilização

```javascript
// Código para gerenciar o modal de inutilização
document
  .querySelector("#btn-inutilizar")
  .addEventListener("click", function () {
    showInutilizacaoModal();
  });

function showInutilizacaoModal() {
  // Função para exibir o modal de inutilização
  const modal = document.createElement("div");
  modal.className = "modal";
  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Inutilizar Numeração</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label for="modelo">Modelo</label>
          <select id="modelo" class="form-control">
            <option value="55">NFe (55)</option>
            <option value="65">NFCe (65)</option>
          </select>
        </div>
        <div class="form-group">
          <label for="serie">Série</label>
          <input type="number" id="serie" class="form-control" min="0" max="999" />
        </div>
        <div class="form-group">
          <label for="numeracao-inicial">Numeração Inicial</label>
          <input type="number" id="numeracao-inicial" class="form-control" min="1" />
        </div>
        <div class="form-group">
          <label for="numeracao-final">Numeração Final</label>
          <input type="number" id="numeracao-final" class="form-control" min="1" />
        </div>
        <div class="form-group">
          <label for="justificativa">Justificativa</label>
          <textarea id="justificativa" class="form-control" rows="3" maxlength="255"></textarea>
          <small class="form-text">A justificativa deve ter entre 15 e 255 caracteres.</small>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="cancel-inutilizacao">Cancelar</button>
        <button class="btn btn-primary" id="confirm-inutilizacao">Inutilizar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#cancel-inutilizacao").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#confirm-inutilizacao").addEventListener("click", () => {
    // Validar formulário
    const modelo = document.querySelector("#modelo").value;
    const serie = document.querySelector("#serie").value;
    const numeracaoInicial = document.querySelector("#numeracao-inicial").value;
    const numeracaoFinal = document.querySelector("#numeracao-final").value;
    const justificativa = document.querySelector("#justificativa").value;

    if (!serie || !numeracaoInicial || !numeracaoFinal || !justificativa) {
      alert("Todos os campos são obrigatórios.");
      return;
    }

    if (justificativa.length < 15) {
      alert("A justificativa deve ter no mínimo 15 caracteres.");
      return;
    }

    if (parseInt(numeracaoInicial) > parseInt(numeracaoFinal)) {
      alert("A numeração inicial deve ser menor ou igual à numeração final.");
      return;
    }

    // Enviar requisição para inutilizar numeração
    const data = {
      modelo,
      serie,
      numeracaoInicial,
      numeracaoFinal,
      justificativa,
    };

    inutilizarNumeracao(data);
    document.body.removeChild(modal);
  });
}

function inutilizarNumeracao(data) {
  // Função para enviar requisição de inutilização
  console.log("Inutilizando numeração:", data);

  // Exemplo de chamada AJAX para enviar os dados
  fetch("/api/nfe-inutilizacoes", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(data),
  })
    .then((response) => response.json())
    .then((result) => {
      if (result.success) {
        showSuccessMessage("Numeração inutilizada com sucesso!");
        // Atualizar lista de inutilizações
        fetchInutilizacoes({});
      } else {
        showErrorMessage(result.message || "Erro ao inutilizar numeração.");
      }
    })
    .catch((error) => {
      console.error("Erro ao inutilizar numeração:", error);
      showErrorMessage(
        "Erro ao inutilizar numeração. Tente novamente mais tarde."
      );
    });
}

function showSuccessMessage(message) {
  // Função para exibir mensagem de sucesso
  const toast = document.createElement("div");
  toast.className = "toast toast-success";
  toast.innerHTML = `
    <div class="toast-icon">
      <i class="icon-check"></i>
    </div>
    <div class="toast-content">
      <p>${message}</p>
    </div>
    <button class="toast-close">&times;</button>
  `;

  document.body.appendChild(toast);

  // Remover toast após 5 segundos
  setTimeout(() => {
    document.body.removeChild(toast);
  }, 5000);

  // Adicionar event listener para fechar o toast
  toast.querySelector(".toast-close").addEventListener("click", () => {
    document.body.removeChild(toast);
  });
}

function showErrorMessage(message) {
  // Função para exibir mensagem de erro
  const toast = document.createElement("div");
  toast.className = "toast toast-error";
  toast.innerHTML = `
    <div class="toast-icon">
      <i class="icon-error"></i>
    </div>
    <div class="toast-content">
      <p>${message}</p>
    </div>
    <button class="toast-close">&times;</button>
  `;

  document.body.appendChild(toast);

  // Remover toast após 5 segundos
  setTimeout(() => {
    document.body.removeChild(toast);
  }, 5000);

  // Adicionar event listener para fechar o toast
  toast.querySelector(".toast-close").addEventListener("click", () => {
    document.body.removeChild(toast);
  });
}
```

## Fluxos de Navegação

### Fluxo Principal

1. Usuário acessa o módulo Ferramentas através do menu lateral
2. Usuário seleciona o subitem "Inutilizações de NFes"
3. O sistema exibe a tela de gerenciamento de inutilizações
4. Se não houver inutilizações cadastradas, o sistema exibe o estado vazio
5. Usuário pode incluir uma nova inutilização, pesquisar ou filtrar inutilizações existentes

### Fluxo de Inutilização de Numeração

1. Usuário clica no botão "inutilizar numeração"
2. Sistema exibe modal para configuração da inutilização
3. Usuário preenche as informações necessárias (modelo, série, numeração inicial e final, justificativa)
4. Usuário confirma a inutilização
5. Sistema envia a solicitação de inutilização para a SEFAZ
6. Sistema exibe mensagem de sucesso ou erro
7. Sistema atualiza a lista de inutilizações

### Fluxo de Consulta de Inutilizações

1. Usuário visualiza a lista de inutilizações cadastradas
2. Usuário pode filtrar inutilizações por período ou modelo
3. Usuário pode pesquisar inutilizações pelo número do protocolo ou série
4. Usuário pode ordenar a lista por data e hora
5. Para cada inutilização, o usuário pode:
   - Visualizar detalhes da inutilização
   - Fazer download do XML de inutilização

## Componentes Reutilizáveis

### Botões

```html
<button class="btn btn-primary">Botão Primário</button>
<button class="btn btn-secondary">Botão Secundário</button>
<button class="btn btn-outline">Botão Outline</button>
<button class="btn btn-danger">Botão Perigo</button>
<button class="btn btn-sm">Botão Pequeno</button>
```

```css
.btn {
  display: inline-block;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  text-align: center;
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-primary {
  background-color: var(--primary-color);
  color: #fff;
  border: 1px solid var(--primary-color);
}

.btn-secondary {
  background-color: var(--secondary-color);
  color: #fff;
  border: 1px solid var(--secondary-color);
}

.btn-outline {
  background-color: transparent;
  color: var(--primary-color);
  border: 1px solid var(--primary-color);
}

.btn-danger {
  background-color: var(--danger-color);
  color: #fff;
  border: 1px solid var(--danger-color);
}

.btn-sm {
  padding: 6px 12px;
  font-size: 12px;
}

.btn:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}
```

### Estado Vazio

```html
<div class="empty-state">
  <div class="empty-state-icon">
    <img src="/assets/images/empty-state-icon.svg" alt="Estado vazio" />
  </div>
  <div class="empty-state-message">
    <h3>Título do estado vazio</h3>
    <p>Mensagem explicativa sobre o estado vazio.</p>
  </div>
</div>
```

```css
.empty-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  background-color: #fff;
  border-radius: 8px;
  padding: 40px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  max-width: 600px;
  margin: 0 auto;
}

.empty-state-icon {
  margin-bottom: 20px;
}

.empty-state-icon img {
  width: 120px;
  height: auto;
}

.empty-state-message h3 {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.empty-state-message p {
  font-size: 14px;
  color: #666;
  margin: 0;
}
```

### Modal

```html
<div class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3>Título do Modal</h3>
      <button class="close-button">&times;</button>
    </div>
    <div class="modal-body">Conteúdo do modal</div>
    <div class="modal-footer">
      <button class="btn btn-outline">Cancelar</button>
      <button class="btn btn-primary">Confirmar</button>
    </div>
  </div>
</div>
```

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

.modal-content {
  background-color: #fff;
  border-radius: 8px;
  width: 100%;
  max-width: 500px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.modal-header {
  padding: 15px 20px;
  border-bottom: 1px solid var(--border-color);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.modal-header h3 {
  margin: 0;
  font-size: 18px;
  font-weight: 600;
}

.close-button {
  background: transparent;
  border: none;
  font-size: 24px;
  cursor: pointer;
  color: #666;
}

.modal-body {
  padding: 20px;
}

.modal-footer {
  padding: 15px 20px;
  border-top: 1px solid var(--border-color);
  display: flex;
  justify-content: flex-end;
  gap: 10px;
}
```

### Toast

```html
<div class="toast toast-success">
  <div class="toast-icon">
    <i class="icon-check"></i>
  </div>
  <div class="toast-content">
    <p>Mensagem de sucesso</p>
  </div>
  <button class="toast-close">&times;</button>
</div>
```

```css
.toast {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: flex;
  align-items: center;
  padding: 15px;
  border-radius: 4px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  z-index: 1100;
  min-width: 300px;
  max-width: 400px;
}

.toast-success {
  background-color: #e8f5e9;
  border-left: 4px solid var(--success-color);
}

.toast-error {
  background-color: #ffebee;
  border-left: 4px solid var(--danger-color);
}

.toast-icon {
  margin-right: 15px;
  font-size: 20px;
}

.toast-success .toast-icon {
  color: var(--success-color);
}

.toast-error .toast-icon {
  color: var(--danger-color);
}

.toast-content {
  flex: 1;
}

.toast-content p {
  margin: 0;
  font-size: 14px;
  color: var(--text-color);
}

.toast-close {
  background: transparent;
  border: none;
  font-size: 18px;
  cursor: pointer;
  color: #666;
  margin-left: 10px;
}
```

## Responsividade

```css
/* Estilos para tablets */
@media (max-width: 992px) {
  .sidebar {
    width: 200px;
  }

  .content-container {
    margin-left: 200px;
  }

  .actions-bar,
  .filters-bar {
    flex-wrap: wrap;
    gap: 10px;
  }

  .search-container {
    width: 100%;
    order: 1;
  }

  .filters-container {
    width: 100%;
    order: 3;
    justify-content: flex-start;
    margin-top: 10px;
  }

  .actions-container {
    order: 2;
  }
}

/* Estilos para dispositivos móveis */
@media (max-width: 768px) {
  .sidebar {
    width: 100%;
    height: auto;
    position: relative;
    border-right: none;
    border-bottom: 1px solid var(--border-color);
  }

  .content-container {
    margin-left: 0;
    padding: 15px;
  }

  .menu li a {
    padding: 10px 15px;
  }

  .actions-bar,
  .filters-bar {
    padding: 10px 15px;
  }

  .filter-link {
    padding: 6px 10px;
    font-size: 12px;
  }

  .empty-state {
    padding: 20px;
  }

  .modal-content {
    max-width: 90%;
  }

  .toast {
    left: 20px;
    right: 20px;
    max-width: none;
  }
}
```

## Observações Adicionais

- O subitem "Inutilizações de NFes" do módulo Ferramentas apresenta uma interface intuitiva para gerenciamento de inutilizações de numeração de Notas Fiscais Eletrônicas.
- A tela inicial exibe um estado vazio quando não há inutilizações cadastradas, com orientações claras para o usuário.
- A interface oferece funcionalidades de pesquisa e filtragem para facilitar a localização de inutilizações específicas.
- O sistema utiliza modais para interações que requerem entrada de dados, como a inutilização de numeração.
- A funcionalidade de inutilização de NFes é essencial para empresas que emitem notas fiscais eletrônicas, permitindo o registro formal de números de notas que não serão utilizados.
- A interface mantém o mesmo padrão visual do restante do sistema, garantindo consistência na experiência do usuário.
- O processo de inutilização envolve comunicação com a SEFAZ (Secretaria da Fazenda), seguindo os requisitos legais para este procedimento.
- A justificativa para inutilização é um campo obrigatório e deve seguir as regras estabelecidas pela SEFAZ, com um mínimo de 15 caracteres.
