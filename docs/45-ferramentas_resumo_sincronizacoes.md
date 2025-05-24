# Análise do Módulo Ferramentas - Resumo de Sincronizações

## Visão Geral

O subitem "Resumo de Sincronizações" do módulo Ferramentas do ERP Revo oferece funcionalidades para monitoramento e gerenciamento das sincronizações entre o sistema e plataformas externas, como e-commerces e marketplaces. Esta seção permite aos usuários visualizar o status das sincronizações, identificar pendências e acompanhar o histórico de operações realizadas.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <a href="/ferramentas_geral">Ferramentas</a>
    <span class="separator">/</span>
    <span class="current">resumo de sincronizações</span>
  </div>
  <h1>Resumo de sincronizações</h1>
</div>
```

### Barra de Filtros

```html
<div class="filters-bar">
  <div class="filters-container">
    <a href="#" class="filter-link active">
      <i class="icon-calendar-day"></i> Hoje
    </a>
    <a href="#" class="filter-link"> <i class="icon-clock"></i> pendentes </a>
    <a href="#" class="filter-link">
      <i class="icon-check-circle"></i> finalizadas
    </a>
  </div>
</div>
```

### Conteúdo Principal (Estado Vazio)

```html
<div class="content-container">
  <div class="empty-state">
    <div class="empty-state-icon">
      <img
        src="/assets/images/empty-state-sync.svg"
        alt="Nenhum registro encontrado"
      />
    </div>
    <div class="empty-state-message">
      <h3>Nenhum registro encontrado</h3>
      <p>Tente alterar os filtros e pesquisar novamente</p>
    </div>
  </div>
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

### Estilos da Barra de Filtros

```css
.filters-bar {
  display: flex;
  align-items: center;
  padding: 15px 30px;
  background-color: #fff;
  border-bottom: 1px solid var(--border-color);
}

.filters-container {
  display: flex;
  align-items: center;
  gap: 10px;
}

.filter-link {
  display: flex;
  align-items: center;
  padding: 8px 16px;
  color: var(--text-color);
  text-decoration: none;
  font-size: 14px;
  border-radius: 4px;
  transition: all 0.2s ease;
  border: 1px solid var(--border-color);
}

.filter-link:hover {
  background-color: var(--light-gray);
}

.filter-link.active {
  background-color: var(--primary-color);
  color: #fff;
  border-color: var(--primary-color);
}

.filter-link i {
  margin-right: 5px;
  font-size: 16px;
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
  border: 1px solid #ffd700;
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

### Estilos da Lista de Sincronizações (Quando Houver Dados)

```css
.sync-list {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.sync-list-header {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 100px;
  padding: 15px 20px;
  background-color: var(--light-gray);
  border-bottom: 1px solid var(--border-color);
}

.sync-list-header span {
  font-weight: 600;
  font-size: 14px;
  color: var(--text-color);
}

.sync-item {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 100px;
  padding: 15px 20px;
  border-bottom: 1px solid var(--border-color);
  align-items: center;
}

.sync-item:last-child {
  border-bottom: none;
}

.sync-item:hover {
  background-color: var(--light-gray);
}

.sync-platform {
  display: flex;
  align-items: center;
  gap: 10px;
}

.sync-platform img {
  width: 24px;
  height: 24px;
  border-radius: 4px;
}

.sync-platform-name {
  font-weight: 500;
  color: var(--text-color);
}

.sync-type,
.sync-date,
.sync-status {
  font-size: 14px;
  color: #666;
}

.sync-status {
  display: flex;
  align-items: center;
  gap: 5px;
}

.sync-status-indicator {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.sync-status-indicator.success {
  background-color: var(--success-color);
}

.sync-status-indicator.warning {
  background-color: var(--warning-color);
}

.sync-status-indicator.error {
  background-color: var(--danger-color);
}

.sync-status-indicator.pending {
  background-color: #999;
}

.sync-actions {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  gap: 5px;
}

.sync-actions button {
  width: 30px;
  height: 30px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: 1px solid var(--border-color);
  cursor: pointer;
  transition: all 0.2s ease;
}

.sync-actions button:hover {
  background-color: var(--light-gray);
}

.sync-actions button i {
  font-size: 16px;
  color: var(--text-color);
}
```

## Interações JavaScript

### Filtros de Sincronizações

```javascript
// Código para gerenciar os filtros de sincronizações
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
    const filterType = this.textContent.trim().toLowerCase();
    applyFilter(filterType);
  });
});

function applyFilter(filterType) {
  // Função para aplicar o filtro selecionado
  console.log("Aplicando filtro:", filterType);

  switch (filterType) {
    case "hoje":
      // Filtrar sincronizações de hoje
      fetchSyncsByDate("today");
      break;
    case "pendentes":
      // Filtrar sincronizações pendentes
      fetchSyncsByStatus("pending");
      break;
    case "finalizadas":
      // Filtrar sincronizações finalizadas
      fetchSyncsByStatus("completed");
      break;
  }
}

function fetchSyncsByDate(dateFilter) {
  // Função para buscar sincronizações por data
  console.log("Buscando sincronizações por data:", dateFilter);

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/syncs?date=${dateFilter}`)
    .then((response) => response.json())
    .then((data) => {
      updateSyncsList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar sincronizações por data:", error);
    });
}

function fetchSyncsByStatus(statusFilter) {
  // Função para buscar sincronizações por status
  console.log("Buscando sincronizações por status:", statusFilter);

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/syncs?status=${statusFilter}`)
    .then((response) => response.json())
    .then((data) => {
      updateSyncsList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar sincronizações por status:", error);
    });
}

function updateSyncsList(syncs) {
  // Função para atualizar a lista de sincronizações na interface
  const contentContainer = document.querySelector(".content-container");

  if (syncs.length === 0) {
    // Exibir estado vazio
    contentContainer.innerHTML = `
      <div class="empty-state">
        <div class="empty-state-icon">
          <img src="/assets/images/empty-state-sync.svg" alt="Nenhum registro encontrado" />
        </div>
        <div class="empty-state-message">
          <h3>Nenhum registro encontrado</h3>
          <p>Tente alterar os filtros e pesquisar novamente</p>
        </div>
      </div>
    `;
  } else {
    // Construir e exibir a lista de sincronizações
    let html = `
      <div class="sync-list">
        <div class="sync-list-header">
          <span>Plataforma</span>
          <span>Tipo</span>
          <span>Data/Hora</span>
          <span>Status</span>
          <span>Ações</span>
        </div>
    `;

    syncs.forEach((sync) => {
      html += `
        <div class="sync-item">
          <div class="sync-platform">
            <img src="${sync.platform_icon}" alt="${sync.platform_name}" />
            <div class="sync-platform-name">${sync.platform_name}</div>
          </div>
          <div class="sync-type">${sync.type}</div>
          <div class="sync-date">${formatDate(sync.date)}</div>
          <div class="sync-status">
            <span class="sync-status-indicator ${getStatusClass(
              sync.status
            )}"></span>
            ${sync.status}
          </div>
          <div class="sync-actions">
            <button type="button" data-id="${
              sync.id
            }" data-action="view" title="Visualizar detalhes">
              <i class="icon-eye"></i>
            </button>
            ${
              sync.status === "pending"
                ? `
              <button type="button" data-id="${sync.id}" data-action="retry" title="Tentar novamente">
                <i class="icon-refresh"></i>
              </button>
            `
                : ""
            }
          </div>
        </div>
      `;
    });

    html += "</div>";
    contentContainer.innerHTML = html;

    // Adicionar event listeners para as ações das sincronizações
    document.querySelectorAll(".sync-actions button").forEach((button) => {
      button.addEventListener("click", handleSyncAction);
    });
  }
}

function formatDate(dateString) {
  // Função para formatar a data
  const date = new Date(dateString);
  return date.toLocaleString("pt-BR", {
    day: "2-digit",
    month: "2-digit",
    year: "numeric",
    hour: "2-digit",
    minute: "2-digit",
  });
}

function getStatusClass(status) {
  // Função para obter a classe CSS com base no status
  switch (status.toLowerCase()) {
    case "completed":
    case "success":
      return "success";
    case "pending":
    case "in_progress":
      return "pending";
    case "warning":
      return "warning";
    case "error":
    case "failed":
      return "error";
    default:
      return "pending";
  }
}

function handleSyncAction(e) {
  const action = e.currentTarget.getAttribute("data-action");
  const syncId = e.currentTarget.getAttribute("data-id");

  switch (action) {
    case "view":
      viewSyncDetails(syncId);
      break;
    case "retry":
      retrySync(syncId);
      break;
  }
}
```

### Visualização de Detalhes e Retry

```javascript
function viewSyncDetails(id) {
  // Função para visualizar detalhes da sincronização
  console.log("Visualizando detalhes da sincronização:", id);

  // Exemplo de chamada AJAX para obter os detalhes
  fetch(`/api/syncs/${id}`)
    .then((response) => response.json())
    .then((data) => {
      showSyncDetailsModal(data);
    })
    .catch((error) => {
      console.error("Erro ao obter detalhes da sincronização:", error);
      showErrorMessage(
        "Erro ao obter detalhes da sincronização. Tente novamente mais tarde."
      );
    });
}

function showSyncDetailsModal(sync) {
  // Função para exibir modal com detalhes da sincronização
  const modal = document.createElement("div");
  modal.className = "modal";

  let logsHtml = "";
  if (sync.logs && sync.logs.length > 0) {
    logsHtml = `
      <div class="sync-logs">
        <h4>Logs</h4>
        <div class="logs-container">
          ${sync.logs
            .map(
              (log) => `
            <div class="log-item ${log.type}">
              <span class="log-time">${formatDate(log.timestamp)}</span>
              <span class="log-message">${log.message}</span>
            </div>
          `
            )
            .join("")}
        </div>
      </div>
    `;
  }

  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Detalhes da Sincronização</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <div class="sync-details">
          <div class="detail-item">
            <span class="detail-label">Plataforma:</span>
            <span class="detail-value">${sync.platform_name}</span>
          </div>
          <div class="detail-item">
            <span class="detail-label">Tipo:</span>
            <span class="detail-value">${sync.type}</span>
          </div>
          <div class="detail-item">
            <span class="detail-label">Data/Hora:</span>
            <span class="detail-value">${formatDate(sync.date)}</span>
          </div>
          <div class="detail-item">
            <span class="detail-label">Status:</span>
            <span class="detail-value">
              <span class="sync-status-indicator ${getStatusClass(
                sync.status
              )}"></span>
              ${sync.status}
            </span>
          </div>
          <div class="detail-item">
            <span class="detail-label">Descrição:</span>
            <span class="detail-value">${
              sync.description || "Não disponível"
            }</span>
          </div>
        </div>
        ${logsHtml}
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="close-details">Fechar</button>
        ${
          sync.status === "pending" || sync.status === "failed"
            ? `
          <button class="btn btn-primary" id="retry-sync" data-id="${sync.id}">Tentar Novamente</button>
        `
            : ""
        }
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#close-details").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  const retryButton = modal.querySelector("#retry-sync");
  if (retryButton) {
    retryButton.addEventListener("click", () => {
      const syncId = retryButton.getAttribute("data-id");
      retrySync(syncId);
      document.body.removeChild(modal);
    });
  }
}

function retrySync(id) {
  // Função para tentar novamente a sincronização
  console.log("Tentando novamente a sincronização:", id);

  // Exemplo de chamada AJAX para retry
  fetch(`/api/syncs/${id}/retry`, {
    method: "POST",
  })
    .then((response) => response.json())
    .then((data) => {
      if (data.success) {
        showSuccessMessage("Sincronização iniciada com sucesso!");
        // Atualizar lista de sincronizações
        applyFilter("pendentes");
      } else {
        showErrorMessage(data.message || "Erro ao iniciar sincronização.");
      }
    })
    .catch((error) => {
      console.error("Erro ao tentar novamente a sincronização:", error);
      showErrorMessage(
        "Erro ao tentar novamente a sincronização. Tente novamente mais tarde."
      );
    });
}
```

### Mensagens de Feedback

```javascript
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
2. Usuário seleciona o subitem "Resumo de Sincronizações"
3. O sistema exibe a tela de gerenciamento de sincronizações
4. Por padrão, o filtro "Hoje" está ativo, mostrando as sincronizações do dia atual
5. Se não houver sincronizações para o filtro selecionado, o sistema exibe o estado vazio
6. Usuário pode alternar entre os filtros "Hoje", "Pendentes" e "Finalizadas"

### Fluxo de Visualização de Detalhes

1. Usuário visualiza a lista de sincronizações
2. Usuário clica no botão de visualizar detalhes de uma sincronização específica
3. Sistema exibe modal com informações detalhadas da sincronização
4. Modal inclui logs e histórico da sincronização, quando disponíveis
5. Usuário pode fechar o modal ou, se a sincronização estiver pendente ou com erro, tentar novamente

### Fluxo de Retry de Sincronização

1. Usuário visualiza uma sincronização com status pendente ou com erro
2. Usuário clica no botão de retry na lista ou no modal de detalhes
3. Sistema envia solicitação para reiniciar a sincronização
4. Sistema exibe mensagem de sucesso ou erro
5. Lista de sincronizações é atualizada para refletir o novo status

## Componentes Reutilizáveis

### Botões

```html
<button class="btn btn-primary">Botão Primário</button>
<button class="btn btn-secondary">Botão Secundário</button>
<button class="btn btn-outline">Botão Outline</button>
<button class="btn btn-danger">Botão Perigo</button>
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
  border: 1px solid #ffd700;
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
  max-width: 600px;
  max-height: 80vh;
  overflow-y: auto;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.modal-header {
  padding: 15px 20px;
  border-bottom: 1px solid var(--border-color);
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: sticky;
  top: 0;
  background-color: #fff;
  z-index: 1;
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
  position: sticky;
  bottom: 0;
  background-color: #fff;
  z-index: 1;
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

  .filters-bar {
    flex-wrap: wrap;
    gap: 10px;
  }

  .sync-list-header {
    grid-template-columns: 1fr 1fr 1fr 100px;
  }

  .sync-list-header span:nth-child(4) {
    display: none;
  }

  .sync-item {
    grid-template-columns: 1fr 1fr 1fr 100px;
  }

  .sync-status {
    display: none;
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

  .sync-list-header {
    grid-template-columns: 1fr 1fr 100px;
  }

  .sync-list-header span:nth-child(3) {
    display: none;
  }

  .sync-item {
    grid-template-columns: 1fr 1fr 100px;
  }

  .sync-date {
    display: none;
  }
}
```

## Observações Adicionais

- O subitem "Resumo de Sincronizações" do módulo Ferramentas apresenta uma interface intuitiva para monitoramento e gerenciamento das sincronizações entre o sistema e plataformas externas.
- A tela inicial exibe um estado vazio quando não há sincronizações para o filtro selecionado, com uma mensagem clara para o usuário.
- A interface oferece três filtros principais: "Hoje", "Pendentes" e "Finalizadas", permitindo ao usuário visualizar as sincronizações de acordo com sua necessidade.
- Para cada sincronização, o usuário pode visualizar detalhes completos, incluindo logs e histórico.
- No caso de sincronizações pendentes ou com erro, o usuário pode tentar novamente a operação diretamente da interface.
- A funcionalidade de resumo de sincronizações é essencial para empresas que integram o ERP com plataformas externas, como e-commerces e marketplaces, permitindo monitorar e resolver problemas de integração.
- A interface mantém o mesmo padrão visual do restante do sistema, garantindo consistência na experiência do usuário.
- O sistema utiliza indicadores visuais de status (cores diferentes) para facilitar a identificação rápida do estado de cada sincronização.
- A visualização detalhada de logs permite diagnóstico e resolução de problemas de sincronização.
- A funcionalidade de retry permite que o usuário resolva problemas de sincronização sem precisar recorrer a processos manuais ou suporte técnico.
