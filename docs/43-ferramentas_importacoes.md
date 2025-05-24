# Análise do Módulo Ferramentas - Importações

## Visão Geral

O subitem "Importações" do módulo Ferramentas do ERP Revo oferece funcionalidades para importação de dados de diferentes áreas do sistema. Esta seção permite aos usuários importar informações de cadastros, suprimentos e vendas, facilitando a migração e atualização em massa de dados no sistema.

## Estrutura HTML

### Cabeçalho

```html
<div class="header">
  <div class="breadcrumb">
    <a href="/inicio"><i class="icon-home"></i> Início</a>
    <span class="separator">/</span>
    <span class="current">Ferramentas</span>
  </div>
  <h1>Ferramentas</h1>
</div>
```

### Navegação Principal

```html
<div class="tabs-container">
  <ul class="nav-tabs">
    <li>
      <a href="/ferramentas_geral" class="tab">
        <span>Geral</span>
      </a>
    </li>
    <li class="active">
      <a href="/ferramentas_importacoes" class="tab">
        <span>Importações</span>
      </a>
    </li>
  </ul>
</div>
```

### Seções de Importação

```html
<div class="import-sections">
  <!-- Seção de Cadastros -->
  <div class="section">
    <h2 class="section-title">Cadastros</h2>
    <div class="section-content">
      <a href="/ferramentas_importacoes/contatos" class="import-item">
        <span>Contatos</span>
      </a>
      <a href="/ferramentas_importacoes/contatos_clientes" class="import-item">
        <span>Contatos dos clientes</span>
      </a>
      <a href="/ferramentas_importacoes/produtos" class="import-item">
        <span>Produtos</span>
      </a>
      <a href="/ferramentas_importacoes/kits_produtos" class="import-item">
        <span>Kits e Produtos Fabricados</span>
      </a>
      <a href="/ferramentas_importacoes/precos_produtos" class="import-item">
        <span>Preços dos produtos</span>
      </a>
    </div>
  </div>

  <!-- Seção de Suprimentos -->
  <div class="section">
    <h2 class="section-title">Suprimentos</h2>
    <div class="section-content">
      <a href="/ferramentas_importacoes/estoque" class="import-item">
        <span>Estoque</span>
      </a>
      <a href="/ferramentas_importacoes/ordens_compra" class="import-item">
        <span>Ordens de Compra</span>
      </a>
    </div>
  </div>

  <!-- Seção de Vendas -->
  <div class="section">
    <h2 class="section-title">Vendas</h2>
    <div class="section-content">
      <a href="/ferramentas_importacoes/pedidos_venda" class="import-item">
        <span>Pedidos de Venda</span>
      </a>
      <a
        href="/ferramentas_importacoes/propostas_comerciais"
        class="import-item"
      >
        <span>Propostas Comerciais</span>
      </a>
      <a
        href="/ferramentas_importacoes/atualizar_info_envio"
        class="import-item"
      >
        <span>Atualizar informações de envio</span>
      </a>
    </div>
  </div>

  <!-- Seção de Notas Fiscais -->
  <div class="section">
    <h2 class="section-title">Notas Fiscais</h2>
    <div class="section-content">
      <!-- Itens de importação de notas fiscais seriam listados aqui -->
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

### Estilos da Navegação por Abas

```css
.tabs-container {
  background-color: #fff;
  border-bottom: 1px solid var(--border-color);
}

.nav-tabs {
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-tabs li {
  margin-right: 2px;
}

.nav-tabs li a {
  display: block;
  padding: 12px 20px;
  color: var(--text-color);
  text-decoration: none;
  border-bottom: 3px solid transparent;
  transition: all 0.2s ease;
}

.nav-tabs li.active a {
  border-bottom-color: var(--primary-color);
  font-weight: 500;
}

.nav-tabs li a:hover {
  background-color: var(--light-gray);
}
```

### Estilos das Seções de Importação

```css
.import-sections {
  padding: 20px 30px;
}

.section {
  margin-bottom: 30px;
}

.section-title {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  margin: 0 0 15px 0;
  padding-bottom: 10px;
  border-bottom: 1px solid var(--section-divider);
}

.section-content {
  display: flex;
  flex-direction: column;
}

.import-item {
  display: block;
  padding: 15px 20px;
  margin-bottom: 10px;
  background-color: #fff;
  border: 1px solid var(--border-color);
  border-radius: 4px;
  color: var(--text-color);
  text-decoration: none;
  transition: all 0.2s ease;
}

.import-item:hover {
  background-color: var(--light-gray);
  border-color: var(--primary-color);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
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

### Navegação entre Abas

```javascript
// Código para gerenciar a navegação entre abas
document.querySelectorAll(".nav-tabs li a").forEach((tab) => {
  tab.addEventListener("click", function (e) {
    // Remover classe active de todas as abas
    document.querySelectorAll(".nav-tabs li").forEach((item) => {
      item.classList.remove("active");
    });

    // Adicionar classe active à aba clicada
    this.parentElement.classList.add("active");

    // Carregar conteúdo correspondente à aba
    const targetUrl = this.getAttribute("href");
    loadContent(targetUrl);

    e.preventDefault();
  });
});

function loadContent(url) {
  // Função para carregar o conteúdo via AJAX
  fetch(url)
    .then((response) => response.text())
    .then((html) => {
      document.querySelector(".content-container").innerHTML = html;
    })
    .catch((error) => {
      console.error("Erro ao carregar conteúdo:", error);
    });
}
```

### Navegação para Itens de Importação

```javascript
// Código para gerenciar a navegação para itens de importação
document.querySelectorAll(".import-item").forEach((item) => {
  item.addEventListener("click", function (e) {
    // Obter URL do item de importação
    const targetUrl = this.getAttribute("href");

    // Navegar para a página de importação específica
    navigateToImport(targetUrl);

    e.preventDefault();
  });
});

function navigateToImport(url) {
  // Função para navegar para uma página de importação específica
  window.location.href = url;
}
```

## Fluxos de Navegação

### Fluxo Principal

1. Usuário acessa o módulo Ferramentas através do menu lateral
2. Usuário seleciona a aba "Importações"
3. O sistema exibe as seções de importação disponíveis (Cadastros, Suprimentos, Vendas, Notas Fiscais)
4. Usuário seleciona um item específico de importação para acessar

### Fluxo de Importação Típico

1. Usuário seleciona um item específico de importação (ex: Produtos)
2. Sistema exibe a página de importação com instruções e opções
3. Usuário seleciona arquivo para importação ou insere dados manualmente
4. Sistema valida os dados e exibe resultados da importação
5. Usuário confirma a importação ou corrige erros
6. Sistema processa a importação e exibe status de conclusão

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

### Cards

```html
<div class="card">
  <div class="card-header">Título do Card</div>
  <div class="card-body">Conteúdo do card</div>
  <div class="card-footer">
    <button class="btn btn-primary">Ação</button>
  </div>
</div>
```

```css
.card {
  background-color: #fff;
  border-radius: 4px;
  border: 1px solid var(--border-color);
  overflow: hidden;
  margin-bottom: 20px;
}

.card-header {
  padding: 15px 20px;
  background-color: var(--light-gray);
  border-bottom: 1px solid var(--border-color);
  font-weight: 500;
}

.card-body {
  padding: 20px;
}

.card-footer {
  padding: 15px 20px;
  background-color: var(--light-gray);
  border-top: 1px solid var(--border-color);
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

  .import-sections {
    padding: 15px 20px;
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
  }

  .menu li a {
    padding: 10px 15px;
  }

  .nav-tabs {
    flex-wrap: wrap;
  }

  .nav-tabs li {
    margin-bottom: 5px;
  }

  .import-item {
    padding: 12px 15px;
  }
}
```

## Observações Adicionais

- O subitem "Importações" do módulo Ferramentas organiza as opções de importação em categorias lógicas (Cadastros, Suprimentos, Vendas, Notas Fiscais), facilitando a localização das funcionalidades.
- Cada item de importação segue um padrão visual consistente, com cards ou links destacados que indicam claramente a função.
- A interface mantém o mesmo padrão visual do restante do sistema, garantindo consistência na experiência do usuário.
- As opções de importação são apresentadas de forma clara e organizada, com separadores visuais entre as diferentes categorias.
- O sistema utiliza feedback visual (hover, active states) para indicar interatividade dos elementos.
