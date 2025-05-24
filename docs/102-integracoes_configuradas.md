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
  cursor: poin
(Content truncated due to size limit. Use line ranges to read in chunks)
```
