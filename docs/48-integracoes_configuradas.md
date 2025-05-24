# Análise do Módulo Integrações - Integrações Configuradas

## Visão Geral

A seção "Integrações Configuradas" do módulo de Integrações do ERP Revo apresenta todas as integrações que já foram instaladas e configuradas pelo usuário. Esta área permite gerenciar as integrações existentes, visualizar seu status, editar configurações, sincronizar dados e, se necessário, remover integrações. É uma interface central para o monitoramento e administração de todas as conexões estabelecidas entre o ERP e sistemas externos.

## Estrutura HTML

### Cabeçalho da Seção

```html
<div class="section-header">
  <h1>Integrações Configuradas</h1>
  <div class="section-actions">
    <a href="/integracoes/adicionar" class="btn btn-primary">
      <i class="icon-plus"></i> Adicionar integração
    </a>
  </div>
</div>
```

### Filtros e Pesquisa

```html
<div class="filters-container">
  <div class="search-box">
    <input
      type="text"
      class="search-input"
      placeholder="Pesquisar integração..."
    />
    <button type="button" class="search-button">
      <i class="icon-search"></i>
    </button>
  </div>

  <div class="filter-options">
    <div class="filter-group">
      <label>Status:</label>
      <select class="filter-select">
        <option value="all">Todos</option>
        <option value="active">Ativo</option>
        <option value="inactive">Inativo</option>
        <option value="error">Com erro</option>
      </select>
    </div>

    <div class="filter-group">
      <label>Tipo:</label>
      <select class="filter-select">
        <option value="all">Todos</option>
        <option value="marketplace">Marketplaces</option>
        <option value="ecommerce">E-commerce</option>
        <option value="other">Outros</option>
      </select>
    </div>
  </div>
</div>
```

### Lista de Integrações Configuradas

```html
<div class="integrations-list">
  <!-- Integração Mercado Livre -->
  <div class="integration-item" data-type="marketplace" data-status="active">
    <div class="integration-icon">
      <img src="/assets/images/logos/mercado-livre.svg" alt="Mercado Livre" />
    </div>

    <div class="integration-details">
      <div class="integration-name">Mercado Livre - Loja Principal</div>
      <div class="integration-type">Marketplace</div>
      <div class="integration-status status-active">
        <span class="status-indicator"></span>
        Ativo
      </div>
    </div>

    <div class="integration-last-sync">
      <div class="sync-label">Última sincronização:</div>
      <div class="sync-time">Hoje às 14:32</div>
    </div>

    <div class="integration-actions">
      <button type="button" class="btn btn-icon" title="Sincronizar agora">
        <i class="icon-sync"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Configurações">
        <i class="icon-settings"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Mais opções">
        <i class="icon-more"></i>
      </button>
    </div>
  </div>

  <!-- Integração WooCommerce -->
  <div class="integration-item" data-type="ecommerce" data-status="error">
    <div class="integration-icon">
      <img src="/assets/images/logos/woocommerce.svg" alt="WooCommerce" />
    </div>

    <div class="integration-details">
      <div class="integration-name">WooCommerce - Site Institucional</div>
      <div class="integration-type">Plataforma de e-commerce</div>
      <div class="integration-status status-error">
        <span class="status-indicator"></span>
        Erro de autenticação
      </div>
    </div>

    <div class="integration-last-sync">
      <div class="sync-label">Última sincronização:</div>
      <div class="sync-time">Ontem às 18:45</div>
    </div>

    <div class="integration-actions">
      <button type="button" class="btn btn-icon" title="Sincronizar agora">
        <i class="icon-sync"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Configurações">
        <i class="icon-settings"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Mais opções">
        <i class="icon-more"></i>
      </button>
    </div>
  </div>

  <!-- Integração Mercos -->
  <div class="integration-item" data-type="other" data-status="inactive">
    <div class="integration-icon">
      <img src="/assets/images/logos/mercos.svg" alt="Mercos" />
    </div>

    <div class="integration-details">
      <div class="integration-name">Mercos</div>
      <div class="integration-type">Outra integração</div>
      <div class="integration-status status-inactive">
        <span class="status-indicator"></span>
        Inativo
      </div>
    </div>

    <div class="integration-last-sync">
      <div class="sync-label">Última sincronização:</div>
      <div class="sync-time">12/05/2025 às 09:20</div>
    </div>

    <div class="integration-actions">
      <button type="button" class="btn btn-icon" title="Ativar">
        <i class="icon-power"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Configurações">
        <i class="icon-settings"></i>
      </button>
      <button type="button" class="btn btn-icon" title="Mais opções">
        <i class="icon-more"></i>
      </button>
    </div>
  </div>
</div>
```

### Menu de Opções

```html
<div class="dropdown-menu" id="integration-options-menu">
  <ul class="menu-list">
    <li class="menu-item">
      <a href="#" class="menu-link"> <i class="icon-edit"></i> Editar </a>
    </li>
    <li class="menu-item">
      <a href="#" class="menu-link">
        <i class="icon-history"></i> Histórico de sincronização
      </a>
    </li>
    <li class="menu-item">
      <a href="#" class="menu-link">
        <i class="icon-pause"></i> Pausar sincronização
      </a>
    </li>
    <li class="menu-item menu-item-danger">
      <a href="#" class="menu-link">
        <i class="icon-trash"></i> Remover integração
      </a>
    </li>
  </ul>
</div>
```

### Modal de Configurações

```html
<div class="modal" id="integration-settings-modal">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">Configurações da Integração</h3>
        <button type="button" class="close-button" data-dismiss="modal">
          <i class="icon-close"></i>
        </button>
      </div>

      <div class="modal-body">
        <div class="form-group">
          <label for="integration-name-edit">Nome da integração</label>
          <input
            type="text"
            id="integration-name-edit"
            class="form-control"
            value="Mercado Livre - Loja Principal"
          />
        </div>

        <div class="form-group">
          <label for="sync-interval">Intervalo de sincronização</label>
          <select id="sync-interval" class="form-control">
            <option value="15">A cada 15 minutos</option>
            <option value="30">A cada 30 minutos</option>
            <option value="60" selected>A cada 1 hora</option>
            <option value="120">A cada 2 horas</option>
            <option value="360">A cada 6 horas</option>
            <option value="720">A cada 12 horas</option>
            <option value="1440">A cada 24 horas</option>
          </select>
        </div>

        <div class="form-group">
          <label>Sincronizar</label>
          <div class="checkbox-group">
            <div class="checkbox-item">
              <input type="checkbox" id="sync-products" checked />
              <label for="sync-products">Produtos</label>
            </div>
            <div class="checkbox-item">
              <input type="checkbox" id="sync-stock" checked />
              <label for="sync-stock">Estoque</label>
            </div>
            <div class="checkbox-item">
              <input type="checkbox" id="sync-prices" checked />
              <label for="sync-prices">Preços</label>
            </div>
            <div class="checkbox-item">
              <input type="checkbox" id="sync-orders" checked />
              <label for="sync-orders">Pedidos</label>
            </div>
          </div>
        </div>

        <div class="form-group">
          <label>Notificações</label>
          <div class="checkbox-group">
            <div class="checkbox-item">
              <input type="checkbox" id="notify-errors" checked />
              <label for="notify-errors"
                >Notificar erros de sincronização</label
              >
            </div>
            <div class="checkbox-item">
              <input type="checkbox" id="notify-new-orders" checked />
              <label for="notify-new-orders">Notificar novos pedidos</label>
            </div>
          </div>
        </div>
      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-outline" data-dismiss="modal">
          Cancelar
        </button>
        <button type="button" class="btn btn-primary">Salvar alterações</button>
      </div>
    </div>
  </div>
</div>
```

### Modal de Confirmação de Remoção

```html
<div class="modal" id="integration-remove-modal">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">Remover Integração</h3>
        <button type="button" class="close-button" data-dismiss="modal">
          <i class="icon-close"></i>
        </button>
      </div>

      <div class="modal-body">
        <p>
          Tem certeza que deseja remover a integração
          <strong>Mercado Livre - Loja Principal</strong>?
        </p>
        <p class="text-danger">Esta ação não poderá ser desfeita.</p>
      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-outline" data-dismiss="modal">
          Cancelar
        </button>
        <button type="button" class="btn btn-danger">Remover</button>
      </div>
    </div>
  </div>
</div>
```

## Estilos CSS

### Estilos do Cabeçalho da Seção

```css
.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.section-header h1 {
  font-size: 24px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0;
}

.section-actions {
  display: flex;
  gap: 10px;
}
```

### Estilos dos Filtros e Pesquisa

```css
.filters-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
  gap: 15px;
}

.search-box {
  position: relative;
  width: 300px;
}

.search-input {
  width: 100%;
  padding: 10px 40px 10px 12px;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 14px;
}

.search-button {
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
  color: #666;
}

.filter-options {
  display: flex;
  gap: 15px;
}

.filter-group {
  display: flex;
  align-items: center;
  gap: 8px;
}

.filter-group label {
  font-size: 14px;
  color: var(--text-color);
  white-space: nowrap;
}

.filter-select {
  padding: 8px 12px;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 14px;
  background-color: #fff;
}
```

### Estilos da Lista de Integrações

```css
.integrations-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.integration-item {
  display: flex;
  align-items: center;
  padding: 20px;
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  transition: all 0.2s ease;
}

.integration-item:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
}

.integration-icon {
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 20px;
}

.integration-icon img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.integration-details {
  flex: 1;
  min-width: 0;
}

.integration-name {
  font-size: 16px;
  font-weight: 600;
  color: var(--text-color);
  margin-bottom: 5px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.integration-type {
  font-size: 14px;
  color: #666;
  margin-bottom: 5px;
}

.integration-status {
  display: flex;
  align-items: center;
  font-size: 14px;
  font-weight: 500;
}

.status-indicator {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 6px;
}

.status-active {
  color: var(--success-color);
}

.status-active .status-indicator {
  background-color: var(--success-color);
}

.status-inactive {
  color: #999;
}

.status-inactive .status-indicator {
  background-color: #999;
}

.status-error {
  color: var(--danger-color);
}

.status-error .status-indicator {
  background-color: var(--danger-color);
}

.integration-last-sync {
  margin: 0 30px;
  min-width: 180px;
}

.sync-label {
  font-size: 12px;
  color: #666;
  margin-bottom: 3px;
}

.sync-time {
  font-size: 14px;
  color: var(--text-color);
}

.integration-actions {
  display: flex;
  gap: 5px;
}

.btn-icon {
  width: 36px;
  height: 36px;
  border-radius: 4px;
  background-color: transparent;
  border: 1px solid var(--border-color);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.2s ease;
  color: #666;
}

.btn-icon:hover {
  background-color: var(--light-gray);
  color: var(--text-color);
}
```

### Estilos do Menu de Opções

```css
.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 1000;
  display: none;
  min-width: 200px;
  padding: 8px 0;
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.dropdown-menu.show {
  display: block;
}

.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu-item {
  margin: 0;
}

.menu-link {
  display: flex;
  align-items: center;
  padding: 8px 16px;
  color: var(--text-color);
  text-decoration: none;
  font-size: 14px;
  transition: all 0.2s ease;
}

.menu-link i {
  margin-right: 10px;
  font-size: 16px;
}

.menu-link:hover {
  background-color: var(--light-gray);
}

.menu-item-danger .menu-link {
  color: var(--danger-color);
}

.menu-item-danger .menu-link:hover {
  background-color: #ffebee;
}
```

### Estilos do Modal

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
  z-index: 1050;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}

.modal.show {
  opacity: 1;
  visibility: visible;
}

.modal-dialog {
  width: 100%;
  max-width: 500px;
  margin: 30px auto;
  transform: translateY(-20px);
  transition: transform 0.3s ease;
}

.modal.show .modal-dialog {
  transform: translateY(0);
}

.modal-dialog.modal-sm {
  max-width: 400px;
}

.modal-content {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.modal-header {
  padding: 20px;
  border-bottom: 1px solid var(--border-color);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.modal-title {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0;
}

.close-button {
  background: transparent;
  border: none;
  font-size: 20px;
  cursor: pointer;
  color: #666;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30px;
  height: 30px;
  border-radius: 4px;
  transition: all 0.2s ease;
}

.close-button:hover {
  background-color: var(--light-gray);
  color: var(--text-color);
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

.checkbox-group {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 10px;
}

.checkbox-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.checkbox-item label {
  font-size: 14px;
  color: var(--text-color);
  cursor: pointer;
}

.text-danger {
  color: var(--danger-color);
}
```

## Interações JavaScript

### Filtrar e Pesquisar Integrações

```javascript
// Código para gerenciar a filtragem e pesquisa de integrações
document.addEventListener("DOMContentLoaded", function () {
  const searchInput = document.querySelector(".search-input");
  const statusFilter = document.querySelector('.filter-select[name="status"]');
  const typeFilter = document.querySelector('.filter-select[name="type"]');
  const integrationItems = document.querySelectorAll(".integration-item");

  // Função para filtrar as integrações
  function filterIntegrations() {
    const searchTerm = searchInput.value.trim().toLowerCase();
    const statusValue = statusFilter.value;
    const typeValue = typeFilter.value;

    integrationItems.forEach((item) => {
      const name = item
        .querySelector(".integration-name")
        .textContent.toLowerCase();
      const type = item.getAttribute("data-type");
      const status = item.getAttribute("data-status");

      // Verificar se o item atende aos critérios de filtro
      const matchesSearch = name.includes(searchTerm);
      const matchesStatus = statusValue === "all" || status === statusValue;
      const matchesType = typeValue === "all" || type === typeValue;

      // Exibir ou ocultar o item com base nos filtros
      if (matchesSearch && matchesStatus && matchesType) {
        item.style.display = "flex";
      } else {
        item.style.display = "none";
      }
    });

    // Verificar se há resultados
    const visibleItems = document.querySelectorAll(
      '.integration-item[style="display: flex;"]'
    );
    if (visibleItems.length === 0) {
      showNoResultsMessage();
    } else {
      hideNoResultsMessage();
    }
  }

  // Adicionar listeners para os eventos de filtro
  searchInput.addEventListener("input", filterIntegrations);
  statusFilter.addEventListener("change", filterIntegrations);
  typeFilter.addEventListener("change", filterIntegrations);

  // Funções para exibir/ocultar mensagem de nenhum resultado
  function showNoResultsMessage() {
    let noResultsMessage = document.querySelector(".no-results-message");

    if (!noResultsMessage) {
      noResultsMessage = document.createElement("div");
      noResultsMessage.className = "no-results-message";
      noResultsMessage.innerHTML = `
        <div class="empty-state">
          <div class="empty-state-icon">
            <i class="icon-search"></i>
          </div>
          <div class="empty-state-message">
            <h3>Nenhuma integração encontrada</h3>
            <p>Tente ajustar os termos da pesquisa ou os filtros.</p>
          </div>
        </div>
      `;

      document.querySelector(".integrations-list").after(noResultsMessage);
    } else {
      noResultsMessage.style.display = "block";
    }
  }

  function hideNoResultsMessage() {
    const noResultsMessage = document.querySelector(".no-results-message");
    if (noResultsMessage) {
      noResultsMessage.style.display = "none";
    }
  }
});
```

### Gerenciar Menu de Opções

```javascript
// Código para gerenciar o menu de opções
document.addEventListener("DOMContentLoaded", function () {
  const moreButtons = document.querySelectorAll(
    '.integration-actions .btn-icon[title="Mais opções"]'
  );
  const optionsMenu = document.getElementById("integration-options-menu");

  // Função para exibir o menu de opções
  function showOptionsMenu(button, integrationName) {
    // Posicionar o menu abaixo do botão
    const buttonRect = button.getBoundingClientRect();
    optionsMenu.style.top = `${buttonRect.bottom + window.scrollY + 5}px`;
    optionsMenu.style.right = `${
      window.innerWidth - buttonRect.right - window.scrollX
    }px`;

    // Atualizar o texto de remoção com o nome da integração
    const removeLink = optionsMenu.querySelector(
      ".menu-item-danger .menu-link"
    );
    removeLink.setAttribute("data-integration-name", integrationName);

    // Exibir o menu
    optionsMenu.classList.add("show");

    // Adicionar listener para fechar o menu ao clicar fora dele
    document.addEventListener("click", closeMenuOnClickOutside);
  }

  // Função para fechar o menu ao clicar fora dele
  function closeMenuOnClickOutside(event) {
    if (
      !optionsMenu.contains(event.target) &&
      !event.target.matches('.btn-icon[title="Mais opções"]')
    ) {
      optionsMenu.classList.remove("show");
      document.removeEventListener("click", closeMenuOnClickOutside);
    }
  }

  // Adicionar listeners para os botões de mais opções
  moreButtons.forEach((button) => {
    button.addEventListener("click", function (e) {
      e.stopPropagation();

      // Obter o nome da integração
      const integrationItem = this.closest(".integration-item");
      const integrationName =
        integrationItem.querySelector(".integration-name").textContent;

      // Exibir o menu de opções
      showOptionsMenu(this, integrationName);
    });
  });

  // Adicionar listeners para as opções do menu
  if (optionsMenu) {
    // Opção de editar
    optionsMenu
      .querySelector(".menu-link:has(.icon-edit)")
      .addEventListener("click", function (e) {
        e.preventDefault();

        // Abrir modal de configurações
        openSettingsModal();

        // Fechar o menu
        optionsMenu.classList.remove("show");
      });

    // Opção de remover
    optionsMenu
      .querySelector(".menu-link:has(.icon-trash)")
      .addEventListener("click", function (e) {
        e.preventDefault();

        // Obter o nome da integração
        const integrationName = this.getAttribute("data-integration-name");

        // Abrir modal de confirmação de remoção
        openRemoveModal(integrationName);

        // Fechar o menu
        optionsMenu.classList.remove("show");
      });
  }
});
```

### Gerenciar Modais

```javascript
// Código para gerenciar os modais
document.addEventListener("DOMContentLoaded", function () {
  const settingsModal = document.getElementById("integration-settings-modal");
  const removeModal = document.getElementById("integration-remove-modal");

  // Função para abrir o modal de configurações
  function openSettingsModal() {
    if (settingsModal) {
      settingsModal.classList.add("show");
      document.body.style.overflow = "hidden";
    }
  }

  // Função para abrir o modal de confirmação de remoção
  function openRemoveModal(integrationName) {
    if (removeModal) {
      // Atualizar o texto com o nome da integração
      const confirmText = removeModal.querySelector(".modal-body strong");
      if (confirmText) {
        confirmText.textContent = integrationName;
      }

      removeModal.classList.add("show");
      document.body.style.overflow = "hidden";
    }
  }

  // Função para fechar os modais
  function closeModal(modal) {
    if (modal) {
      modal.classList.remove("show");
      document.body.style.overflow = "";
    }
  }

  // Adicionar listeners para os botões de fechar dos modais
  document
    .querySelectorAll('.close-button, .btn[data-dismiss="modal"]')
    .forEach((button) => {
      button.addEventListener("click", function () {
        const modal = this.closest(".modal");
        closeModal(modal);
      });
    });

  // Adicionar listeners para fechar os modais ao clicar fora do conteúdo
  [settingsModal, removeModal].forEach((modal) => {
    if (modal) {
      modal.addEventListener("click", function (e) {
        if (e.target === this) {
          closeModal(this);
        }
      });
    }
  });

  // Adicionar listener para o botão de salvar configurações
  if (settingsModal) {
    const saveButton = settingsModal.querySelector(".btn-primary");
    if (saveButton) {
      saveButton.addEventListener("click", function () {
        // Obter os valores dos campos
        const name = document.getElementById("integration-name-edit").value;
        const syncInterval = document.getElementById("sync-interval").value;
        const syncProducts = document.getElementById("sync-products").checked;
        const syncStock = document.getElementById("sync-stock").checked;
        const syncPrices = document.getElementById("sync-prices").checked;
        const syncOrders = document.getElementById("sync-orders").checked;
        const notifyErrors = document.getElementById("notify-errors").checked;
        const notifyNewOrders =
          document.getElementById("notify-new-orders").checked;

        // Salvar as configurações
        saveIntegrationSettings({
          name,
          syncInterval,
          sync: {
            products: syncProducts,
            stock: syncStock,
            prices: syncPrices,
            orders: syncOrders,
          },
          notifications: {
            errors: notifyErrors,
            newOrders: notifyNewOrders,
          },
        });

        // Fechar o modal
        closeModal(settingsModal);
      });
    }
  }

  // Adicionar listener para o botão de remover integração
  if (removeModal) {
    const removeButton = removeModal.querySelector(".btn-danger");
    if (removeButton) {
      removeButton.addEventListener("click", function () {
        // Remover a integração
        removeIntegration();

        // Fechar o modal
        closeModal(removeModal);
      });
    }
  }

  // Função para salvar as configurações da integração
  function saveIntegrationSettings(settings) {
    console.log("Salvando configurações da integração:", settings);

    // Simular requisição para salvar as configurações
    setTimeout(() => {
      // Exibir mensagem de sucesso
      showNotification("Configurações salvas com sucesso!", "success");

      // Atualizar a interface com o novo nome da integração
      const integrationItem = document.querySelector(
        ".integration-item.active"
      );
      if (integrationItem) {
        integrationItem.querySelector(".integration-name").textContent =
          settings.name;
      }
    }, 500);
  }

  // Função para remover a integração
  function removeIntegration() {
    console.log("Removendo integração");

    // Simular requisição para remover a integração
    setTimeout(() => {
      // Exibir mensagem de sucesso
      showNotification("Integração removida com sucesso!", "success");

      // Remover o item da lista
      const integrationItem = document.querySelector(
        ".integration-item.active"
      );
      if (integrationItem) {
        integrationItem.remove();
      }
    }, 500);
  }

  // Função para exibir notificações
  function showNotification(message, type) {
    const notification = document.createElement("div");
    notification.className = `notification notification-${type}`;
    notification.innerHTML = `
      <div class="notification-icon">
        <i class="icon-${type === "success" ? "check" : "info"}"></i>
      </div>
      <div class="notification-content">
        ${message}
      </div>
      <button type="button" class="notification-close">
        <i class="icon-close"></i>
      </button>
    `;

    document.body.appendChild(notification);

    // Exibir a notificação com animação
    setTimeout(() => {
      notification.classList.add("show");
    }, 10);

    // Adicionar listener para fechar a notificação
    notification
      .querySelector(".notification-close")
      .addEventListener("click", function () {
        notification.classList.remove("show");
        setTimeout(() => {
          notification.remove();
        }, 300);
      });

    // Remover a notificação automaticamente após 5 segundos
    setTimeout(() => {
      notification.classList.remove("show");
      setTimeout(() => {
        notification.remove();
      }, 300);
    }, 5000);
  }

  // Expor as funções globalmente para uso em outros scripts
  window.openSettingsModal = openSettingsModal;
  window.openRemoveModal = openRemoveModal;
});
```

### Sincronização de Integrações

```javascript
// Código para gerenciar a sincronização de integrações
document.addEventListener("DOMContentLoaded", function () {
  const syncButtons = document.querySelectorAll(
    '.integration-actions .btn-icon[title="Sincronizar agora"]'
  );

  // Adicionar listeners para os botões de sincronização
  syncButtons.forEach((button) => {
    button.addEventListener("click", function () {
      // Obter o item da integração
      const integrationItem = this.closest(".integration-item");
      const integrationName =
        integrationItem.querySelector(".integration-name").textContent;

      // Iniciar a sincronização
      syncIntegration(integrationItem, integrationName);
    });
  });

  // Função para sincronizar a integração
  function syncIntegration(item, name) {
    console.log("Sincronizando integração:", name);

    // Adicionar classe de sincronização em andamento
    item.classList.add("syncing");

    // Atualizar o ícone do botão para indicar sincronização em andamento
    const syncButton = item.querySelector(
      '.btn-icon[title="Sincronizar agora"]'
    );
    const originalIcon = syncButton.innerHTML;
    syncButton.innerHTML = '<i class="icon-loading"></i>';
    syncButton.disabled = true;

    // Simular requisição de sincronização
    setTimeout(() => {
      // Remover classe de sincronização em andamento
      item.classList.remove("syncing");

      // Restaurar o ícone original
      syncButton.innerHTML = originalIcon;
      syncButton.disabled = false;

      // Atualizar a hora da última sincronização
      const now = new Date();
      const hours = now.getHours().toString().padStart(2, "0");
      const minutes = now.getMinutes().toString().padStart(2, "0");
      item.querySelector(
        ".sync-time"
      ).textContent = `Hoje às ${hours}:${minutes}`;

      // Exibir mensagem de sucesso
      showNotification(
        `Integração "${name}" sincronizada com sucesso!`,
        "success"
      );
    }, 2000);
  }

  // Função para exibir notificações
  function showNotification(message, type) {
    const notification = document.createElement("div");
    notification.className = `notification notification-${type}`;
    notification.innerHTML = `
      <div class="notification-icon">
        <i class="icon-${type === "success" ? "check" : "info"}"></i>
      </div>
      <div class="notification-content">
        ${message}
      </div>
      <button type="button" class="notification-close">
        <i class="icon-close"></i>
      </button>
    `;

    document.body.appendChild(notification);

    // Exibir a notificação com animação
    setTimeout(() => {
      notification.classList.add("show");
    }, 10);

    // Adicionar listener para fechar a notificação
    notification
      .querySelector(".notification-close")
      .addEventListener("click", function () {
        notification.classList.remove("show");
        setTimeout(() => {
          notification.remove();
        }, 300);
      });

    // Remover a notificação automaticamente após 5 segundos
    setTimeout(() => {
      notification.classList.remove("show");
      setTimeout(() => {
        notification.remove();
      }, 300);
    }, 5000);
  }
});
```

## Fluxos de Navegação

### Fluxo de Visualização de Integrações Configuradas

1. Usuário acessa o módulo Integrações através do menu lateral
2. Sistema exibe a lista de integrações configuradas
3. Usuário pode filtrar as integrações por status ou tipo
4. Usuário pode pesquisar integrações pelo nome

### Fluxo de Sincronização de Integração

1. Usuário localiza a integração desejada na lista
2. Usuário clica no botão de sincronização
3. Sistema inicia o processo de sincronização
4. Sistema exibe indicador de progresso
5. Sistema finaliza a sincronização e atualiza a hora da última sincronização
6. Sistema exibe mensagem de sucesso

### Fluxo de Edição de Configurações

1. Usuário localiza a integração desejada na lista
2. Usuário clica no botão de configurações ou seleciona "Editar" no menu de opções
3. Sistema exibe modal com as configurações atuais
4. Usuário edita as configurações desejadas
5. Usuário clica em "Salvar alterações"
6. Sistema salva as configurações e atualiza a interface
7. Sistema exibe mensagem de sucesso

### Fluxo de Remoção de Integração

1. Usuário localiza a integração desejada na lista
2. Usuário clica no botão de mais opções
3. Usuário seleciona "Remover integração" no menu
4. Sistema exibe modal de confirmação
5. Usuário confirma a remoção
6. Sistema remove a integração e atualiza a interface
7. Sistema exibe mensagem de sucesso

## Componentes Reutilizáveis

### Item de Integração

```html
<div class="integration-item" data-type="tipo" data-status="status">
  <div class="integration-icon">
    <img src="/assets/images/logos/logo.svg" alt="Nome da Integração" />
  </div>

  <div class="integration-details">
    <div class="integration-name">Nome da Integração</div>
    <div class="integration-type">Tipo da Integração</div>
    <div class="integration-status status-active">
      <span class="status-indicator"></span>
      Status
    </div>
  </div>

  <div class="integration-last-sync">
    <div class="sync-label">Última sincronização:</div>
    <div class="sync-time">Data e hora</div>
  </div>

  <div class="integration-actions">
    <button type="button" class="btn btn-icon" title="Ação 1">
      <i class="icon-action1"></i>
    </button>
    <button type="button" class="btn btn-icon" title="Ação 2">
      <i class="icon-action2"></i>
    </button>
  </div>
</div>
```

### Modal

```html
<div class="modal" id="modal-id">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">Título do Modal</h3>
        <button type="button" class="close-button" data-dismiss="modal">
          <i class="icon-close"></i>
        </button>
      </div>

      <div class="modal-body">Conteúdo do modal</div>

      <div class="modal-footer">
        <button type="button" class="btn btn-outline" data-dismiss="modal">
          Cancelar
        </button>
        <button type="button" class="btn btn-primary">Confirmar</button>
      </div>
    </div>
  </div>
</div>
```

### Notificação

```html
<div class="notification notification-success">
  <div class="notification-icon">
    <i class="icon-check"></i>
  </div>
  <div class="notification-content">Mensagem de notificação</div>
  <button type="button" class="notification-close">
    <i class="icon-close"></i>
  </button>
</div>
```

```css
.notification {
  position: fixed;
  top: 20px;
  right: 20px;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  padding: 15px;
  display: flex;
  align-items: center;
  min-width: 300px;
  max-width: 400px;
  z-index: 1060;
  transform: translateX(110%);
  transition: transform 0.3s ease;
}

.notification.show {
  transform: translateX(0);
}

.notification-success {
  border-left: 4px solid var(--success-color);
}

.notification-error {
  border-left: 4px solid var(--danger-color);
}

.notification-info {
  border-left: 4px solid var(--primary-color);
}

.notification-icon {
  margin-right: 15px;
  font-size: 20px;
}

.notification-success .notification-icon {
  color: var(--success-color);
}

.notification-error .notification-icon {
  color: var(--danger-color);
}

.notification-info .notification-icon {
  color: var(--primary-color);
}

.notification-content {
  flex: 1;
  font-size: 14px;
  color: var(--text-color);
}

.notification-close {
  background: transparent;
  border: none;
  font-size: 16px;
  cursor: pointer;
  color: #666;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  margin-left: 10px;
}
```

## Responsividade

```css
/* Estilos para tablets */
@media (max-width: 992px) {
  .filters-container {
    flex-direction: column;
    align-items: flex-start;
  }

  .search-box {
    width: 100%;
    margin-bottom: 15px;
  }

  .filter-options {
    width: 100%;
    justify-content: space-between;
  }

  .integration-item {
    flex-wrap: wrap;
  }

  .integration-details {
    width: calc(100% - 70px);
  }

  .integration-last-sync {
    margin: 15px 0 0 70px;
    width: calc(100% - 70px - 120px);
  }

  .integration-actions {
    margin-top: 15px;
    margin-left: auto;
  }
}

/* Estilos para dispositivos móveis */
@media (max-width: 768px) {
  .section-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }

  .section-actions {
    width: 100%;
  }

  .section-actions .btn {
    width: 100%;
    justify-content: center;
  }

  .filter-options {
    flex-direction: column;
    gap: 10px;
  }

  .filter-group {
    width: 100%;
  }

  .filter-select {
    width: 100%;
  }

  .integration-item {
    padding: 15px;
  }

  .integration-icon {
    margin-right: 15px;
  }

  .integration-details {
    width: calc(100% - 65px);
  }

  .integration-last-sync {
    margin: 15px 0 0 0;
    width: 100%;
  }

  .integration-actions {
    margin-top: 15px;
    width: 100%;
    justify-content: flex-end;
  }

  .modal-dialog {
    margin: 20px;
    max-width: calc(100% - 40px);
  }
}
```

## Observações Adicionais

- A seção "Integrações Configuradas" do módulo de Integrações apresenta uma interface intuitiva para gerenciar as integrações já instaladas e configuradas pelo usuário.
- Cada integração é representada por um item na lista, contendo logo, nome, tipo, status, hora da última sincronização e botões de ação.
- Os status possíveis para uma integração são: Ativo, Inativo e Com erro, cada um com uma cor específica para facilitar a identificação visual.
- A interface permite filtrar as integrações por status e tipo, além de pesquisar pelo nome, facilitando a localização de integrações específicas.
- O botão de sincronização permite atualizar manualmente os dados entre o ERP e a plataforma externa, exibindo um indicador de progresso durante o processo.
- O botão de configurações permite editar as configurações da integração, como nome, intervalo de sincronização, tipos de dados a sincronizar e notificações.
- O menu de opções oferece acesso a funcionalidades adicionais, como edição, histórico de sincronização, pausa de sincronização e remoção da integração.
- A remoção de uma integração requer confirmação do usuário, evitando exclusões acidentais.
- O sistema exibe notificações para informar o usuário sobre o resultado das ações realizadas, como sincronização, edição de configurações e remoção de integrações.
- O design é responsivo, adaptando-se a diferentes tamanhos de tela e dispositivos.
- Os componentes visuais seguem um padrão consistente, utilizando cores, tipografia e espaçamentos padronizados.
- A documentação detalhada dos componentes HTML, CSS e JavaScript facilita a recriação da interface no Figma, mantendo a consistência visual e funcional.
