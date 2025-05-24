# Análise do Módulo Integrações - Visão Geral

## Visão Geral

O módulo de Integrações do ERP Revo oferece funcionalidades para conectar o sistema a diversas plataformas externas, como marketplaces, plataformas de e-commerce e outros sistemas complementares. Esta seção permite aos usuários instalar, configurar e gerenciar integrações, facilitando a operação omnichannel e a sincronização de dados entre diferentes plataformas.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <span class="current">integrações</span>
  </div>
  <h1>Adicionar integração</h1>
</div>
```

### Barra de Pesquisa

```html
<div class="search-container">
  <input
    type="text"
    class="search-input"
    placeholder="Pesquise por integrações ou canais de venda"
  />
  <button type="button" class="search-button">
    <i class="icon-search"></i>
  </button>
</div>
```

### Filtros de Categorias

```html
<div class="filters-container">
  <button type="button" class="filter-button active">
    todas as integrações
  </button>
  <button type="button" class="filter-button">marketplaces e hubs</button>
  <button type="button" class="filter-button">plataformas de e-commerce</button>
  <button type="button" class="filter-button">outras integrações</button>
</div>
```

### Descrição da Categoria

```html
<div class="category-description">
  <h2>Marketplaces e Hubs</h2>
  <p>
    Marketplaces funcionam como um shopping online, onde as empresas podem
    anunciar seus produtos em lojas conhecidas e abrir novos canais de venda com
    maior visibilidade, enquanto hubs são conectores que ligam o Sistema ERP com
    marketplaces ainda não integrados de forma nativa.
  </p>
</div>
```

### Lista de Integrações

```html
<div class="integrations-grid">
  <div class="integration-card">
    <div class="integration-logo">
      <img src="/assets/images/logos/Revo-store.svg" alt="Revo Store" />
    </div>
    <div class="integration-info">
      <h3>Revo Store</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/48" class="install-button">instalar</a>
    </div>
  </div>

  <div class="integration-card">
    <div class="integration-logo">
      <img src="/assets/images/logos/mercado-livre.svg" alt="Mercado Livre" />
    </div>
    <div class="integration-info">
      <h3>Mercado Livre</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/12" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Mais cards de integração -->
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
      <li class="active">
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
      <li>
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

### Estilos da Barra de Pesquisa

```css
.search-container {
  display: flex;
  align-items: center;
  width: 100%;
  max-width: 500px;
  margin-bottom: 20px;
  position: relative;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  overflow: hidden;
}

.search-input {
  width: 100%;
  padding: 12px 16px;
  border: none;
  font-size: 14px;
  outline: none;
}

.search-button {
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 40px;
  background: var(--primary-color);
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.search-button i {
  color: #fff;
  font-size: 16px;
}
```

### Estilos dos Filtros de Categorias

```css
.filters-container {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 30px;
  flex-wrap: wrap;
}

.filter-button {
  padding: 8px 16px;
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.filter-button:hover {
  background-color: var(--light-gray);
}

.filter-button.active {
  background-color: var(--primary-color);
  color: #fff;
  border-color: var(--primary-color);
}
```

### Estilos da Descrição da Categoria

```css
.category-description {
  margin-bottom: 30px;
}

.category-description h2 {
  font-size: 20px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.category-description p {
  font-size: 14px;
  color: #666;
  line-height: 1.5;
  margin: 0;
}
```

### Estilos da Lista de Integrações

```css
.integrations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.integration-card {
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  transition: all 0.2s ease;
}

.integration-card:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
  transform: translateY(-2px);
}

.integration-logo {
  margin-bottom: 15px;
  height: 60px;
  display: flex;
  align-items: center;
}

.integration-logo img {
  max-height: 100%;
  max-width: 100%;
}

.integration-info {
  flex: 1;
}

.integration-info h3 {
  font-size: 16px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 5px 0;
}

.integration-info p {
  font-size: 14px;
  color: #666;
  margin: 0;
}

.integration-action {
  margin-top: 15px;
}

.install-button {
  display: inline-block;
  padding: 8px 16px;
  background-color: var(--primary-color);
  color: #fff;
  border-radius: 4px;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
  transition: all 0.2s ease;
}

.install-button:hover {
  background-color: #0066a2;
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

### Filtros de Categorias

```javascript
// Código para gerenciar os filtros de categorias
document.querySelectorAll(".filter-button").forEach((filter) => {
  filter.addEventListener("click", function () {
    // Remover classe active de todos os filtros
    document.querySelectorAll(".filter-button").forEach((item) => {
      item.classList.remove("active");
    });

    // Adicionar classe active ao filtro clicado
    this.classList.add("active");

    // Obter o tipo de filtro
    const filterType = this.textContent.trim().toLowerCase();

    // Aplicar o filtro
    filterIntegrations(filterType);
  });
});

function filterIntegrations(filterType) {
  // Função para filtrar as integrações com base no tipo selecionado
  console.log("Filtrando integrações por:", filterType);

  // Ocultar todas as categorias
  document.querySelectorAll(".category-description").forEach((category) => {
    category.style.display = "none";
  });

  // Ocultar todas as integrações
  document.querySelectorAll(".integration-card").forEach((card) => {
    card.style.display = "none";
  });

  // Exibir a categoria e integrações correspondentes ao filtro
  switch (filterType) {
    case "todas as integrações":
      // Exibir todas as categorias e integrações
      document.querySelectorAll(".category-description").forEach((category) => {
        category.style.display = "block";
      });
      document.querySelectorAll(".integration-card").forEach((card) => {
        card.style.display = "flex";
      });
      break;
    case "marketplaces e hubs":
      // Exibir apenas a categoria de marketplaces e suas integrações
      document.querySelector(
        ".category-description:nth-of-type(1)"
      ).style.display = "block";
      document
        .querySelectorAll('.integration-card[data-type="marketplace"]')
        .forEach((card) => {
          card.style.display = "flex";
        });
      break;
    case "plataformas de e-commerce":
      // Exibir apenas a categoria de e-commerce e suas integrações
      document.querySelector(
        ".category-description:nth-of-type(2)"
      ).style.display = "block";
      document
        .querySelectorAll('.integration-card[data-type="ecommerce"]')
        .forEach((card) => {
          card.style.display = "flex";
        });
      break;
    case "outras integrações":
      // Exibir apenas a categoria de outras integrações e suas integrações
      document.querySelector(
        ".category-description:nth-of-type(3)"
      ).style.display = "block";
      document
        .querySelectorAll('.integration-card[data-type="other"]')
        .forEach((card) => {
          card.style.display = "flex";
        });
      break;
  }
}
```

### Pesquisa de Integrações

```javascript
// Código para gerenciar a pesquisa de integrações
document.querySelector(".search-input").addEventListener("keyup", function (e) {
  if (e.key === "Enter") {
    searchIntegrations(this.value);
  }
});

document.querySelector(".search-button").addEventListener("click", function () {
  const searchTerm = document.querySelector(".search-input").value;
  searchIntegrations(searchTerm);
});

function searchIntegrations(term) {
  // Função para pesquisar integrações com base no termo informado
  console.log("Pesquisando integrações com o termo:", term);

  if (!term.trim()) {
    // Se o termo estiver vazio, exibir todas as integrações
    document.querySelectorAll(".integration-card").forEach((card) => {
      card.style.display = "flex";
    });
    return;
  }

  // Converter o termo para minúsculas para comparação case-insensitive
  const searchTerm = term.trim().toLowerCase();

  // Filtrar as integrações com base no termo
  document.querySelectorAll(".integration-card").forEach((card) => {
    const integrationName = card.querySelector("h3").textContent.toLowerCase();
    const integrationType = card.querySelector("p").textContent.toLowerCase();

    if (
      integrationName.includes(searchTerm) ||
      integrationType.includes(searchTerm)
    ) {
      card.style.display = "flex";
    } else {
      card.style.display = "none";
    }
  });

  // Verificar se há resultados
  const visibleCards = document.querySelectorAll(
    '.integration-card[style="display: flex;"]'
  );
  if (visibleCards.length === 0) {
    // Exibir mensagem de nenhum resultado encontrado
    showNoResultsMessage();
  } else {
    // Ocultar mensagem de nenhum resultado encontrado, se estiver visível
    hideNoResultsMessage();
  }
}

function showNoResultsMessage() {
  // Verificar se a mensagem já existe
  let noResultsMessage = document.querySelector(".no-results-message");

  if (!noResultsMessage) {
    // Criar a mensagem
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

    // Adicionar a mensagem ao DOM
    document.querySelector(".integrations-grid").after(noResultsMessage);
  } else {
    // Exibir a mensagem existente
    noResultsMessage.style.display = "block";
  }
}

function hideNoResultsMessage() {
  const noResultsMessage = document.querySelector(".no-results-message");
  if (noResultsMessage) {
    noResultsMessage.style.display = "none";
  }
}
```

### Instalação de Integrações

```javascript
// Código para gerenciar a instalação de integrações
document.querySelectorAll(".install-button").forEach((button) => {
  button.addEventListener("click", function (e) {
    e.preventDefault();

    // Obter o ID da integração a partir do href
    const href = this.getAttribute("href");
    const integrationId = href.split("/").pop();

    // Iniciar o processo de instalação
    installIntegration(integrationId);
  });
});

function installIntegration(id) {
  // Função para iniciar o processo de instalação da integração
  console.log("Iniciando instalação da integração:", id);

  // Redirecionar para a página de instalação
  window.location.href = `/integracoes/instalar/${id}`;
}
```

## Fluxos de Navegação

### Fluxo Principal

1. Usuário acessa o módulo Integrações através do menu lateral
2. O sistema exibe a tela principal com todas as integrações disponíveis
3. Usuário pode filtrar as integrações por categoria (marketplaces, e-commerce, outras)
4. Usuário pode pesquisar integrações específicas
5. Usuário seleciona uma integração para instalar

### Fluxo de Instalação de Integração

1. Usuário clica no botão "instalar" de uma integração
2. Sistema redireciona para a tela de configuração da integração
3. Usuário preenche as informações necessárias (nome da integração no ERP)
4. Usuário clica no botão "conectar com [nome da plataforma]"
5. Sistema redireciona para a página de autenticação da plataforma
6. Usuário realiza a autenticação na plataforma
7. Sistema finaliza a configuração e redireciona para a lista de integrações configuradas

### Fluxo de Pesquisa de Integrações

1. Usuário digita um termo de pesquisa no campo de busca
2. Usuário pressiona Enter ou clica no botão de pesquisa
3. Sistema filtra as integrações com base no termo informado
4. Sistema exibe os resultados da pesquisa ou uma mensagem de nenhum resultado encontrado

## Componentes Reutilizáveis

### Botões

```html
<button class="btn btn-primary">Botão Primário</button>
<button class="btn btn-secondary">Botão Secundário</button>
<button class="btn btn-outline">Botão Outline</button>
<button class="btn btn-danger">Botão Perigo</button>
` (Content truncated due to size limit. Use line ranges to read in chunks)
```
