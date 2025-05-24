# Análise do Módulo Integrações - Outras Integrações

## Visão Geral

A seção "Outras integrações" do módulo de Integrações do ERP Revo oferece funcionalidades para conectar o sistema a diversos serviços complementares que não se enquadram nas categorias de marketplaces ou plataformas de e-commerce. Esta categoria permite aos usuários instalar e configurar integrações com serviços como Mercos, Conecta Lá, Devi PDV, Hoop, entre outros, ampliando as funcionalidades do ERP e otimizando processos específicos do negócio.

## Estrutura HTML

### Cabeçalho da Categoria

```html
<div class="category-header">
  <h2>Outras integrações</h2>
  <p class="category-description">
    Integrações com sistemas que completam a operação da empresa através de
    diferentes recursos e soluções. Tudo para tornar o sistema flexível e
    completo a fim de otimizar o seu negócio.
  </p>
</div>
```

### Grid de Outras Integrações

```html
<div class="integrations-grid">
  <!-- Mercos -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/mercos.svg" alt="Mercos" />
    </div>
    <div class="integration-info">
      <h3>Mercos</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/64" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Conecta Lá -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/conecta-la.svg" alt="Conecta Lá" />
    </div>
    <div class="integration-info">
      <h3>Conecta Lá</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/72" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Devi PDV -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/devi-pdv.svg" alt="Devi PDV" />
    </div>
    <div class="integration-info">
      <h3>Devi PDV</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/68" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Hoop -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/hoop.svg" alt="Hoop" />
    </div>
    <div class="integration-info">
      <h3>Hoop</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/76" class="install-button">instalar</a>
    </div>
  </div>

  <!-- 99Meli -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/99meli.svg" alt="99Meli" />
    </div>
    <div class="integration-info">
      <h3>99Meli</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/82" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Vesti -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/vesti.svg" alt="Vesti" />
    </div>
    <div class="integration-info">
      <h3>Vesti</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/84" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Dooster -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/dooster.svg" alt="Dooster" />
    </div>
    <div class="integration-info">
      <h3>Dooster</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/86" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Ecomece by Moovin -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img
        src="/assets/images/logos/ecomece-moovin.svg"
        alt="Ecomece by Moovin"
      />
    </div>
    <div class="integration-info">
      <h3>Ecomece by Moovin</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/88" class="install-button">instalar</a>
    </div>
  </div>

  <!-- API do ERP -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/api-erp.svg" alt="API do ERP" />
    </div>
    <div class="integration-info">
      <h3>API do ERP</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/90" class="install-button">instalar</a>
    </div>
  </div>

  <!-- Arquivei -->
  <div class="integration-card" data-type="other">
    <div class="integration-logo">
      <img src="/assets/images/logos/arquivei.svg" alt="Arquivei" />
    </div>
    <div class="integration-info">
      <h3>Arquivei</h3>
      <p>Outra Integração</p>
    </div>
    <div class="integration-action">
      <a href="/integracoes/instalar/92" class="install-button">instalar</a>
    </div>
  </div>
</div>
```

### Tela de Configuração de Outra Integração

```html
<div class="integration-setup">
  <div class="integration-setup-header">
    <div class="integration-logo">
      <img src="/assets/images/logos/mercos.svg" alt="Mercos" />
    </div>
    <h2>Integração com Mercos</h2>
  </div>

  <div class="integration-setup-content">
    <div class="setup-section">
      <h3>Conectar Integração</h3>
      <p>
        Realizar a conexão com o Mercos é o primeiro passo para otimizar o seu
        negócio através do Sistema ERP.
      </p>

      <div class="form-group">
        <label for="integration-name">Nome da integração no ERP</label>
        <input
          type="text"
          id="integration-name"
          class="form-control"
          placeholder="Mercos"
        />
      </div>

      <div class="form-group">
        <label for="api-key">Chave de API</label>
        <input
          type="text"
          id="api-key"
          class="form-control"
          placeholder="Chave de API do Mercos"
        />
        <small class="form-text"
          >Você pode obter sua chave de API nas configurações da sua conta
          Mercos.</small
        >
      </div>

      <div class="auth-section">
        <button type="button" class="btn btn-primary">Conectar</button>
      </div>
    </div>

    <div class="help-section">
      <p>Ficou com alguma dúvida?</p>
      <a href="/ajuda/integracoes/mercos" class="help-link"
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

.form-text {
  display: block;
  font-size: 12px;
  color: #666;
  margin-top: 5px;
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

### Instalação de Outra Integração

```javascript
// Código para gerenciar a instalação de outras integrações
document
  .querySelectorAll('.integration-card[data-type="other"] .install-button')
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
      installOtherIntegration(integrationId, integrationName);
    });
  });

function installOtherIntegration(id, name) {
  // Função para iniciar o processo de instalação de outra integração
  console.log("Iniciando instalação de outra integração:", name, "ID:", id);

  // Redirecionar para a página de instalação
  window.location.href = `/integracoes/other/auth/new/${id}`;
}
```

### Configuração de Outra Integração

```javascript
// Código para gerenciar a configuração de outras integrações
document.addEventListener("DOMContentLoaded", function () {
  const integrationNameInput = document.getElementById("integration-name");
  const apiKeyInput = document.getElementById("api-key");
  const connectButton = document.querySelector(".auth-section .btn-primary");

  if (integrationNameInput && connectButton) {
    // Função para verificar se todos os campos obrigatórios foram preenchidos
    function validateForm() {
      const isNameFilled = integrationNameInput.value.trim() !== "";
      const isApiKeyFilled = apiKeyInput
        ? apiKeyInput.value.trim() !== ""
        : true;

      // Habilitar ou desabilitar o botão de conexão
      if (isNameFilled && isApiKeyFilled) {
        connectButton.removeAttribute("disabled");
      } else {
        connectButton.setAttribute("disabled", "disabled");
      }
    }

    // Adicionar listeners para validar o formulário quando os campos forem alterados
    [integrationNameInput, apiKeyInput].forEach((input) => {
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
      const apiKey = apiKeyInput ? apiKeyInput.value.trim() : "";

      // Verificar se os campos obrigatórios foram preenchidos
      if (integrationName) {
        // Obter o ID da integração a partir da URL
        const urlParts = window.location.pathname.split("/");
        const integrationId = urlParts[urlParts.length - 1];

        // Iniciar o processo de conexão
        connectOtherIntegration(integrationId, integrationName, apiKey);
      }
    });
  }
});

function connectOtherIntegration(id, name, apiKey) {
  // Função para iniciar o processo de conexão com outra integração
  console.log("Iniciando conexão com outra integração:", name, "ID:", id);

  // Construir o objeto de dados para a requisição
  const data = {
    name: name,
  };

  // Adicionar a chave de API, se fornecida
  if (apiKey) data.api_key = apiKey;

  // Fazer a requisição para conectar com a integração
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
            "Não foi possível conectar com a integração. Verifique os dados informados e tente novamente."
        );
      }
    })
    .catch((error) => {
      console.error("Erro ao conectar com a integração:", error);
      showErrorMessage(
        "Ocorreu um erro ao conectar com a integração. Tente novamente mais tarde."
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

### Fluxo de Instalação de Outra Integração

1. Usuário acessa o módulo Integrações através
   (Content truncated due to size limit. Use line ranges to read in chunks)
