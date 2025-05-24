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
document.addEventListener("DOMContentLoaded", function () {
  // Verificar se estamos na página de callback
  if (window.location.pathname.includes("/auth/callback")) {
    // Obter os parâmetros da URL
    const urlParams = new URLSearchParams(window.location.search);
    const code = urlParams.get("code");
    const error = urlParams.get("error");

    if (code) {
      // Obter o ID da integração a partir da URL
      const urlParts = window.location.pathname.split("/");
      const integrationId = urlParts[urlParts.length - 2];

      // Obter o nome da integração do localStorage
      const integrationName =
        localStorage.getItem("integration_name") || "Integração";

      // Finalizar o processo de autenticação
      finalizeAuthentication(integrationId, code, integrationName);
    } else if (error) {
      // Exibir mensagem de erro
      showAuthError(error);
    }
  }
});

function finalizeAuthentication(id, code, name) {
  // Função para finalizar o processo de autenticação
  console.log("Finalizando autenticação do marketplace:", name, "ID:", id);

  // Construir a URL para finalizar a autenticação
  const finalizeUrl = `/api/integrations/${id}/finalize`;

  // Fazer a requisição para finalizar a autenticação
  fetch(finalizeUrl, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      code: code,
      name: name,
    }),
  })
    .then((response) => response.json())
    .then((data) => {
      if (data.success) {
        // Limpar o localStorage
        localStorage.removeItem("integration_name");

        // Exibir mensagem de sucesso
        showSuccessMessage();

        // Redirecionar para a lista de integrações configuradas
        setTimeout(() => {
          window.location.href = "/integracoes";
        }, 3000);
      } else {
        // Exibir mensagem de erro
        showAuthError(
          data.message || "Não foi possível finalizar a autenticação."
        );
      }
    })
    .catch((error) => {
      console.error("Erro ao finalizar autenticação:", error);
      showAuthError(
        "Ocorreu um erro ao finalizar o processo de autenticação. Tente novamente mais tarde."
      );
    });
}

function showSuccessMessage() {
  // Criar a mensagem de sucesso
  const successMessage = document.createElement("div");
  successMessage.className = "success-message";
  successMessage.innerHTML = `
    <div class="success-icon">
      <i class="icon-check"></i>
    </div>
    <div class="success-content">
      <h3>Integração configurada com sucesso!</h3>
      <p>Você será redirecionado para a lista de integrações em instantes...</p>
    </div>
  `;

  // Limpar o conteúdo atual
  document.querySelector(".integration-setup-content").innerHTML = "";

  // Adicionar a mensagem ao DOM
  document
    .querySelector(".integration-setup-content")
    .appendChild(successMessage);
}

function showAuthError(message) {
  // Criar a mensagem de erro
  const errorMessage = document.createElement("div");
  errorMessage.className = "error-message-full";
  errorMessage.innerHTML = `
    <div class="error-icon">
      <i class="icon-error"></i>
    </div>
    <div class="error-content">
      <h3>Erro na autenticação</h3>
      <p>${message}</p>
      <a href="/integracoes" class="btn btn-primary">Voltar para integrações</a>
    </div>
  `;

  // Limpar o conteúdo atual
  document.querySelector(".integration-setup-content").innerHTML = "";

  // Adicionar a mensagem ao DOM
  document
    .querySelector(".integration-setup-content")
    .appendChild(errorMessage);
}
```

## Fluxos de Navegação

### Fluxo de Instalação de Marketplace

1. Usuário acessa o módulo Integrações através do menu lateral
2. Usuário filtra por "marketplaces e hubs" ou visualiza todas as integrações
3. Usuário localiza o marketplace desejado e clica no botão "instalar"
4. Sistema redireciona para a tela de configuração do marketplace
5. Usuário preenche o nome da integração no ERP
6. Usuário clica no botão "conectar com [nome do marketplace]"
7. Sistema redireciona para a página de autenticação do marketplace
8. Usuário realiza a autenticação na plataforma do marketplace
9. Marketplace redireciona de volta para o ERP com o código de autorização
10. Sistema finaliza a configuração e exibe mensagem de sucesso
11. Sistema redireciona para a lista de integrações configuradas

### Fluxo de Visualização de Marketplaces

1. Usuário acessa o módulo Integrações através do menu lateral
2. Usuário clica no filtro "marketplaces e hubs"
3. Sistema exibe apenas as integrações da categoria de marketplaces
4. Usuário pode visualizar os detalhes de cada marketplace disponível

## Componentes Reutilizáveis

### Cards de Integração

```html
<div class="integration-card" data-type="marketplace">
  <div class="integration-logo">
    <img
      src="/assets/images/logos/marketplace-logo.svg"
      alt="Nome do Marketplace"
    />
  </div>
  <div class="integration-info">
    <h3>Nome do Marketplace</h3>
    <p>Marketplace</p>
  </div>
  <div class="integration-action">
    <a href="/integracoes/instalar/ID" class="install-button">instalar</a>
  </div>
</div>
```

```css
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
  text-align: center;
  width: 100%;
}

.install-button:hover {
  background-color: #0066a2;
}
```

### Badges

```html
<div class="integration-badges">
  <span class="badge badge-ml" title="Mercado Livre"></span>
  <span class="badge badge-ml-full" title="Mercado Livre Full"></span>
</div>
```

```css
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
```

### Mensagens de Feedback

```html
<div class="success-message">
  <div class="success-icon">
    <i class="icon-check"></i>
  </div>
  <div class="success-content">
    <h3>Integração configurada com sucesso!</h3>
    <p>Você será redirecionado para a lista de integrações em instantes...</p>
  </div>
</div>

<div class="error-message-full">
  <div class="error-icon">
    <i class="icon-error"></i>
  </div>
  <div class="error-content">
    <h3>Erro na autenticação</h3>
    <p>Mensagem de erro detalhada</p>
    <a href="/integracoes" class="btn btn-primary">Voltar para integrações</a>
  </div>
</div>
```

```css
.success-message {
  background-color: #e8f5e9;
  border-left: 4px solid var(--success-color);
  padding: 20px;
  border-radius: 4px;
  display: flex;
  align-items: flex-start;
  margin-bottom: 20px;
}

.success-icon {
  margin-right: 15px;
  font-size: 24px;
  color: var(--success-color);
}

.success-content h3 {
  font-size: 16px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 5px 0;
}

.success-content p {
  font-size: 14px;
  color: #666;
  margin: 0;
}

.error-message {
  background-color: #ffebee;
  border-left: 4px solid var(--danger-color);
  padding: 10px 15px;
  border-radius: 4px;
  font-size: 14px;
  color: var(--danger-color);
  margin-top: 10px;
}

.error-message-full {
  background-color: #ffebee;
  border-left: 4px solid var(--danger-color);
  padding: 20px;
  border-radius: 4px;
  display: flex;
  align-items: flex-start;
  margin-bottom: 20px;
}

.error-icon {
  margin-right: 15px;
  font-size: 24px;
  color: var(--danger-color);
}

.error-content h3 {
  font-size: 16px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 5px 0;
}

.error-content p {
  font-size: 14px;
  color: #666;
  margin: 0 0 15px 0;
}
```

## Responsividade

```css
/* Estilos para tablets */
@media (max-width: 992px) {
  .integrations-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  }

  .integration-setup-content {
    padding: 20px;
  }
}

/* Estilos para dispositivos móveis */
@media (max-width: 768px) {
  .integrations-grid {
    grid-template-columns: 1fr;
  }

  .integration-setup-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
  }

  .integration-setup-content {
    padding: 15px;
  }

  .auth-section {
    padding: 15px;
  }
}
```

## Observações Adicionais

- A seção "Marketplaces e Hubs" do módulo de Integrações apresenta uma interface intuitiva para instalação e configuração de integrações com diversos marketplaces e hubs de vendas.
- Cada marketplace é representado por um card contendo logo, nome e botão de instalação, facilitando a identificação visual.
- Alguns marketplaces possuem badges indicando funcionalidades específicas, como Mercado Livre Full ou as diferentes lojas do grupo Casas Bahia.
- O processo de instalação segue um fluxo padronizado, com etapas de configuração e autenticação específicas para cada marketplace.
- A autenticação é realizada diretamente na plataforma do marketplace, garantindo segurança e conformidade com as políticas de cada plataforma.
- Após a autenticação bem-sucedida, o sistema exibe uma mensagem de confirmação e redireciona para a lista de integrações configuradas.
- Em caso de erro na autenticação, o sistema exibe uma mensagem detalhada e oferece opções para tentar novamente ou voltar para a lista de integrações.
- O design é responsivo, adaptando-se a diferentes tamanhos de tela e dispositivos.
- Os componentes visuais seguem um padrão consistente, utilizando cores, tipografia e espaçamentos padronizados.
- A documentação detalhada dos componentes HTML, CSS e JavaScript facilita a recriação da interface no Figma, mantendo a consistência visual e funcional.
