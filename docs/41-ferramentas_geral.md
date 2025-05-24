# Análise do Módulo Ferramentas - Geral

## Visão Geral

O módulo Ferramentas do ERP Revo oferece um conjunto de funcionalidades auxiliares para gerenciamento do sistema. A seção "Geral" serve como página inicial do módulo, apresentando a navegação para todos os subitens disponíveis.

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
    <li class="active">
      <a href="/ferramentas_geral" class="tab">
        <span>Geral</span>
      </a>
    </li>
    <li>
      <a href="/ferramentas_importacoes" class="tab">
        <span>Importações</span>
      </a>
    </li>
  </ul>
</div>
```

### Lista de Ferramentas

```html
<div class="tools-list">
  <a href="/ferramentas_backup" class="tool-item">
    <span>Backup</span>
  </a>
  <a href="/ferramentas_exclusao_registros" class="tool-item">
    <span>Exclusão de registros</span>
  </a>
  <a href="/ferramentas_inutilizacoes_nfes" class="tool-item">
    <span>Inutilizações de NFes</span>
  </a>
  <a href="/ferramentas_gerenciar_anexos" class="tool-item">
    <span>Gerenciar Anexos</span>
  </a>
  <a href="/resumo_hub_ecommerce" class="tool-item">
    <span>Resumo de Sincronizações</span>
  </a>
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

### Estilos da Lista de Ferramentas

```css
.tools-list {
  display: flex;
  flex-direction: column;
  padding: 20px 30px;
}

.tool-item {
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

.tool-item:hover {
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

### Navegação do Menu Lateral

```javascript
// Código para gerenciar a navegação do menu lateral
document.querySelectorAll(".menu li a").forEach((menuItem) => {
  menuItem.addEventListener("click", function (e) {
    // Remover classe active de todos os itens do menu
    document.querySelectorAll(".menu li").forEach((item) => {
      item.classList.remove("active");
    });

    // Adicionar classe active ao item clicado
    this.parentElement.classList.add("active");

    // Se não for um link externo ou com comportamento especial, prevenir comportamento padrão
    if (!this.hasAttribute("data-external")) {
      e.preventDefault();

      // Carregar conteúdo correspondente ao item do menu
      const targetUrl = this.getAttribute("href");
      navigateTo(targetUrl);
    }
  });
});

function navigateTo(url) {
  // Função para navegar para uma nova página
  window.location.href = url;
}
```

## Fluxos de Navegação

### Fluxo Principal

1. Usuário acessa o módulo Ferramentas através do menu lateral
2. O sistema exibe a página inicial do módulo (subitem "Geral")
3. Usuário visualiza a lista de ferramentas disponíveis
4. Usuário pode selecionar uma ferramenta específica para acessar

### Navegação entre Subitens

- **Geral**: Página inicial com lista de todas as ferramentas
- **Importações**: Acesso às funcionalidades de importação de dados
- **Backup**: Ferramentas para backup e restauração de dados
- **Exclusão de registros**: Funcionalidades para exclusão segura de registros
- **Inutilizações de NFes**: Gerenciamento de inutilizações de notas fiscais
- **Gerenciar Anexos**: Gerenciamento de arquivos anexados no sistema
- **Resumo de Sincronizações**: Visualização do status das sincronizações

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
}
```

## Observações Adicionais

- O módulo Ferramentas utiliza o mesmo padrão visual do restante do sistema, mantendo a consistência da interface.
- A navegação é intuitiva, com abas claramente definidas e itens de menu destacados quando ativos.
- As ferramentas são apresentadas em formato de lista, facilitando a visualização e acesso.
- O sistema utiliza ícones consistentes para representar cada funcionalidade, melhorando a experiência do usuário.
