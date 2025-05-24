# Análise do Módulo Relatórios de Vendas - ERP Revo

## Estrutura Geral

O módulo "Relatórios" do ERP Revo na seção de Vendas apresenta uma interface organizada para acesso a diferentes tipos de relatórios relacionados às operações de vendas. A tela principal exibe categorias de relatórios e uma lista de relatórios disponíveis com suas descrições.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação:

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <div class="breadcrumb">
      <a href="/inicio" class="breadcrumb-item">Início</a>
      <span class="breadcrumb-separador">/</span>
      <a href="/vendas" class="breadcrumb-item">Vendas</a>
      <span class="breadcrumb-separador">/</span>
      <span class="breadcrumb-item breadcrumb-ativo">Relatórios</span>
    </div>
    <h1 class="titulo-modulo">Relatórios de Vendas</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-primario" id="btn-outros-relatorios">
      <span class="icone icone-relatorio"></span>
      <span class="texto">outros relatórios</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.modulo-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.breadcrumb {
  display: flex;
  align-items: center;
  font-size: 14px;
  color: #666666;
  margin-bottom: 8px;
}

.breadcrumb-item {
  color: #1890ff;
  text-decoration: none;
}

.breadcrumb-item:hover {
  text-decoration: underline;
}

.breadcrumb-separador {
  margin: 0 8px;
  color: #d9d9d9;
}

.breadcrumb-ativo {
  color: #666666;
}

.titulo-modulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.acoes-container {
  display: flex;
  gap: 8px;
}

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
  text-decoration: none;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao .icone {
  margin-right: 8px;
  font-size: 16px;
}
```

### Categorias de Relatórios

A seção de categorias permite filtrar os relatórios por tipo:

**Estrutura HTML:**

```html
<div class="categorias-container">
  <a href="#" class="categoria-item categoria-ativa" data-categoria="geral">
    <span class="texto">Geral</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="crm">
    <span class="texto">CRM</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="expedicao">
    <span class="texto">Expedição</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="notas-fiscais">
    <span class="texto">Notas Fiscais</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="pdv">
    <span class="texto">PDV</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="pedidos-venda">
    <span class="texto">Pedidos de Venda</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="propostas-comerciais">
    <span class="texto">Propostas Comerciais</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.categorias-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.categoria-item {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  border: 1px solid #e0e0e0;
}

.categoria-item:hover {
  background-color: #f5f5f5;
}

.categoria-ativa {
  background-color: #f0f5ff;
  color: #1890ff;
  border-color: #d6e4ff;
}
```

### Lista de Relatórios

A lista de relatórios exibe os relatórios disponíveis com suas descrições:

**Estrutura HTML:**

```html
<div class="relatorios-container">
  <div class="relatorio-item" data-categoria="geral">
    <div class="relatorio-cabecalho">
      <h2 class="relatorio-titulo">Vendas</h2>
    </div>
    <div class="relatorio-descricao">
      <p>
        Relatório que demonstra todas as vendas efetuadas em um período, tanto
        de pedidos, como notas fiscais. Permite agrupamentos e sub-agrupamentos
        por cliente, produto ou vendedor e o cálculo da lucratividade com base
        no custo ou última compra.
      </p>
    </div>
    <div class="relatorio-acoes">
      <a href="/relatorios/vendas" class="botao botao-secundario">
        <span class="icone icone-visualizar"></span>
        <span class="texto">Visualizar</span>
      </a>
    </div>
  </div>

  <div class="relatorio-item" data-categoria="geral">
    <div class="relatorio-cabecalho">
      <h2 class="relatorio-titulo">Relatório Financeiro de Vendas</h2>
    </div>
    <div class="relatorio-descricao">
      <p>
        Relatório de vendas, com base em pedidos ou notas fiscais, que demonstra
        os custos financeiros envolvidos em uma transação de venda (taxas e
        tarifas), meio de pagamento e forma de pagamento.
      </p>
    </div>
    <div class="relatorio-acoes">
      <a href="/relatorios/financeiro-vendas" class="botao botao-secundario">
        <span class="icone icone-visualizar"></span>
        <span class="texto">Visualizar</span>
      </a>
    </div>
  </div>

  <div class="relatorio-item" data-categoria="geral">
    <div class="relatorio-cabecalho">
      <h2 class="relatorio-titulo">Curva ABC</h2>
      <span class="relatorio-tag">Premium</span>
    </div>
    <div class="relatorio-descricao">
      <p>
        Relatório que mostra os clientes ou produtos com maior importância ou
        impacto no faturamento, baseando-se em quantidades e valores
      </p>
    </div>
    <div class="relatorio-acoes">
      <a href="/relatorios/curva-abc" class="botao botao-secundario">
        <span class="icone icone-visualizar"></span>
        <span class="texto">Visualizar</span>
      </a>
    </div>
  </div>

  <!-- Outros relatórios seriam listados aqui -->
</div>
```

**Estilos CSS:**

```css
.relatorios-container {
  padding: 24px;
  background-color: #f5f5f5;
  min-height: calc(100vh - 200px);
}

.relatorio-item {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 16px;
  overflow: hidden;
  transition: box-shadow 0.2s ease;
}

.relatorio-item:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.relatorio-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.relatorio-tag {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
  background-color: #f0f5ff;
  color: #1890ff;
}

.relatorio-descricao {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-descricao p {
  margin: 0;
  font-size: 14px;
  color: #666666;
  line-height: 1.5;
}

.relatorio-acoes {
  padding: 16px 24px;
  display: flex;
  justify-content: flex-end;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}
```

### Modal de Outros Relatórios

O modal para acessar outros relatórios é exibido ao clicar no botão "outros relatórios":

**Estrutura HTML:**

```html
<div class="modal-outros-relatorios">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Outros Relatórios</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <div class="pesquisa-container">
        <div class="campo-pesquisa">
          <input
            type="text"
            placeholder="Pesquisar relatório..."
            class="input-pesquisa"
          />
          <button class="botao-pesquisa">
            <span class="icone icone-pesquisa"></span>
          </button>
        </div>
      </div>

      <div class="categorias-modal">
        <h3 class="categorias-titulo">Categorias</h3>
        <div class="categorias-lista">
          <a
            href="#"
            class="categoria-modal-item categoria-modal-ativa"
            data-categoria="todos"
            >Todos</a
          >
          <a href="#" class="categoria-modal-item" data-categoria="vendas"
            >Vendas</a
          >
          <a href="#" class="categoria-modal-item" data-categoria="financeiro"
            >Financeiro</a
          >
          <a href="#" class="categoria-modal-item" data-categoria="estoque"
            >Estoque</a
          >
          <a href="#" class="categoria-modal-item" data-categoria="compras"
            >Compras</a
          >
          <a href="#" class="categoria-modal-item" data-categoria="fiscal"
            >Fiscal</a
          >
        </div>
      </div>

      <div class="relatorios-lista">
        <div class="relatorio-modal-item" data-categoria="vendas">
          <div class="relatorio-modal-info">
            <h4 class="relatorio-modal-titulo">
              Relatório de Vendas por Período
            </h4>
            <p class="relatorio-modal-descricao">
              Análise de vendas por período com gráficos e totalizadores
            </p>
          </div>
          <div class="relatorio-modal-acoes">
            <a
              href="/relatorios/vendas-periodo"
              class="botao botao-secundario botao-pequeno"
            >
              <span class="icone icone-visualizar"></span>
              <span class="texto">Acessar</span>
            </a>
          </div>
        </div>

        <div class="relatorio-modal-item" data-categoria="financeiro">
          <div class="relatorio-modal-info">
            <h4 class="relatorio-modal-titulo">Fluxo de Caixa</h4>
            <p class="relatorio-modal-descricao">
              Relatório de entradas e saídas financeiras
            </p>
          </div>
          <div class="relatorio-modal-acoes">
            <a
              href="/relatorios/fluxo-caixa"
              class="botao botao-secundario botao-pequeno"
            >
              <span class="icone icone-visualizar"></span>
              <span class="texto">Acessar</span>
            </a>
          </div>
        </div>

        <!-- Outros relatórios seriam listados aqui -->
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modal-outros-relatorios {
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

.modal-conteudo {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 800px;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.modal-titulo {
  margin: 0;
  font-size: 18px;
  font-weight: 500;
  color: #333333;
}

.botao-fechar {
  background: none;
  border: none;
  font-size: 20px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}

.pesquisa-container {
  margin-bottom: 24px;
}

.campo-pesquisa {
  position: relative;
}

.input-pesquisa {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.input-pesquisa:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #999999;
  cursor: pointer;
}

.categorias-modal {
  margin-bottom: 24px;
}

.categorias-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 12px 0;
}

.categorias-lista {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.categoria-modal-item {
  display: inline-block;
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  background-color: #f5f5f5;
}

.categoria-modal-item:hover {
  background-color: #e0e0e0;
}

.categoria-modal-ativa {
  background-color: #1890ff;
  color: white;
}

.relatorios-lista {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.relatorio-modal-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-radius: 4px;
  background-color: #f9f9f9;
  transition: background-color 0.2s ease;
}

.relatorio-modal-item:hover {
  background-color: #f0f0f0;
}

.relatorio-modal-info {
  flex: 1;
}

.relatorio-modal-titulo {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 4px 0;
}

.relatorio-modal-descricao {
  font-size: 12px;
  color: #666666;
  margin: 0;
}

.botao-pequeno {
  padding: 4px 12px;
  font-size: 12px;
}
```

### Tela de Visualização de Relatório

A tela de visualização de relatório é exibida ao clicar em um relatório:

**Estrutura HTML:**

```html
<div class="visualizacao-relatorio-container">
  <div class="visualizacao-cabecalho">
    <div class="titulo-container">
      <div class="breadcrumb">
        <a href="/inicio" class="breadcrumb-item">Início</a>
        <span class="breadcrumb-separador">/</span>
        <a href="/vendas" class="breadcrumb-item">Vendas</a>
        <span class="breadcrumb-separador">/</span>
        <a href="/relatorios" class="breadcrumb-item">Relatórios</a>
        <span class="breadcrumb-separador">/</span>
        <span class="breadcrumb-item breadcrumb-ativo">Vendas</span>
      </div>
      <h1 class="titulo-relatorio">Relatório de Vendas</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-exportar">
        <span class="icone icone-exportar"></span>
        <span class="texto">Exportar</span>
      </button>
      <button class="botao botao-secundario" id="btn-imprimir">
        <span class="icone icone-imprimir"></span>
        <span class="texto">Imprimir</span>
      </button>
    </div>
  </div>

  <div class="visualizacao-filtros">
    <div class="filtros-container">
      <div class="filtro-grupo">
        <label for="periodo" class="filtro-label">Período</label>
        <div class="filtro-periodo">
          <input type="date" id="data_inicial" class="filtro-input" value="2025-05-01">
          <span class="filtro-separador">até</span>
          <input type="date" id="data_final" class="filtro-input" value="2025-05-19">
        </div>
      </div>

      <div class="filtro-grupo">
        <label for="cliente" class="filtro-label">Cliente</label>
        <select id="cliente" class="filtro-select">
          <option value="">Todos</option>
          <option value="1">Cliente A</option>
          <option value="2">Cliente B</option>
          <option value="3">Cliente C</option>
        </select>
      </div>

      <div class="filtro-grupo">
        <label for="vendedor" class="filtro-label">Vendedor</label>
        <select id="vendedor" class="filtro-select">
          <option value="">Todos</option>
          <option value="1">Vendedor 1</option>
          <option value="2">Vendedor 2</option>
          <option value="3">Vendedor 3</option>
        </select>
      </div>

      <div class="filtro-grupo">
        <label for="agrupamento" class="filtro-label">Agrupar por</label>
        <select id="agrupamento" class="filtro-select">
          <option value="cliente">Cliente</option>
          <option value="produto">Produto</option>
          <option value="vendedor">Vendedor</option>
          <option value="data">Data</option>
        </select>
      </div>

      <div class="filtro-acoes">
        <button class="botao botao-primario" id="btn-aplicar-filtros">
          <span class="icone icone-filtrar"></span>
          <span class="texto">Aplicar</span>
        </button>
        <button class="botao botao-secundario" id="btn-limpar-filtros">
          <span cl
(Content truncated due to size limit. Use line ranges to read in chunks)
```
