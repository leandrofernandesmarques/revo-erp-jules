# Análise do Dashboard - ERP Revo

## Estrutura Geral

O Dashboard do ERP Revo apresenta uma interface moderna e organizada, com um layout que prioriza a visualização de dados importantes para o usuário. A estrutura é composta por um menu lateral à esquerda e uma área principal de conteúdo à direita.

## Componentes Principais

### Menu Lateral

O menu lateral é um componente fundamental da interface, apresentando uma estrutura hierárquica de navegação com as seguintes características:

- Logotipo da Revo no topo
- Seções principais do sistema (Início, Cadastros, Suprimentos, Vendas, Finanças, Serviços)
- Submenus expansíveis para cada seção principal
- Indicadores visuais para o item ativo (destacado com cor diferenciada)
- Opção para expandir/recolher o menu
- Ícones associados a cada item de menu

**Estrutura HTML:**

```html
<div class="menu-lateral">
  <div class="logo-container">
    <img src="logo-Revo.svg" alt="Logo Revo" />
  </div>
  <div class="menu-principal">
    <div class="menu-item ativo">
      <a href="/inicio">
        <span class="icone inicio-icon"></span>
        <span class="texto">Início</span>
      </a>
    </div>
    <!-- Outros itens de menu -->
  </div>
  <div class="submenu">
    <div class="submenu-item ativo">
      <a href="/dashboard">
        <span class="icone dashboard-icon"></span>
        <span class="texto">Dashboard</span>
      </a>
    </div>
    <!-- Outros itens de submenu -->
  </div>
  <div class="menu-toggle">
    <label class="switch">
      <input type="checkbox" />
      <span class="slider"></span>
    </label>
    <span class="texto">Expandir menu</span>
  </div>
</div>
```

**Estilos CSS:**

```css
.menu-lateral {
  width: 240px;
  height: 100vh;
  background-color: #f5f5f5;
  border-right: 1px solid #e0e0e0;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 100;
  transition: width 0.3s ease;
}

.menu-item {
  padding: 12px 16px;
  display: flex;
  align-items: center;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.menu-item:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.menu-item.ativo {
  background-color: #e6f7ff;
  border-left: 3px solid #1890ff;
}

.icone {
  width: 20px;
  height: 20px;
  margin-right: 12px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.menu-toggle {
  position: absolute;
  bottom: 16px;
  left: 16px;
  display: flex;
  align-items: center;
}

.switch {
  position: relative;
  display: inline-block;
  width: 40px;
  height: 20px;
  margin-right: 8px;
}
```

### Cabeçalho

O cabeçalho está presente em todas as páginas e contém:

- Breadcrumbs para navegação
- Título da página atual
- Ícones de ações rápidas (ajuda, notificações, perfil)
- Indicador de usuário logado

**Estrutura HTML:**

```html
<header class="cabecalho">
  <div class="breadcrumbs">
    <a href="/inicio">Início</a>
    <span class="separador">/</span>
    <a href="/dashboard">Dashboard</a>
  </div>
  <h1 class="titulo-pagina">Dashboard de vendas</h1>
  <div class="acoes-rapidas">
    <a
      href="#"
      class="icone-acao aparencia"
      aria-label="Aparência do ERP da Revo"
    ></a>
    <a href="#" class="icone-acao ajuda">?</a>
    <a href="#" class="icone-acao notificacoes">0</a>
    <a href="#" class="icone-acao perfil">LM</a>
  </div>
</header>
```

**Estilos CSS:**

```css
.cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
  height: 64px;
}

.breadcrumbs {
  font-size: 14px;
  color: #666;
}

.breadcrumbs .separador {
  margin: 0 8px;
}

.titulo-pagina {
  font-size: 20px;
  font-weight: 500;
  color: #333;
  margin: 0;
}

.acoes-rapidas {
  display: flex;
  align-items: center;
}

.icone-acao {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 8px;
  background-color: #f5f5f5;
  color: #333;
  text-decoration: none;
}

.icone-acao.perfil {
  background-color: #1890ff;
  color: white;
}
```

### Área de Filtros

A área de filtros permite ao usuário personalizar os dados exibidos no dashboard:

- Seletor de período (últimos 7 dias, etc.)
- Botão de filtros avançados
- Indicador de última atualização
- Botão de atualização manual

**Estrutura HTML:**

```html
<div class="area-filtros">
  <div class="filtro-periodo">
    <a href="#" class="botao-filtro periodo">
      <span class="icone calendario"></span>
      <span class="texto">últimos 7 dias</span>
    </a>
  </div>
  <div class="filtros-avancados">
    <a href="#" class="botao-filtro">
      <span class="icone filtro"></span>
      <span class="texto">Filtros</span>
    </a>
  </div>
  <div class="atualizacao">
    <a href="#" class="botao-filtro">
      <span class="icone atualizar"></span>
      <span class="texto">atualizado agora</span>
    </a>
  </div>
  <button class="botao-atualizar"></button>
</div>
```

**Estilos CSS:**

```css
.area-filtros {
  display: flex;
  align-items: center;
  padding: 12px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.botao-filtro {
  display: flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #f5f5f5;
  border-radius: 4px;
  margin-right: 12px;
  text-decoration: none;
  color: #333;
  font-size: 14px;
}

.botao-filtro .icone {
  margin-right: 8px;
}

.botao-atualizar {
  width: 32px;
  height: 32px;
  border-radius: 4px;
  background-color: #f5f5f5;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Cards de Métricas

Os cards de métricas exibem informações importantes de forma visual e direta:

- Total das vendas
- Ticket médio
- Gráficos de tendência
- Opção para expandir detalhes

**Estrutura HTML:**

```html
<div class="card-metrica">
  <div class="card-cabecalho">
    <h3 class="card-titulo">Total das vendas</h3>
  </div>
  <div class="card-conteudo">
    <div class="valor-principal">R$ 0,00</div>
    <div class="grafico-tendencia">
      <div class="escala">R$ 100</div>
      <div class="grafico-linha">
        <!-- Gráfico de linha -->
      </div>
      <div class="eixo-x">
        <span>Ter</span>
        <span>Qua</span>
        <span>Qui</span>
        <span>Sex</span>
        <span>Sáb</span>
        <span>Dom</span>
        <span>Seg</span>
      </div>
    </div>
  </div>
  <div class="card-rodape">
    <a href="#" class="link-expandir">expandir detalhes</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.card-metrica {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  margin-bottom: 24px;
  overflow: hidden;
}

.card-cabecalho {
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.card-titulo {
  margin: 0;
  font-size: 16px;
  font-weight: 500;
  color: #333;
}

.card-conteudo {
  padding: 16px;
}

.valor-principal {
  font-size: 24px;
  font-weight: 500;
  color: #333;
  margin-bottom: 16px;
}

.grafico-tendencia {
  height: 120px;
  position: relative;
}

.escala {
  position: absolute;
  left: 0;
  top: 0;
  font-size: 12px;
  color: #999;
}

.eixo-x {
  display: flex;
  justify-content: space-between;
  margin-top: 8px;
  font-size: 12px;
  color: #999;
}

.card-rodape {
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
  text-align: center;
}

.link-expandir {
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
}
```

### Visão Geral

A seção de visão geral apresenta indicadores-chave em formato de ícones com valores:

- Número de pedidos
- Vendas em e-commerce
- Vendas físicas
- Valor total
- NF-e emitidas
- Status de integração

**Estrutura HTML:**

```html
<div class="secao-visao-geral">
  <h3 class="secao-titulo">Visão geral</h3>
  <div class="indicadores-container">
    <div class="indicador">
      <div class="indicador-icone pedidos"></div>
      <div class="indicador-valor">0</div>
      <div class="indicador-legenda">pedidos</div>
    </div>
    <!-- Outros indicadores -->
  </div>
</div>
```

**Estilos CSS:**

```css
.secao-visao-geral {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  padding: 16px;
  margin-bottom: 24px;
}

.secao-titulo {
  margin: 0 0 16px 0;
  font-size: 16px;
  font-weight: 500;
  color: #333;
}

.indicadores-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.indicador {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: calc(16.66% - 16px);
  margin-bottom: 16px;
}

.indicador-icone {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #f5f5f5;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 8px;
}

.indicador-valor {
  font-size: 18px;
  font-weight: 500;
  color: #333;
  margin-bottom: 4px;
}

.indicador-legenda {
  font-size: 12px;
  color: #999;
  text-align: center;
}
```

### Gráficos e Visualizações

O dashboard inclui diversas visualizações de dados:

- Gráficos de barras
- Mapas para visualização geográfica
- Listas de produtos mais vendidos

**Estrutura HTML:**

```html
<div class="card-grafico">
  <div class="card-cabecalho">
    <h3 class="card-titulo">Pedidos por estado</h3>
  </div>
  <div class="card-conteudo">
    <div class="mapa-brasil">
      <!-- Mapa SVG do Brasil -->
    </div>
  </div>
</div>

<div class="card-grafico">
  <div class="card-cabecalho">
    <h3 class="card-titulo">Pedidos por integrações</h3>
  </div>
  <div class="card-conteudo">
    <div class="mensagem-sem-dados">
      Sem dados para essa combinação de filtros, tente outra.
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.card-grafico {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  margin-bottom: 24px;
  overflow: hidden;
}

.mapa-brasil {
  height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.mensagem-sem-dados {
  padding: 32px;
  text-align: center;
  color: #999;
  font-size: 14px;
}
```

## Interações JavaScript

### Navegação entre Abas

O dashboard permite alternar entre diferentes visualizações (Vendas, Finanças) através de abas:

```javascript
// Código para alternar entre abas
document.querySelectorAll(".aba").forEach((aba) => {
  aba.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todas as abas
    document.querySelectorAll(".aba").forEach((item) => {
      item.classList.remove("ativo");
    });

    // Adiciona classe ativo à aba clicada
    this.classList.add("ativo");

    // Carrega o conteúdo correspondente
    const tipo = this.getAttribute("data-tipo");
    carregarDashboard(tipo);
  });
});

function carregarDashboard(tipo) {
  // Lógica para carregar os dados do dashboard conforme o tipo
  // Faz requisição AJAX para obter os dados
  fetch(`/api/dashboard/${tipo}`)
    .then((response) => response.json())
    .then((data) => {
      // Atualiza os componentes do dashboard com os novos dados
      atualizarComponentes(data);
    });
}
```

### Filtros e Atualização de Dados

Os filtros permitem personalizar a visualização dos dados:

```javascript
// Código para aplicar filtros
document
  .querySelector(".botao-filtro.periodo")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre modal de seleção de período
    abrirModalPeriodo();
  });

document
  .querySelector(".botao-filtro.filtros")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre modal de filtros avançados
    abrirModalFiltros();
  });

document
  .querySelector(".botao-atualizar")
  .addEventListener("click", function () {
    // Atualiza os dados do dashboard
    atualizarDados();
  });

function atualizarDados() {
  // Obtém os filtros ativos
  const filtros = obterFiltrosAtivos();

  // Atualiza o indicador de última atualização
  document.querySelector(".atualizacao .texto").textContent =
    "atualizado agora";

  // Faz requisição para obter dados atualizados
  fetch("/api/dashboard/dados", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(filtros),
  })
    .then((response) => response.json())
    .then((data) => {
      // Atualiza os componentes do dashboard
      atualizarComponentes(data);
    });
}
```

### Expansão de Detalhes

Os cards permitem expandir para visualizar mais detalhes:

```javascript
// Código para expandir detalhes dos cards
document.querySelectorAll(".link-expandir").forEach((link) => {
  link.addEventListener("click", function (e) {
    e.preventDefault();

    // Obtém o card pai
    const card = this.closest(".card-metrica");

    // Obtém o tipo de métrica
    const metrica = card.getAttribute("data-metrica");

    // Abre modal com detalhes expandidos
    abrirModalDetalhes(metrica);
  });
});

function abrirModalDetalhes(metrica) {
  // Cria e exibe o modal com detalhes expandidos
  const modal = document.createElement("div");
  modal.classList.add("modal-detalhes");

  // Obtém dados detalhados da métrica
  fetch(`/api/metricas/${metrica}/detalhes`)
    .then((response) => response.json())
    .then((data) => {
      // Preenche o modal com os dados detalhados
      preencherModalDetalhes(modal, data);

      // Adiciona o modal ao DOM
      document.body.appendChild(modal);
    });
}
```

## Responsividade

O dashboard é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .indicador {
    width: calc(33.33% - 16px);
  }

  .menu-lateral.recolhido {
    width: 64px;
  }

  .menu-lateral.recolhido .texto {
    display: none;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .indicador {
    width: calc(50% - 16px);
  }

  .area-filtros {
    flex-wrap: wrap;
  }

  .botao-filtro {
    margin-bottom: 8px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .indicador {
    width: 100%;
  }

  .menu-lateral {
    transform: translateX(-100%);
    position: fixed;
    z-index: 1000;
  }

  .menu-lateral.aberto {
    transform: translateX(0);
  }

  .menu-toggle-mobile {
    display: block;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 20px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Botões

```css
.botao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-secundario {
  background-color: white;
  color: #1890ff;
  border: 1px solid #1890ff;
}

.botao-terciario {
  background-color: #f5f5f5;
  color: #333;
  border: none;
}
```

### Ícones

```css
.icone {
  width: 20px;
  height: 20px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.icone-texto {
  display: inline-flex;
  align-items: center;
}

.icone-texto .icone {
  margin-right: 8px;
}
```

### Cards

```css
.card {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.card-cabecalho {
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.card-conteudo {
  padding: 16px;
}

.card-rodape {
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
}
```

## Fluxos de Navegação

1. **Navegação Principal**:
   - Menu lateral permite acesso a todos os módulos principais
   - Submenu expande para mostrar opções e
     (Content truncated due to size limit. Use line ranges to read in chunks)
