# Análise do Módulo Ferramentas - Backup

## Visão Geral

O subitem "Backup" do módulo Ferramentas do ERP Revo oferece funcionalidades para gerenciamento de backups do sistema. Esta seção permite aos usuários agendar, gerenciar e restaurar backups dos dados do sistema, garantindo a segurança e integridade das informações.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <a href="/ferramentas_geral">Ferramentas</a>
    <span class="separator">/</span>
    <span class="current">Backup</span>
  </div>
  <h1>Backup</h1>
</div>
```

### Barra de Ações

```html
<div class="actions-bar">
  <div class="search-container">
    <input type="text" class="search-input" placeholder="Pesquisa..." />
    <button type="button" class="search-button">
      <i class="icon-search"></i>
    </button>
  </div>

  <div class="filters-container">
    <a href="#" class="filter-link active">
      <i class="icon-filter"></i> Em aberto
    </a>
    <a href="#" class="filter-link">
      <i class="icon-calendar"></i> por período
    </a>
    <a href="#" class="filter-link">
      <i class="icon-clear"></i> limpar filtros
    </a>
  </div>

  <div class="actions-container">
    <a href="/incluir_backup" class="btn btn-primary">
      <i class="icon-plus"></i> Incluir Backup
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
        src="/assets/images/empty-state-backup.svg"
        alt="Nenhum backup cadastrado"
      />
    </div>
    <div class="empty-state-message">
      <h3>Você não possui nenhum item cadastrado.</h3>
      <p>Para inserir novos registros você pode clicar em Incluir Backup.</p>
      <a href="/incluir_backup" class="btn btn-primary">
        <i class="icon-plus"></i> Incluir Backup
      </a>
    </div>
  </div>
</div>
```

### Rodapé de Ajuda

```html
<div class="help-footer">
  <p>Ficou com alguma dúvida?</p>
  <a href="/ajuda/backup" class="help-link"> Acesse a ajuda do Revo. </a>
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

.search-container {
  display: flex;
  align-items: center;
  width: 300px;
  position: relative;
}

.search-input {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
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

.actions-container {
  display: flex;
  align-items: center;
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
  margin: 0 0 20px 0;
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

### Pesquisa de Backups

```javascript
// Código para gerenciar a pesquisa de backups
document.querySelector(".search-input").addEventListener("keyup", function (e) {
  if (e.key === "Enter") {
    searchBackups(this.value);
  }
});

document.querySelector(".search-button").addEventListener("click", function () {
  const searchTerm = document.querySelector(".search-input").value;
  searchBackups(searchTerm);
});

function searchBackups(term) {
  // Função para pesquisar backups com base no termo informado
  console.log("Pesquisando backups com o termo:", term);

  // Aqui seria implementada a lógica para filtrar os backups
  // e atualizar a lista exibida na interface

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/backups/search?term=${encodeURIComponent(term)}`)
    .then((response) => response.json())
    .then((data) => {
      updateBackupsList(data);
    })
    .catch((error) => {
      console.error("Erro ao pesquisar backups:", error);
    });
}

function updateBackupsList(backups) {
  // Função para atualizar a lista de backups na interface
  const contentContainer = document.querySelector(".content-container");

  if (backups.length === 0) {
    // Exibir estado vazio
    contentContainer.innerHTML = `
      <div class="empty-state">
        <div class="empty-state-icon">
          <img src="/assets/images/empty-state-backup.svg" alt="Nenhum backup encontrado" />
        </div>
        <div class="empty-state-message">
          <h3>Nenhum backup encontrado.</h3>
          <p>Tente ajustar os filtros ou criar um novo backup.</p>
          <a href="/incluir_backup" class="btn btn-primary">
            <i class="icon-plus"></i> Incluir Backup
          </a>
        </div>
      </div>
    `;
  } else {
    // Construir e exibir a lista de backups
    let backupsHtml = '<div class="backups-list">';

    backups.forEach((backup) => {
      backupsHtml += `
        <div class="backup-item">
          <div class="backup-info">
            <h3>${backup.name}</h3>
            <p>Data: ${backup.date}</p>
            <p>Status: ${backup.status}</p>
          </div>
          <div class="backup-actions">
            <button class="btn btn-outline btn-sm" data-id="${backup.id}" data-action="download">
              <i class="icon-download"></i> Download
            </button>
            <button class="btn btn-outline btn-sm" data-id="${backup.id}" data-action="restore">
              <i class="icon-restore"></i> Restaurar
            </button>
            <button class="btn btn-danger btn-sm" data-id="${backup.id}" data-action="delete">
              <i class="icon-trash"></i> Excluir
            </button>
          </div>
        </div>
      `;
    });

    backupsHtml += "</div>";
    contentContainer.innerHTML = backupsHtml;

    // Adicionar event listeners para as ações dos backups
    document.querySelectorAll(".backup-actions button").forEach((button) => {
      button.addEventListener("click", handleBackupAction);
    });
  }
}

function handleBackupAction(e) {
  const action = e.currentTarget.getAttribute("data-action");
  const backupId = e.currentTarget.getAttribute("data-id");

  switch (action) {
    case "download":
      downloadBackup(backupId);
      break;
    case "restore":
      confirmRestoreBackup(backupId);
      break;
    case "delete":
      confirmDeleteBackup(backupId);
      break;
  }
}
```

### Filtros de Backups

```javascript
// Código para gerenciar os filtros de backups
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
    case "Em aberto":
      // Filtrar backups em aberto
      fetchBackups({ status: "open" });
      break;
    case "por período":
      // Exibir seletor de período
      showPeriodSelector();
      break;
    case "limpar filtros":
      // Limpar todos os filtros
      clearFilters();
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
      fetchBackups({ startDate, endDate });
    }

    document.body.removeChild(modal);
  });
}

function clearFilters() {
  // Função para limpar todos os filtros
  document.querySelector(".search-input").value = "";

  // Resetar filtros ativos
  document.querySelectorAll(".filter-link").forEach((item) => {
    item.classList.remove("active");
  });

  // Buscar todos os backups sem filtros
  fetchBackups({});
}

function fetchBackups(filters) {
  // Função para buscar backups com base nos filtros
  console.log("Buscando backups com filtros:", filters);

  // Construir query string com os filtros
  const queryParams = new URLSearchParams();

  Object.entries(filters).forEach(([key, value]) => {
    queryParams.append(key, value);
  });

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/backups?${queryParams.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      updateBackupsList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar backups:", error);
    });
}
```

## Fluxos de Navegação

### Fluxo Principal

1. Usuário acessa o módulo Ferramentas através do menu lateral
2. Usuário seleciona o subitem "Backup"
3. O sistema exibe a tela de gerenciamento de backups
4. Se não houver backups cadastrados, o sistema exibe o estado vazio
5. Usuário pode incluir um novo backup, pesquisar ou filtrar backups existentes

### Fluxo de Inclusão de Backup

1. Usuário clica no botão "Incluir Backup"
2. Sistema exibe formulário para configuração do backup
3. Usuário preenche as informações necessárias (nome, periodicidade, dados a serem incluídos)
4. Usuário confirma a inclusão do backup
5. Sistema agenda o backup conforme configuração e retorna à lista de backups

### Fluxo de Gerenciamento de Backups

1. Usuário visualiza a lista de backups cadastrados
2. Usuário pode filtrar backups por status ou período
3. Usuário pode pesquisar backups pelo nome
4. Para cada backup, o usuário pode:
   - Fazer download do arquivo de backup
   - Restaurar o sistema a partir do backup
   - Excluir o backup

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
    <button class="btn btn-primary">Ação Principal</button>
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
  margin: 0 0 20px 0;
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

  .actions-bar {
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

  .actions-bar {
    padding: 10px 15px;
  }

  .filter-link {
    padding: 6px 10px;
    font-size: 12px;
  }

  .empty-state {
    padding: 20px;
  }
}
```

## Observações Adicionais

- O subitem "Backup" do módulo Ferramentas apresenta uma interface intuitiva para gerenciamento de backups do sistema.
- A tela inicial exibe um estado vazio quando não há backups cadastrados, com orientações claras para o usuário.
- A interface oferece funcionalidades de pesquisa e filtragem para facilitar a localização de backups específicos.
- O sistema utiliza modais para interações que requerem confirmação ou entrada de dados adicionais.
- A funcionalidade de backup é essencial para garantir a segurança dos dados do sistema, permitindo restauração em caso de problemas.
- A interface mantém o mesmo padrão visual do restante do sistema, garantindo consistência na experiência do usuário.
