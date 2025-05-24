# Análise do Módulo Integrações - Plataformas de e-commerce

## Visão Geral

A seção "Plataformas de e-commerce" do módulo de Integrações do ERP Revo oferece funcionalidades para conectar o sistema a diversas plataformas de lojas virtuais. Esta categoria permite aos usuários instalar e configurar integrações com plataformas como Revo Vnda, Nuvemshop, Shopify, WooCommerce, entre outras, facilitando a gestão de vendas online e a sincronização de dados entre o ERP e as lojas virtuais.

## Estrutura HTML

### Cabeçalho da Categoria

```html
<div class="category-header">
  <h2>Plataformas de e-commerce</h2>
  <p class="category-description">
    Sistemas que permitem a criação, publicação e gerenciamento de lojas
    virtuais. As plataformas de e-commerce disponibilizam a vitrine online para
    a divulgação dos produtos oferecidos por empresas dos mais variados
    segmentos.
  </p>
</div>
```

### Grid de Integrações de E-commerce

```html
<div class="integrations-grid">
  <!-- Revo Vnda Commerce -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/Revo-vnda-commerce.svg"
        alt="Revo Vnda Commerce"
      />
    </div>
    <div class="integration-info">
      <h3>Revo Vnda Commerce</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/51" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Revo Vnda -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/Revo-vnda.svg" alt="Revo Vnda" />
    </div>
    <div class="integration-info">
      <h3>Revo Vnda</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/52" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Nuvemshop -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/nuvemshop.svg" alt="Nuvemshop" />
    </div>
    <div class="integration-info">
      <h3>Nuvemshop</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/32" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Tray -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/tray.svg" alt="Tray" />
    </div>
    <div class="integration-info">
      <h3>Tray</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/36" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Loja Integrada -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/loja-integrada.svg" alt="Loja Integrada" />
    </div>
    <div class="integration-info">
      <h3>Loja Integrada</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/24" class="install-button">instalar</a>
    </div>
  </div>

  <!-- WooCommerce -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/woocommerce.svg" alt="WooCommerce" />
    </div>
    <div class="integration-info">
      <h3>WooCommerce</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/18" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Shopify -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/shopify.svg" alt="Shopify" />
    </div>
    <div class="integration-info">
      <h3>Shopify</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/16" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Wix -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/wix.svg" alt="Wix" />
    </div>
    <div class="integration-info">
      <h3>Wix</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/44" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Magento -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/magento.svg" alt="Magento" />
    </div>
    <div class="integration-info">
      <h3>Magento</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/26" class="install-button">instalar</a>
    </div>
  </div>

  <!-- OpenCart -->
  <div class="integration-card" data-type="ecommerce">
    <div class="integration-logo">
      <img src="/assets/images/logos/opencart.svg" alt="OpenCart" />
    </div>
    <div class="integration-info">
      <h3>OpenCart</h3>
      <p>Plataforma de e-commerce</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/30" class="install-button">instalar</a>
    </div>
  </div>
</div>
```

### Tela de Configuração de E-commerce

```html
<div class="integration-setup">
  <div class="integration-setup-header">
    <div class="integration-logo">
      <img src="/assets/images/logos/woocommerce.svg" alt="WooCommerce" />
    </div>
    <h2>Integração com WooCommerce</h2>
  </div>

  <div class="integration-setup-content">
    <div class="setup-section">
      <h3>Conectar Integração</h3>
      <p>
        Realizar a conexão com a plataforma de e-commerce é o primeiro passo
        para otimizar o seu negócio de vendas online através do Sistema ERP.
      </p>

      <div class="form-group">
        <label for="integration-name">Nome da integração no ERP</label>
        <input
          type="text"
          id="integration-name"
          class="form-control"
          placeholder="WooCommerce"
        />
      </div>

      <div class="form-group">
        <label for="store-url">URL da loja</label>
        <input
          type="text"
          id="store-url"
          class="form-control"
          placeholder="https://minhaloja.com.br"
        />
      </div>

      <div class="form-group">
        <label for="consumer-key">Consumer Key</label>
        <input
          type="text"
          id="consumer-key"
          class="form-control"
          placeholder="ck_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
        />
      </div>

      <div class="form-group">
        <label for="consumer-secret">Consumer Secret</label>
        <input
          type="text"
          id="consumer-secret"
          class="form-control"
          placeholder="cs_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
        />
      </div>

      <div class="auth-section">
        <button type="button" class="btn btn-primary">Conectar</button>
      </div>
    </div>

    <div class="help-section">
      <p>Ficou com alguma dúvida?</p>
      <a href="/ajuda/integracoes/woocommerce" class="help-link"
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
  margin-top: 30px;
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

### Instalação de Plataforma E-commerce

```javascript
// Código para gerenciar a instalação de plataformas de e-commerce
document
  .querySelectorAll('.integration-card[data-type="ecommerce"] .install-button')
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
      installEcommerce(integrationId, integrationName);
    });
  });

function installEcommerce(id, name) {
  // Função para iniciar o processo de instalação da plataforma de e-commerce
  console.log(
    "Iniciando instalação da plataforma de e-commerce:",
    name,
    "ID:",
    id
  );

  // Redirecionar para a página de instalação
  window.location.href = `/integracoes/ecommerce/auth/new/${id}`;
}
```

### Configuração de Plataforma E-commerce

```javascript
// Código para gerenciar a configuração de plataformas de e-commerce
document.addEventListener("DOMContentLoaded", function () {
  const integrationNameInput = document.getElementById("integration-name");
  const storeUrlInput = document.getElementById("store-url");
  const consumerKeyInput = document.getElementById("consumer-key");
  const consumerSecretInput = document.getElementById("consumer-secret");
  const connectButton = document.querySelector(".auth-section .btn-primary");

  if (integrationNameInput && connectButton) {
    // Função para verificar se todos os campos obrigatórios foram preenchidos
    function validateForm() {
      const isNameFilled = integrationNameInput.value.trim() !== "";
      const isUrlFilled = storeUrlInput
        ? storeUrlInput.value.trim() !== ""
        : true;
      const isKeyFilled = consumerKeyInput
        ? consumerKeyInput.value.trim() !== ""
        : true;
      const isSecretFilled = consumerSecretInput
        ? consumerSecretInput.value.trim() !== ""
        : true;

      // Habilitar ou desabilitar o botão de conexão
      if (isNameFilled && isUrlFilled && isKeyFilled && isSecretFilled) {
        connectButton.removeAttribute("disabled");
      } else {
        connectButton.setAttribute("disabled", "disabled");
      }
    }

    // Adicionar listeners para validar o formulário quando os campos forem alterados
    [
      integrationNameInput,
      storeUrlInput,
      consumerKeyInput,
      consumerSecretInput,
    ].forEach((input) => {
      if (input) {
        input.addEventListener("input", validateForm);
      }
    });

    // Validar o formulário inicialmente
    validateForm();

    // Iniciar o processo de conexão
    connectButton.addEventListener("click", function () {
      // Obter os valores dos campos
      const integrationName = integrationNameInput.value.trim();
      const storeUrl = storeUrlInput ? storeUrlInput.value.trim() : "";
      const consumerKey = consumerKeyInput ? consumerKeyInput.value.trim() : "";
      const consumerSecret = consumerSecretInput
        ? consumerSecretInput.value.trim()
        : "";

      // Verificar se os campos obrigatórios foram preenchidos
      if (integrationName) {
        // Obter o ID da integração a partir da URL
        const urlParts = window.location.pathname.split("/");
        const integrationId = urlParts[urlParts.length - 1];

        // Iniciar o processo de conexão
        connectEcommerce(
          integrationId,
          integrationName,
          storeUrl,
          consumerKey,
          consumerSecret
        );
      }
    });
  }
});

function connectEcommerce(id, name, url, key, secret) {
  // Função para iniciar o processo de conexão com a plataforma de e-commerce
  console.log(
    "Iniciando conexão com a plataforma de e-commerce:",
    name,
    "ID:",
    id
  );

  // Construir o objeto de dados para a requisição
  const data = {
    name: name,
  };

  // Adicionar os campos específicos da plataforma, se fornecidos
  if (url) data.store_url = url;
  if (key) data.consumer_key = key;
  if (secret) data.consumer_secret = secret;

  // Fazer a requisição para conectar com a plataforma
  fetch(`/api/integrations/${id}/connect`, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(data),
  })
    .then((response) => response.json())
    .then((data) => {
      if (data.success) {
        // Se a conexão for bem-sucedida, exibir mensagem de sucesso
        showSuccessMessage();

        // Redirecionar para a lista de integrações configuradas
        setTimeout(() => {
          window.location.href = "/integracoes";
        }, 3000);
      } else if (data.redirect_url) {
        // Se for necessário redirecionar para autenticação externa
        window.location.href = data.redirect_url;
      } else {
        // Se houver erro, exibir mensagem
        showErrorMessage(
          data.message ||
            "Não foi possível conectar com a plataforma. Verifique os dados informados e tente novamente."
        );
      }
    })
    .catch((error) => {
      console.error("Erro ao conectar com a plataforma:", error);
      showErrorMessage(
        "Ocorreu um erro ao conectar com a plataforma. Tente novamente mais tarde."
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

## Fluxos de Navegação

### Fluxo de Instalação de Plataforma E-commerce

1. Usuário acessa o módulo Integrações através do menu lateral
2. Usuário filtra por "plataformas de e-commerce" ou visualiza todas as integrações
3. Usuário localiza a plataforma desejada e clica no botão "instalar"
4. Sistema redireciona para a tela de configuração da plataforma
5. Usuário preenche as informações necessárias (nome da integração, URL da loja, credenciais)
6. Usuário clica no botão "Conectar"
7. Sistema realiza a conexão com a plataforma
8. Se necessário, sistema redireciona para autenticação externa na plataforma
9. Sistema finaliza a configuração e exibe mensagem de sucesso
10. Sistema redireciona para a lista de integrações configuradas

### Fluxo de Visualização de Plataformas E-commerce

1. Usuário acessa o módulo Integrações através do menu lateral
2. Usuário clica no filtro "plataformas de e-commerce"
3. Sistema exibe apenas as integrações da categoria de plataformas de e-commerce
4. Usuário pode visualizar os detalhes de cada plataforma disponível

## Componentes Reutilizáveis

### Cards de Integração

```html
<div class="integration-card" data-type="ecommerce">
  <div class="integration-logo">
    <img
      src="/assets/images/logos/ecommerce-logo.svg"
      alt="Nome da Plataforma"
    />
  </div>
  <div class="integration-info">
    <h3>Nome da Plataforma</h3>
    <p>Plataforma de e-commerce</p>
  </div>
  <div class="integration-action">
    <a href="/integracoes/instalar/ID" class="install-button">instalar</a>
  </div>
</div>
```

### Formulários de Configuração

```html
<div class="form-group">
  <label for="field-id">Nome do Campo</label>
  <input
    type="text"
    id="field-id"
    class="form-control"
    placeholder="Placeholder"
  />
  <small class="form-text">Texto de ajuda para o campo</small>
</div>
```

```css
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

.form-text {
  display: block;
  font-size: 12px;
  color: #666;
  margin-top: 5px;
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

<div class="error-message">Mensagem de erro detalhada</div>
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
}
```

## Observações Adicionais

- A seção "Plataformas de e-commerce" do módulo de Integrações apresenta uma interface intuitiva para instalação e configuração de integrações com diversas plataformas de lojas virtuais.
- Cada plataforma é representada por um card contendo logo, nome e botão de instalação, facilitando a identificação visual.
- O processo de instalação varia de acordo com a plataforma, mas segue um fluxo padronizado, com etapas de configuração específicas para cada uma.
- Algumas plataformas requerem apenas nome e URL da loja, enquanto outras necessitam de credenciais específicas, como chaves de API ou tokens de acesso.
- A autenticação pode ser realizada diretamente no ERP ou redirecionada para a plataforma externa, dependendo dos requisitos de cada integração.
- Após a configuração bem-sucedida, o sistema exibe uma mensagem de confirmação e redireciona para a lista de integrações configuradas.
- Em caso de erro na configuração, o sistema exibe uma mensagem detalhada e permite que o usuário corrija os dados informados.
- O design é responsivo, adaptando-se a diferentes tamanhos de tela e dispositivos.
- Os componentes visuais seguem um padrão consistente, utilizando cores, tipografia e espaçamentos padronizados.
- A documentação detalhada dos componentes HTML, CSS e JavaScript facilita a recriação da interface no Figma, mantendo a consistência visual e funcional.
