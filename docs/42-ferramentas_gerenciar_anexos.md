# Análise do Módulo Ferramentas - Gerenciar Anexos

## Visão Geral

O subitem "Gerenciar Anexos" do módulo Ferramentas do ERP Revo oferece funcionalidades para gerenciamento centralizado de todos os arquivos anexados em diferentes partes do sistema. Esta seção permite aos usuários visualizar, pesquisar, baixar e gerenciar anexos de forma unificada, facilitando o acesso a documentos importantes.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <a href="/ferramentas_geral">Ferramentas</a>
    <span class="separator">/</span>
    <span class="current">gerenciar anexos</span>
  </div>
  <h1>Gerenciar anexos</h1>
</div>
```

### Barra de Pesquisa e Filtros

```html
<div class="search-filter-bar">
  <div class="search-container">
    <input
      type="text"
      class="search-input"
      placeholder="Pesquise por nome ou extensão"
    />
    <button type="button" class="search-button">
      <i class="icon-search"></i>
    </button>
  </div>

  <div class="filters-container">
    <a href="#" class="filter-link"> <i class="icon-filter"></i> por origem </a>
  </div>
</div>
```

### Conteúdo Principal (Estado Vazio)

```html
<div class="content-container">
  <div class="empty-state">
    <div class="empty-state-icon">
      <img
        src="/assets/images/empty-state-anexos.svg"
        alt="Nenhum anexo encontrado"
      />
    </div>
    <div class="empty-state-message">
      <h3>Você não possui nenhum item cadastrado.</h3>
      <p>Ainda não existem anexos no seu sistema.</p>
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

### Estilos da Barra de Pesquisa e Filtros

```css
.search-filter-bar {
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

### Estilos da Lista de Anexos (Quando Houver Dados)

```css
.anexos-list {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.anexos-list-header {
  display: grid;
  grid-template-columns: 40px 3fr 1fr 1fr 1fr 100px;
  padding: 15px 20px;
  background-color: var(--light-gray);
  border-bottom: 1px solid var(--border-color);
}

.anexos-list-header span {
  font-weight: 600;
  font-size: 14px;
  color: var(--text-color);
}

.anexo-item {
  display: grid;
  grid-template-columns: 40px 3fr 1fr 1fr 1fr 100px;
  padding: 15px 20px;
  border-bottom: 1px solid var(--border-color);
  align-items: center;
}

.anexo-item:last-child {
  border-bottom: none;
}

.anexo-item:hover {
  background-color: var(--light-gray);
}

.anexo-icon {
  display: flex;
  align-items: center;
  justify-content: center;
}

.anexo-icon i {
  font-size: 20px;
}

.anexo-name {
  font-weight: 500;
  color: var(--text-color);
}

.anexo-extension,
.anexo-size,
.anexo-origin {
  font-size: 14px;
  color: #666;
}

.anexo-actions {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  gap: 5px;
}

.anexo-actions button {
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

.anexo-actions button:hover {
  background-color: var(--light-gray);
}

.anexo-actions button i {
  font-size: 16px;
  color: var(--text-color);
}
```

## Interações JavaScript

### Pesquisa de Anexos

```javascript
// Código para gerenciar a pesquisa de anexos
document.querySelector(".search-input").addEventListener("keyup", function (e) {
  if (e.key === "Enter") {
    searchAnexos(this.value);
  }
});

document.querySelector(".search-button").addEventListener("click", function () {
  const searchTerm = document.querySelector(".search-input").value;
  searchAnexos(searchTerm);
});

function searchAnexos(term) {
  // Função para pesquisar anexos com base no termo informado
  console.log("Pesquisando anexos com o termo:", term);

  // Aqui seria implementada a lógica para filtrar os anexos
  // e atualizar a lista exibida na interface

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/anexos/search?term=${encodeURIComponent(term)}`)
    .then((response) => response.json())
    .then((data) => {
      updateAnexosList(data);
    })
    .catch((error) => {
      console.error("Erro ao pesquisar anexos:", error);
    });
}

function updateAnexosList(anexos) {
  // Função para atualizar a lista de anexos na interface
  const contentContainer = document.querySelector(".content-container");

  if (anexos.length === 0) {
    // Exibir estado vazio
    contentContainer.innerHTML = `
      <div class="empty-state">
        <div class="empty-state-icon">
          <img src="/assets/images/empty-state-anexos.svg" alt="Nenhum anexo encontrado" />
        </div>
        <div class="empty-state-message">
          <h3>Nenhum anexo encontrado.</h3>
          <p>Tente ajustar os termos da pesquisa ou os filtros.</p>
        </div>
      </div>
    `;
  } else {
    // Construir e exibir a lista de anexos
    let html = `
      <div class="anexos-list">
        <div class="anexos-list-header">
          <span></span>
          <span>Nome</span>
          <span>Extensão</span>
          <span>Tamanho</span>
          <span>Origem</span>
          <span>Ações</span>
        </div>
    `;

    anexos.forEach((anexo) => {
      html += `
        <div class="anexo-item">
          <div class="anexo-icon">
            <i class="icon-${getIconByExtension(anexo.extension)}"></i>
          </div>
          <div class="anexo-name">${anexo.name}</div>
          <div class="anexo-extension">${anexo.extension}</div>
          <div class="anexo-size">${formatFileSize(anexo.size)}</div>
          <div class="anexo-origin">${anexo.origin}</div>
          <div class="anexo-actions">
            <button type="button" data-id="${
              anexo.id
            }" data-action="view" title="Visualizar">
              <i class="icon-eye"></i>
            </button>
            <button type="button" data-id="${
              anexo.id
            }" data-action="download" title="Download">
              <i class="icon-download"></i>
            </button>
            <button type="button" data-id="${
              anexo.id
            }" data-action="delete" title="Excluir">
              <i class="icon-trash"></i>
            </button>
          </div>
        </div>
      `;
    });

    html += "</div>";
    contentContainer.innerHTML = html;

    // Adicionar event listeners para as ações dos anexos
    document.querySelectorAll(".anexo-actions button").forEach((button) => {
      button.addEventListener("click", handleAnexoAction);
    });
  }
}

function getIconByExtension(extension) {
  // Função para obter o ícone com base na extensão do arquivo
  const iconMap = {
    pdf: "pdf",
    doc: "word",
    docx: "word",
    xls: "excel",
    xlsx: "excel",
    ppt: "powerpoint",
    pptx: "powerpoint",
    jpg: "image",
    jpeg: "image",
    png: "image",
    gif: "image",
    zip: "archive",
    rar: "archive",
    txt: "text",
  };

  return iconMap[extension.toLowerCase()] || "file";
}

function formatFileSize(bytes) {
  // Função para formatar o tamanho do arquivo
  if (bytes === 0) return "0 Bytes";

  const k = 1024;
  const sizes = ["Bytes", "KB", "MB", "GB", "TB"];
  const i = Math.floor(Math.log(bytes) / Math.log(k));

  return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + " " + sizes[i];
}

function handleAnexoAction(e) {
  const action = e.currentTarget.getAttribute("data-action");
  const anexoId = e.currentTarget.getAttribute("data-id");

  switch (action) {
    case "view":
      viewAnexo(anexoId);
      break;
    case "download":
      downloadAnexo(anexoId);
      break;
    case "delete":
      confirmDeleteAnexo(anexoId);
      break;
  }
}

function viewAnexo(id) {
  // Função para visualizar o anexo
  console.log("Visualizando anexo:", id);

  // Exemplo de chamada AJAX para obter a URL do anexo
  fetch(`/api/anexos/${id}/view`)
    .then((response) => response.json())
    .then((data) => {
      if (data.url) {
        // Abrir o anexo em uma nova aba
        window.open(data.url, "_blank");
      }
    })
    .catch((error) => {
      console.error("Erro ao visualizar anexo:", error);
      showErrorMessage("Erro ao visualizar anexo. Tente novamente mais tarde.");
    });
}

function downloadAnexo(id) {
  // Função para fazer download do anexo
  console.log("Fazendo download do anexo:", id);

  // Exemplo de chamada AJAX para obter a URL de download
  fetch(`/api/anexos/${id}/download`)
    .then((response) => response.json())
    .then((data) => {
      if (data.url) {
        // Criar um link temporário para download
        const link = document.createElement("a");
        link.href = data.url;
        link.download = data.filename;
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
      }
    })
    .catch((error) => {
      console.error("Erro ao fazer download do anexo:", error);
      showErrorMessage(
        "Erro ao fazer download do anexo. Tente novamente mais tarde."
      );
    });
}

function confirmDeleteAnexo(id) {
  // Função para confirmar a exclusão do anexo
  console.log("Confirmando exclusão do anexo:", id);

  // Criar modal de confirmação
  const modal = document.createElement("div");
  modal.className = "modal";
  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Confirmar Exclusão</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <p>Tem certeza que deseja excluir este anexo?</p>
        <p>Esta ação não poderá ser desfeita.</p>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="cancel-delete">Cancelar</button>
        <button class="btn btn-danger" id="confirm-delete">Excluir</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#cancel-delete").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#confirm-delete").addEventListener("click", () => {
    deleteAnexo(id);
    document.body.removeChild(modal);
  });
}

function deleteAnexo(id) {
  // Função para excluir o anexo
  console.log("Excluindo anexo:", id);

  // Exemplo de chamada AJAX para excluir o anexo
  fetch(`/api/anexos/${id}`, {
    method: "DELETE",
  })
    .then((response) => response.json())
    .then((data) => {
      if (data.success) {
        showSuccessMessage("Anexo excluído com sucesso!");
        // Atualizar lista de anexos
        fetchAnexos();
      } else {
        showErrorMessage(data.message || "Erro ao excluir anexo.");
      }
    })
    .catch((error) => {
      console.error("Erro ao excluir anexo:", error);
      showErrorMessage("Erro ao excluir anexo. Tente novamente mais tarde.");
    });
}
```

### Filtro por Origem

```javascript
// Código para gerenciar o filtro por origem
document.querySelector(".filter-link").addEventListener("click", function (e) {
  e.preventDefault();

  // Exibir modal de seleção de origem
  showOriginSelector();
});

function showOriginSelector() {
  // Função para exibir o seletor de origem
  const modal = document.createElement("div");
  modal.className = "modal";
  modal.innerHTML = `
    <div class="modal-content">
      <div class="modal-header">
        <h3>Filtrar por Origem</h3>
        <button class="close-button">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label>Origem</label>
          <div class="checkbox-group">
            <label>
              <input type="checkbox" name="origin" value="pedidos" checked> Pedidos
            </label>
            <label>
              <input type="checkbox" name="origin" value="produtos" checked> Produtos
            </label>
            <label>
              <input type="checkbox" name="origin" value="clientes" checked> Clientes
            </label>
            <label>
              <input type="checkbox" name="origin" value="fornecedores" checked> Fornecedores
            </label>
            <label>
              <input type="checkbox" name="origin" value="financeiro" checked> Financeiro
            </label>
            <label>
              <input type="checkbox" name="origin" value="outros" checked> Outros
            </label>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline" id="cancel-origin">Cancelar</button>
        <button class="btn btn-primary" id="apply-origin">Aplicar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adicionar event listeners para os botões do modal
  modal.querySelector(".close-button").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#cancel-origin").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#apply-origin").addEventListener("click", () => {
    const selectedOrigins = Array.from(
      document.querySelectorAll('input[name="origin"]:checked')
    ).map((checkbox) => checkbox.value);

    if (selectedOrigins.length > 0) {
      fetchAnexosByOrigin(selectedOrigins);
    }

    document.body.removeChild(modal);
  });
}

function fetchAnexosByOrigin(origins) {
  // Função para buscar anexos com base nas origens selecionadas
  console.log("Buscando anexos por origem:", origins);

  // Construir query string com as origens
  const queryParams = new URLSearchParams();

  origins.forEach((origin) => {
    queryParams.append("origin", origin);
  });

  // Exemplo de chamada AJAX para buscar os resultados
  fetch(`/api/anexos?${queryParams.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      updateAnexosList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar anexos por origem:", error);
    });
}

function fetchAnexos() {
  // Função para buscar todos os anexos
  fetch("/api/anexos")
    .then((response) => response.json())
    .then((data) => {
      updateAnexosList(data);
    })
    .catch((error) => {
      console.error("Erro ao buscar anexos:", error);
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
2. Usuário seleciona o subitem "Gerenciar Anexos"
3. O sistema exibe a tela de gerenciamento de anexos
4. Se não houver anexos cadastrados, o sistema exibe o estado vazio
5. Usuário pode pesquisar ou filtrar anexos existentes

### Fluxo de Pesquisa de Anexos

1. Usuário digita um termo de pesquisa no campo de busca
2. Usuário pressiona Enter ou clica no botão de pesquisa
3. Sistema filtra os anexos com base no termo informado
4. Sistema exibe os resultados da pesquisa ou um estado vazio caso não encontre resultados

### Fluxo de Filtragem por Origem

1. Usuário clica no filtro "por origem"
2. Sistema exibe modal com opções de origem
3. Usuário seleciona as origens desejadas
4. Usuário confirma a seleção
5. Sistema filtra os anexos com base nas origens selecionadas
6. Sistema exibe os resultados filtrados ou um estado vazio caso não encontre resultados

### Fluxo de Gerenciamento de Anexos

1. Usuário visualiza a lista de anexos
2. Para cada anexo, o usuário pode:
   - Visualizar o anexo
   - Fazer download do anexo
   - Excluir o anexo

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

  .search-filter-bar {
    flex-wrap: wrap;
    gap: 10px;
  }

  .search-container {
    width: 100%;
    order: 1;
  }

  .filters-container {
    width: 100%;
    order: 2;
    justify-content: flex-start;
    margin-top: 10px;
  }

  .anexo-item {
    grid-template-columns: 40px 2fr 1fr 1fr 100px;
  }

  .anexo-origin {
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

  .search-filter-bar {
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

  .anexos-list-header {
    grid-template-columns: 40px 2fr 1fr 100px;
  }

  .anexos-list-header span:nth-child(4),
  .anexos-list-header span:nth-child(5) {
    display: none;
  }

  .anexo-item {
    grid-template-columns: 40px 2fr 1fr 100px;
  }

  .anexo-size,
  .anexo-origin {
    display: none;
  }
}
```

## Observações Adicionais

- O subitem "Gerenciar Anexos" do módulo Ferramentas apresenta uma interface intuitiva para gerenciamento centralizado de todos os arquivos anexados em diferentes partes do sistema.
- A tela inicial exibe um estado vazio quando não há anexos cadastrados, com uma mensagem clara para o usuário.
- A interface oferece funcionalidades de pesquisa e filtragem para facilitar a localização de anexos específicos.
- Os anexos são organizados em uma lista com informações relevantes como nome, extensão, tamanho e origem.
- Para cada anexo, o usuário pode realizar ações como visualizar, fazer download ou excluir.
- A funcionalidade de gerenciamento centralizado de anexos é essencial para empresas que trabalham com muitos documentos, facilitando o acesso e organização dos arquivos.
- A interface mantém o mesmo padrão visual do restante do sistema, garantindo consistência na experiência do usuário.
- O sistema utiliza ícones diferentes para cada tipo de arquivo, facilitando a identificação visual dos anexos.
- A exclusão de anexos requer confirmação do usuário, evitando exclusões acidentais.
- A pesquisa por nome ou extensão permite encontrar rapidamente arquivos específicos, mesmo em grandes volumes de anexos.
