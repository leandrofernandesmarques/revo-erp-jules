# Análise do Módulo Integrações - Marketplaces e Hubs

## Visão Geral

A seção "Marketplaces e Hubs" do módulo de Integrações do ERP Revo oferece funcionalidades para conectar o sistema a diversos marketplaces e hubs de vendas. Esta categoria permite aos usuários instalar e configurar integrações com plataformas como Revo Store, Mercado Livre, Shopee, entre outras, facilitando a gestão de vendas em múltiplos canais.

## Estrutura HTML

### Cabeçalho da Categoria

```html
<div class="category-header">
  <h2>Marketplaces e Hubs</h2>
  <p class="category-description">
    Marketplaces funcionam como um shopping online, onde as empresas podem
    anunciar seus produtos em lojas conhecidas e abrir novos canais de venda com
    maior visibilidade, enquanto hubs são conectores que ligam o Sistema ERP com
    marketplaces ainda não integrados de forma nativa.
  </p>
</div>
```

### Grid de Integrações de Marketplaces

```html
<div class="integrations-grid">
  <!-- Revo Store -->
  <div class="integration-card" data-type="marketplace">
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

  <!-- Mercado Livre -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img src="/assets/images/logos/mercado-livre.svg" alt="Mercado Livre" />
    </div>
    <div class="integration-info">
      <h3>Mercado Livre</h3>
      <p>Marketplace</p>
      <div class="integration-badges">
        <span class="badge badge-ml"></span>
        <span class="badge badge-ml-full"></span>
      </div>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/12" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Shopee -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img src="/assets/images/logos/shopee.svg" alt="Shopee" />
    </div>
    <div class="integration-info">
      <h3>Shopee</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/56" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Americanas Marketplace -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/americanas.svg"
        alt="Americanas Marketplace"
      />
    </div>
    <div class="integration-info">
      <h3>Americanas Marketplace</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/34" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Magalu Marketplace -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img src="/assets/images/logos/magalu.svg" alt="Magalu Marketplace" />
    </div>
    <div class="integration-info">
      <h3>Magalu Marketplace</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/22" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Casas Bahia Marketplace -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/casas-bahia.svg"
        alt="Casas Bahia Marketplace"
      />
    </div>
    <div class="integration-info">
      <h3>Casas Bahia Marketplace</h3>
      <p>Marketplace</p>
      <div class="integration-badges">
        <span class="badge badge-cb"></span>
        <span class="badge badge-pf"></span>
        <span class="badge badge-ef"></span>
      </div>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/28" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Carrefour -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img src="/assets/images/logos/carrefour.svg" alt="Carrefour" />
    </div>
    <div class="integration-info">
      <h3>Carrefour</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/42" class="install-button">instalar</a>
    </div>
  </div>

  <!-- MadeiraMadeira -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/madeira-madeira.svg"
        alt="MadeiraMadeira"
      />
    </div>
    <div class="integration-info">
      <h3>MadeiraMadeira</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/38" class="install-button">instalar</a>
    </div>
  </div>

  <!-- AliExpress -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img src="/assets/images/logos/aliexpress.svg" alt="AliExpress" />
    </div>
    <div class="integration-info">
      <h3>AliExpress</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/62" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Mercado Livre Fulfillment -->
  <div class="integration-card" data-type="marketplace">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/mercado-livre-fulfillment.svg"
        alt="Mercado Livre Fulfillment"
      />
    </div>
    <div class="integration-info">
      <h3>Mercado Livre Fulfillment</h3>
      <p>Marketplace</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/14" class="install-button">instalar</a>
    </div>
  </div>
</div>
```

### Tela de Configuração de Marketplace

```html
<div class="integration-setup">
  <div class="integration-setup-header">
    <div class="integration-logo">
      <img src="/assets/images/logos/Revo-store.svg" alt="Revo Store" />
    </div>
    <h2>Integração com Revo Store</h2>
  </div>

  <div class="integration-setup-content">
    <div class="setup-section">
      <h3>Conectar Integração</h3>
      <p>
        Realizar a conexão com o marketplace é o primeiro passo para otimizar o
        seu negócio de vendas online através do Sistema ERP.
      </p>

      <div class="form-group">
        <label for="integration-name">Nome da integração no ERP</label>
        <input
          type="text"
          id="integration-name"
          class="form-control"
          placeholder="Revo Store"
        />
      </div>

      <div class="auth-section">
        <h4>Autenticação</h4>
        <p>Você será direcionado para autenticação padrão do marketplace</p>
        <button type="button" class="btn btn-primary">
          conectar com Revo Store
        </button>
      </div>
    </div>

    <div class="help-section">
      <p>Ficou com alguma dúvida?</p>
      <a href="/ajuda/integracoes/Revo-store" class="help-link"
        >Acesse a ajuda sobre a integração</a
      >
    </div>
  </div>
</div>
```

## Estilos CSS

### Estilos do Cabeçalho da Categoria

```css
.category-header {
  margin-bottom: 30px;
}

.category-header h2 {
  font-size: 20px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.category-description {
  font-size: 14px;
  color: #666;
  line-height: 1.5;
  margin: 0;
  max-width: 800px;
}
```

### Estilos do Grid de Integrações

```css
.integrations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  margin-bottom: 40px;
}

.integration-card {
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  transition: all 0.2s ease;
  height: 100%;
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
  object-fit: contain;
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
  margin: 0 0 10px 0;
}

.integration-badges {
  display: flex;
  gap: 5px;
  margin-top: 10px;
}

.badge {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
}

.badge-ml {
  background-image: url("/assets/images/badges/mercado-livre.png");
}

.badge-ml-full {
  background-image: url("/assets/images/badges/mercado-livre-full.png");
}

.badge-cb {
  background-image: url("/assets/images/badges/casas-bahia.png");
}

.badge-pf {
  background-image: url("/assets/images/badges/ponto-frio.png");
}

.badge-ef {
  background-image: url("/assets/images/badges/extra.png");
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
  text-align: center;
  width: 100%;
}

.install-button:hover {
  background-color: #0066a2;
}
```

### Estilos da Tela de Configuração

```css
.integration-setup {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.integration-setup-header {
  padding: 20px 30px;
  border-bottom: 1px solid var(--border-color);
  display: flex;
  align-items: center;
  gap: 15px;
}

.integration-setup-header .integration-logo {
  width: 40px;
  height: 40px;
  margin-bottom: 0;
}

.integration-setup-header h2 {
  font-size: 20px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0;
}

.integration-setup-content {
  padding: 30px;
}

.setup-section {
  margin-bottom: 30px;
}

.setup-section h3 {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.setup-section p {
  font-size: 14px;
  color: #666;
  margin: 0 0 20px 0;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  font-size: 14px;
  font-weight: 500;
  color: var(--text-color);
  margin-bottom: 5px;
}

.form-control {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 14px;
  transition: border-color 0.2s ease;
}

.form-control:focus {
  outline: none;
  border-color: var(--primary-color);
}

.auth-section {
  background-color: var(--light-gray);
  padding: 20px;
  border-radius: 8px;
  margin-top: 20px;
}

.auth-section h4 {
  font-size: 16px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.auth-section p {
  margin-bottom: 15px;
}

.help-section {
  border-top: 1px solid var(--border-color);
  padding-top: 20px;
  margin-top: 30px;
}

.help-section p {
  font-size: 14px;
  color: #666;
  margin: 0 0 10px 0;
}

.help-link {
  color: var(--primary-color);
  text-decoration: none;
  font-size: 14px;
  display: inline-flex;
  align-items: center;
}

.help-link:hover {
  text-decoration: underline;
}

.help-link::before {
  content: "";
  display: inline-block;
  width: 16px;
  height: 16px;
  background-image: url("/assets/images/icons/help.svg");
  background-size: contain;
  background-repeat: no-repeat;
  margin-right: 5px;
}
```

## Interações JavaScript

### Instalação de Marketplace

```javascript
// Código para gerenciar a instalação de marketplaces
document
  .querySelectorAll(
    '.integration-card[data-type="marketplace"] .install-button'
  )
  .forEach((button) => {
    button.addEventListener("click", function (e) {
      e.preventDefault();

      // Obter o ID da integração a partir do href
      const href = this.getAttribute("href");
      const integrationId = href.split("/").pop();

      // Obter o nome da integração
      const integrationName =
        this.closest(".integration-card").querySelector("h3").textContent;

      // Iniciar o processo de instalação
      installMarketplace(integrationId, integrationName);
    });
  });

function installMarketplace(id, name) {
  // Função para iniciar o processo de instalação do marketplace
  console.log("Iniciando instalação do marketplace:", name, "ID:", id);

  // Redirecionar para a página de instalação
  window.location.href = `/integracoes/ecommerce/auth/new/${id}`;
}
```

### Configuração de Marketplace

```javascript
// Código para gerenciar a configuração de marketplaces
document.addEventListener("DOMContentLoaded", function () {
  const integrationNameInput = document.getElementById("integration-name");
  const connectButton = document.querySelector(".auth-section .btn-primary");

  if (integrationNameInput && connectButton) {
    // Verificar se o nome da integração foi preenchido antes de habilitar o botão
    integrationNameInput.addEventListener("input", function () {
      if (this.value.trim()) {
        connectButton.removeAttribute("disabled");
      } else {
        connectButton.setAttribute("disabled", "disabled");
      }
    });

    // Iniciar o processo de autenticação
    connectButton.addEventListener("click", function () {
      const integrationName = integrationNameInput.value.trim();

      if (integrationName) {
        // Obter o ID da integração a partir da URL
        const urlParts = window.location.pathname.split("/");
        const integrationId = urlParts[urlParts.length - 1];

        // Iniciar o processo de autenticação
        authenticateMarketplace(integrationId, integrationName);
      }
    });
  }
});

function authenticateMarketplace(id, name) {
  // Função para iniciar o processo de autenticação do marketplace
  console.log("Iniciando autenticação do marketplace:", name, "ID:", id);

  // Salvar o nome da integração no localStorage para uso posterior
  localStorage.setItem("integration_name", name);

  // Construir a URL de autenticação
  const authUrl = `/api/integrations/${id}/auth?name=${encodeURIComponent(
    name
  )}`;

  // Fazer a requisição para obter a URL de autenticação externa
  fetch(authUrl)
    .then((response) => response.json())
    .then((data) => {
      if (data.auth_url) {
        // Redirecionar para a URL de autenticação externa
        window.location.href = data.auth_url;
      } else {
        // Exibir mensagem de erro
        showErrorMessage(
          "Não foi possível obter a URL de autenticação. Tente novamente mais tarde."
        );
      }
    })
    .catch((error) => {
      console.error("Erro ao obter URL de autenticação:", error);
      showErrorMessage(
        "Ocorreu um erro ao iniciar o processo de autenticação. Tente novamente mais tarde."
      );
    });
}

function showErrorMessage(message) {
  // Verificar se já existe uma mensagem de erro
  let errorMessage = document.querySelector(".error-message");

  if (!errorMessage) {
    // Criar a mensagem de erro
    errorMessage = document.createElement("div");
    errorMessage.className = "error-message";

    // Adicionar a mensagem ao DOM
    document.querySelector(".auth-section").appendChild(errorMessage);
  }

  // Atualizar o conteúdo da mensagem
  errorMessage.textContent = message;
  errorMessage.style.display = "block";
}
```

### Callback de Autenticação

```javascript
// Código para gerenciar o callback de autenticação
document.addEventListener('DOMContentLoaded', function() {
  // Verificar se estamos na página de callback
  if (window.location.pathname.includes('/auth/callback')) {
    // Obter os parâmetros da URL
    const urlParams = new URLSearchParams(window.location.search);
    const code = urlParams.get('code');
    const error = urlParams.get('error');

    if (code) {
      // Obter o ID da integração a partir da URL
      const urlParts = window.location.pathname.split('/');
      const integrationId = urlParts[urlParts.length - 2];

      // Obter o nome da integração do localStorage
      const integrationName = loc
(Content truncated due to size limit. Use line ranges to read in chunks)
```
