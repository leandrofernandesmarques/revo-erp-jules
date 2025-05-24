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
          <input
            type="date"
            id="data_inicial"
            class="filtro-input"
            value="2025-05-01"
          />
          <span class="filtro-separador">até</span>
          <input
            type="date"
            id="data_final"
            class="filtro-input"
            value="2025-05-19"
          />
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
          <span class="icone icone-limpar"></span>
          <span class="texto">Limpar</span>
        </button>
      </div>
    </div>
  </div>

  <div class="visualizacao-conteudo">
    <div class="relatorio-resumo">
      <div class="resumo-card">
        <div class="resumo-titulo">Total de Vendas</div>
        <div class="resumo-valor">R$ 25.750,00</div>
        <div class="resumo-comparativo positivo">
          <span class="icone icone-crescimento"></span>
          <span class="texto">+15% vs. período anterior</span>
        </div>
      </div>

      <div class="resumo-card">
        <div class="resumo-titulo">Quantidade de Vendas</div>
        <div class="resumo-valor">42</div>
        <div class="resumo-comparativo positivo">
          <span class="icone icone-crescimento"></span>
          <span class="texto">+8% vs. período anterior</span>
        </div>
      </div>

      <div class="resumo-card">
        <div class="resumo-titulo">Ticket Médio</div>
        <div class="resumo-valor">R$ 613,10</div>
        <div class="resumo-comparativo positivo">
          <span class="icone icone-crescimento"></span>
          <span class="texto">+6% vs. período anterior</span>
        </div>
      </div>

      <div class="resumo-card">
        <div class="resumo-titulo">Lucratividade</div>
        <div class="resumo-valor">32%</div>
        <div class="resumo-comparativo negativo">
          <span class="icone icone-queda"></span>
          <span class="texto">-2% vs. período anterior</span>
        </div>
      </div>
    </div>

    <div class="relatorio-grafico">
      <div class="grafico-cabecalho">
        <h2 class="grafico-titulo">Vendas por Período</h2>
        <div class="grafico-controles">
          <button class="botao-grafico botao-grafico-ativo" data-periodo="dia">
            Dia
          </button>
          <button class="botao-grafico" data-periodo="semana">Semana</button>
          <button class="botao-grafico" data-periodo="mes">Mês</button>
        </div>
      </div>
      <div class="grafico-container">
        <canvas id="grafico-vendas" width="800" height="300"></canvas>
      </div>
    </div>

    <div class="relatorio-tabela">
      <div class="tabela-cabecalho">
        <h2 class="tabela-titulo">Detalhamento de Vendas</h2>
        <div class="tabela-controles">
          <div class="campo-pesquisa campo-pesquisa-pequeno">
            <input
              type="text"
              placeholder="Pesquisar..."
              class="input-pesquisa"
            />
            <button class="botao-pesquisa">
              <span class="icone icone-pesquisa"></span>
            </button>
          </div>
        </div>
      </div>
      <div class="tabela-container">
        <table class="tabela-dados">
          <thead>
            <tr>
              <th class="coluna-data">
                <div class="cabecalho-ordenavel">
                  <span class="texto">Data</span>
                  <span class="icone icone-ordenar"></span>
                </div>
              </th>
              <th class="coluna-cliente">
                <div class="cabecalho-ordenavel">
                  <span class="texto">Cliente</span>
                  <span class="icone icone-ordenar"></span>
                </div>
              </th>
              <th class="coluna-vendedor">
                <div class="cabecalho-ordenavel">
                  <span class="texto">Vendedor</span>
                  <span class="icone icone-ordenar"></span>
                </div>
              </th>
              <th class="coluna-documento">
                <div class="cabecalho-ordenavel">
                  <span class="texto">Documento</span>
                  <span class="icone icone-ordenar"></span>
                </div>
              </th>
              <th class="coluna-valor">
                <div class="cabecalho-ordenavel">
                  <span class="texto">Valor</span>
                  <span class="icone icone-ordenar"></span>
                </div>
              </th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="coluna-data">19/05/2025</td>
              <td class="coluna-cliente">Cliente A</td>
              <td class="coluna-vendedor">Vendedor 1</td>
              <td class="coluna-documento">NF-e 1001</td>
              <td class="coluna-valor">R$ 1.250,00</td>
              <td class="coluna-acoes">
                <button class="botao-acao" title="Visualizar">
                  <span class="icone icone-visualizar"></span>
                </button>
              </td>
            </tr>
            <tr>
              <td class="coluna-data">18/05/2025</td>
              <td class="coluna-cliente">Cliente B</td>
              <td class="coluna-vendedor">Vendedor 2</td>
              <td class="coluna-documento">NF-e 1000</td>
              <td class="coluna-valor">R$ 2.500,00</td>
              <td class="coluna-acoes">
                <button class="botao-acao" title="Visualizar">
                  <span class="icone icone-visualizar"></span>
                </button>
              </td>
            </tr>
            <tr>
              <td class="coluna-data">17/05/2025</td>
              <td class="coluna-cliente">Cliente C</td>
              <td class="coluna-vendedor">Vendedor 1</td>
              <td class="coluna-documento">NF-e 999</td>
              <td class="coluna-valor">R$ 1.800,00</td>
              <td class="coluna-acoes">
                <button class="botao-acao" title="Visualizar">
                  <span class="icone icone-visualizar"></span>
                </button>
              </td>
            </tr>
            <!-- Mais linhas seriam adicionadas aqui -->
          </tbody>
          <tfoot>
            <tr>
              <td colspan="4" class="rodape-label">Total:</td>
              <td class="rodape-valor">R$ 25.750,00</td>
              <td></td>
            </tr>
          </tfoot>
        </table>
      </div>

      <div class="paginacao">
        <div class="paginacao-info">
          <span class="texto">Exibindo 1-10 de 42 registros</span>
        </div>
        <div class="paginacao-controles">
          <button class="botao-paginacao" disabled>
            <span class="icone icone-primeira-pagina"></span>
          </button>
          <button class="botao-paginacao" disabled>
            <span class="icone icone-pagina-anterior"></span>
          </button>
          <span class="paginacao-pagina">Página 1 de 5</span>
          <button class="botao-paginacao">
            <span class="icone icone-proxima-pagina"></span>
          </button>
          <button class="botao-paginacao">
            <span class="icone icone-ultima-pagina"></span>
          </button>
        </div>
        <div class="paginacao-por-pagina">
          <span class="texto">Itens por página:</span>
          <select class="select-por-pagina">
            <option value="10">10</option>
            <option value="25">25</option>
            <option value="50">50</option>
            <option value="100">100</option>
          </select>
        </div>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.visualizacao-relatorio-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-color: #f5f5f5;
}

.visualizacao-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.titulo-relatorio {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.visualizacao-filtros {
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  padding: 16px 24px;
}

.filtros-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  align-items: flex-end;
}

.filtro-grupo {
  flex: 1;
  min-width: 200px;
}

.filtro-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.filtro-input,
.filtro-select {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.filtro-input:focus,
.filtro-select:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.filtro-periodo {
  display: flex;
  align-items: center;
  gap: 8px;
}

.filtro-separador {
  font-size: 14px;
  color: #666666;
}

.filtro-acoes {
  display: flex;
  gap: 8px;
}

.visualizacao-conteudo {
  flex: 1;
  padding: 24px;
  overflow: auto;
}

.relatorio-resumo {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 16px;
  margin-bottom: 24px;
}

.resumo-card {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  padding: 16px;
}

.resumo-titulo {
  font-size: 14px;
  color: #666666;
  margin-bottom: 8px;
}

.resumo-valor {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.resumo-comparativo {
  display: flex;
  align-items: center;
  font-size: 12px;
}

.resumo-comparativo.positivo {
  color: #52c41a;
}

.resumo-comparativo.negativo {
  color: #f5222d;
}

.resumo-comparativo .icone {
  margin-right: 4px;
}

.relatorio-grafico {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
  overflow: hidden;
}

.grafico-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.grafico-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.grafico-controles {
  display: flex;
  gap: 8px;
}

.botao-grafico {
  padding: 4px 12px;
  border-radius: 4px;
  font-size: 12px;
  background-color: #f5f5f5;
  border: none;
  color: #666666;
  cursor: pointer;
}

.botao-grafico-ativo {
  background-color: #1890ff;
  color: white;
}

.grafico-container {
  padding: 16px;
}

.relatorio-tabela {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.tabela-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.campo-pesquisa-pequeno {
  width: 250px;
}

.tabela-container {
  overflow-x: auto;
}

.tabela-dados {
  width: 100%;
  border-collapse: collapse;
}

.tabela-dados th,
.tabela-dados td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-dados th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-dados tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-data,
.coluna-documento {
  width: 120px;
}

.coluna-vendedor {
  width: 150px;
}

.coluna-valor {
  width: 120px;
  text-align: right;
}

.coluna-acoes {
  width: 60px;
  text-align: center;
}

.cabecalho-ordenavel {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-ordenavel .icone {
  margin-left: 4px;
  font-size: 12px;
  opacity: 0.5;
}

.cabecalho-ordenavel:hover .icone {
  opacity: 1;
}

.botao-acao {
  background: none;
  border: none;
  color: #1890ff;
  cursor: pointer;
  padding: 4px;
  border-radius: 4px;
}

.botao-acao:hover {
  background-color: #f0f5ff;
}

.rodape-label {
  text-align: right;
  font-weight: 500;
  color: #666666;
}

.rodape-valor {
  text-align: right;
  font-weight: 500;
  color: #333333;
}

.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
}

.paginacao-info,
.paginacao-pagina {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
  gap: 8px;
}

.botao-paginacao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: white;
  color: #666666;
  cursor: pointer;
}

.botao-paginacao:hover:not(:disabled) {
  background-color: #f5f5f5;
}

.botao-paginacao:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.paginacao-por-pagina {
  display: flex;
  align-items: center;
  gap: 8px;
}

.paginacao-por-pagina .texto {
  font-size: 14px;
  color: #666666;
}

.select-por-pagina {
  padding: 4px 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}
```

## Interações JavaScript

### Filtro de Categorias

```javascript
// Código para filtro de categorias
document.querySelectorAll(".categoria-item").forEach((categoria) => {
  categoria.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove a classe ativa de todas as categorias
    document.querySelectorAll(".categoria-item").forEach((cat) => {
      cat.classList.remove("categoria-ativa");
    });

    // Adiciona a classe ativa na categoria clicada
    this.classList.add("categoria-ativa");

    // Obtém a categoria selecionada
    const categoriaSelecionada = this.getAttribute("data-categoria");

    // Filtra os relatórios
    filtrarRelatorios(categoriaSelecionada);
  });
});

function filtrarRelatorios(categoria) {
  // Obtém todos os relatórios
  const relatorios = document.querySelectorAll(".relatorio-item");

  // Mostra ou esconde os relatórios de acordo com a categoria
  relatorios.forEach((relatorio) => {
    const categoriaRelatorio = relatorio.getAttribute("data-categoria");

    if (categoria === "geral" || categoriaRelatorio === categoria) {
      relatorio.style.display = "block";
    } else {
      relatorio.style.display = "none";
    }
  });
}
```

### Modal de Outros Relatórios

```javascript
// Código para modal de outros relatórios
document
  .querySelector("#btn-outros-relatorios")
  .addEventListener("click", function () {
    // Cria o modal
    const modal = document.createElement("div");
    modal.classList.add("modal-outros-relatorios");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Outros Relatórios</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="pesquisa-container">
          <div class="campo-pesquisa">
            <input type="text" placeholder="Pesquisar relatório..." class="input-pesquisa">
            <button class="botao-pesquisa">
              <span class="icone icone-pesquisa"></span>
            </button>
          </div>
        </div>
        
        <div class="categorias-modal">
          <h3 class="categorias-titulo">Categorias</h3>
          <div class="categorias-lista">
            <a href="#" class="categoria-modal-item categoria-modal-ativa" data-categoria="todos">Todos</a>
            <a href="#" class="categoria-modal-item" data-categoria="vendas">Vendas</a>
            <a href="#" class="categoria-modal-item" data-categoria="financeiro">Financeiro</a>
            <a href="#" class="categoria-modal-item" data-categoria="estoque">Estoque</a>
            <a href="#" class="categoria-modal-item" data-categoria="compras">Compras</a>
            <a href="#" class="categoria-modal-item" data-categoria="fiscal">Fiscal</a>
          </div>
        </div>
        
        <div class="relatorios-lista">
          <div class="relatorio-modal-item" data-categoria="vendas">
            <div class="relatorio-modal-info">
              <h4 class="relatorio-modal-titulo">Relatório de Vendas por Período</h4>
              <p class="relatorio-modal-descricao">Análise de vendas por período com gráficos e totalizadores</p>
            </div>
            <div class="relatorio-modal-acoes">
              <a href="/relatorios/vendas-periodo" class="botao botao-secundario botao-pequeno">
                <span class="icone icone-visualizar"></span>
                <span class="texto">Acessar</span>
              </a>
            </div>
          </div>
          
          <div class="relatorio-modal-item" data-categoria="financeiro">
            <div class="relatorio-modal-info">
              <h4 class="relatorio-modal-titulo">Fluxo de Caixa</h4>
              <p class="relatorio-modal-descricao">Relatório de entradas e saídas financeiras</p>
            </div>
            <div class="relatorio-modal-acoes">
              <a href="/relatorios/fluxo-caixa" class="botao botao-secundario botao-pequeno">
                <span class="icone icone-visualizar"></span>
                <span class="texto">Acessar</span>
              </a>
            </div>
          </div>
          
          <div class="relatorio-modal-item" data-categoria="estoque">
            <div class="relatorio-modal-info">
              <h4 class="relatorio-modal-titulo">Posição de Estoque</h4>
              <p class="relatorio-modal-descricao">Relatório de posição atual de estoque</p>
            </div>
            <div class="relatorio-modal-acoes">
              <a href="/relatorios/posicao-estoque" class="botao botao-secundario botao-pequeno">
                <span class="icone icone-visualizar"></span>
                <span class="texto">Acessar</span>
              </a>
            </div>
          </div>
          
          <div class="relatorio-modal-item" data-categoria="compras">
            <div class="relatorio-modal-info">
              <h4 class="relatorio-modal-titulo">Compras por Fornecedor</h4>
              <p class="relatorio-modal-descricao">Relatório de compras agrupadas por fornecedor</p>
            </div>
            <div class="relatorio-modal-acoes">
              <a href="/relatorios/compras-fornecedor" class="botao botao-secundario botao-pequeno">
                <span class="icone icone-visualizar"></span>
                <span class="texto">Acessar</span>
              </a>
            </div>
          </div>
          
          <div class="relatorio-modal-item" data-categoria="fiscal">
            <div class="relatorio-modal-info">
              <h4 class="relatorio-modal-titulo">Apuração de Impostos</h4>
              <p class="relatorio-modal-descricao">Relatório de apuração de impostos</p>
            </div>
            <div class="relatorio-modal-acoes">
              <a href="/relatorios/apuracao-impostos" class="botao botao-secundario botao-pequeno">
                <span class="icone icone-visualizar"></span>
                <span class="texto">Acessar</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    // Filtro de categorias
    modal.querySelectorAll(".categoria-modal-item").forEach((categoria) => {
      categoria.addEventListener("click", function (e) {
        e.preventDefault();

        // Remove a classe ativa de todas as categorias
        modal.querySelectorAll(".categoria-modal-item").forEach((cat) => {
          cat.classList.remove("categoria-modal-ativa");
        });

        // Adiciona a classe ativa na categoria clicada
        this.classList.add("categoria-modal-ativa");

        // Obtém a categoria selecionada
        const categoriaSelecionada = this.getAttribute("data-categoria");

        // Filtra os relatórios
        filtrarRelatoriosModal(modal, categoriaSelecionada);
      });
    });

    // Pesquisa de relatórios
    modal
      .querySelector(".botao-pesquisa")
      .addEventListener("click", function () {
        const termoPesquisa = modal
          .querySelector(".input-pesquisa")
          .value.toLowerCase();
        pesquisarRelatoriosModal(modal, termoPesquisa);
      });

    modal
      .querySelector(".input-pesquisa")
      .addEventListener("keydown", function (e) {
        if (e.key === "Enter") {
          const termoPesquisa = this.value.toLowerCase();
          pesquisarRelatoriosModal(modal, termoPesquisa);
        }
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

function filtrarRelatoriosModal(modal, categoria) {
  // Obtém todos os relatórios
  const relatorios = modal.querySelectorAll(".relatorio-modal-item");

  // Mostra ou esconde os relatórios de acordo com a categoria
  relatorios.forEach((relatorio) => {
    const categoriaRelatorio = relatorio.getAttribute("data-categoria");

    if (categoria === "todos" || categoriaRelatorio === categoria) {
      relatorio.style.display = "flex";
    } else {
      relatorio.style.display = "none";
    }
  });
}

function pesquisarRelatoriosModal(modal, termo) {
  // Obtém todos os relatórios
  const relatorios = modal.querySelectorAll(".relatorio-modal-item");

  // Mostra ou esconde os relatórios de acordo com o termo de pesquisa
  relatorios.forEach((relatorio) => {
    const titulo = relatorio
      .querySelector(".relatorio-modal-titulo")
      .textContent.toLowerCase();
    const descricao = relatorio
      .querySelector(".relatorio-modal-descricao")
      .textContent.toLowerCase();

    if (titulo.includes(termo) || descricao.includes(termo)) {
      relatorio.style.display = "flex";
    } else {
      relatorio.style.display = "none";
    }
  });
}
```

### Visualização de Relatório

```javascript
// Código para visualização de relatório
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de visualização de relatório
  const visualizacaoRelatorio = document.querySelector(
    ".visualizacao-relatorio-container"
  );
  if (!visualizacaoRelatorio) return;

  // Inicializa o gráfico
  inicializarGrafico();

  // Adiciona eventos aos botões de controle do gráfico
  document.querySelectorAll(".botao-grafico").forEach((botao) => {
    botao.addEventListener("click", function () {
      // Remove a classe ativa de todos os botões
      document.querySelectorAll(".botao-grafico").forEach((b) => {
        b.classList.remove("botao-grafico-ativo");
      });

      // Adiciona a classe ativa no botão clicado
      this.classList.add("botao-grafico-ativo");

      // Atualiza o gráfico
      const periodo = this.getAttribute("data-periodo");
      atualizarGrafico(periodo);
    });
  });

  // Adiciona eventos aos botões de exportar e imprimir
  document
    .querySelector("#btn-exportar")
    .addEventListener("click", function () {
      exportarRelatorio();
    });

  document
    .querySelector("#btn-imprimir")
    .addEventListener("click", function () {
      imprimirRelatorio();
    });

  // Adiciona eventos aos botões de filtro
  document
    .querySelector("#btn-aplicar-filtros")
    .addEventListener("click", function () {
      aplicarFiltros();
    });

  document
    .querySelector("#btn-limpar-filtros")
    .addEventListener("click", function () {
      limparFiltros();
    });

  // Adiciona eventos aos botões de ordenação
  document.querySelectorAll(".cabecalho-ordenavel").forEach((cabecalho) => {
    cabecalho.addEventListener("click", function () {
      const coluna = this.closest("th").className.replace("coluna-", "");
      ordenarTabela(coluna);
    });
  });

  // Adiciona eventos aos botões de paginação
  document.querySelectorAll(".botao-paginacao").forEach((botao) => {
    if (botao.disabled) return;

    botao.addEventListener("click", function () {
      const icone = this.querySelector(".icone");

      if (icone.classList.contains("icone-primeira-pagina")) {
        irParaPagina(1);
      } else if (icone.classList.contains("icone-pagina-anterior")) {
        irParaPaginaAnterior();
      } else if (icone.classList.contains("icone-proxima-pagina")) {
        irParaProximaPagina();
      } else if (icone.classList.contains("icone-ultima-pagina")) {
        irParaUltimaPagina();
      }
    });
  });

  // Adiciona evento ao seletor de itens por página
  document
    .querySelector(".select-por-pagina")
    .addEventListener("change", function () {
      const itensPorPagina = parseInt(this.value);
      alterarItensPorPagina(itensPorPagina);
    });

  // Adiciona eventos aos botões de visualização de detalhes
  document.querySelectorAll(".botao-acao").forEach((botao) => {
    botao.addEventListener("click", function () {
      const linha = this.closest("tr");
      const documento = linha.querySelector(".coluna-documento").textContent;
      visualizarDetalhes(documento);
    });
  });
});

function inicializarGrafico() {
  // Simulação de inicialização de gráfico
  console.log("Inicializando gráfico...");

  // Aqui seria utilizada uma biblioteca como Chart.js
  // const ctx = document.getElementById('grafico-vendas').getContext('2d');
  // const grafico = new Chart(ctx, {
  //   type: 'line',
  //   data: {
  //     labels: ['01/05', '02/05', '03/05', '04/05', '05/05', '06/05', '07/05', '08/05', '09/05', '10/05', '11/05', '12/05', '13/05', '14/05', '15/05', '16/05', '17/05', '18/05', '19/05'],
  //     datasets: [{
  //       label: 'Vendas',
  //       data: [1200, 1500, 1000, 1800, 2000, 1700, 1900, 2100, 2300, 2000, 1800, 1600, 1900, 2200, 2400, 2100, 1800, 2500, 1250],
  //       backgroundColor: 'rgba(24, 144, 255, 0.2)',
  //       borderColor: 'rgba(24, 144, 255, 1)',
  //       borderWidth: 2,
  //       pointBackgroundColor: 'rgba(24, 144, 255, 1)',
  //       pointBorderColor: '#fff',
  //       pointBorderWidth: 2,
  //       pointRadius: 4,
  //       tension: 0.4
  //     }]
  //   },
  //   options: {
  //     responsive: true,
  //     maintainAspectRatio: false,
  //     scales: {
  //       y: {
  //         beginAtZero: true,
  //         grid: {
  //           color: 'rgba(0, 0, 0, 0.05)'
  //         }
  //       },
  //       x: {
  //         grid: {
  //           display: false
  //         }
  //       }
  //     },
  //     plugins: {
  //       legend: {
  //         display: false
  //       },
  //       tooltip: {
  //         backgroundColor: 'rgba(0, 0, 0, 0.7)',
  //         padding: 10,
  //         titleFont: {
  //           size: 14
  //         },
  //         bodyFont: {
  //           size: 14
  //         },
  //         callbacks: {
  //           label: function(context) {
  //             return `R$ ${context.raw.toFixed(2)}`;
  //           }
  //         }
  //       }
  //     }
  //   }
  // });
}

function atualizarGrafico(periodo) {
  // Simulação de atualização de gráfico
  console.log(`Atualizando gráfico para período: ${periodo}`);

  // Aqui seria atualizado o gráfico com novos dados
  // const dados = obterDadosPorPeriodo(periodo);
  // grafico.data.labels = dados.labels;
  // grafico.data.datasets[0].data = dados.valores;
  // grafico.update();
}

function exportarRelatorio() {
  // Simulação de exportação de relatório
  console.log("Exportando relatório...");

  // Cria o modal de exportação
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Exportar Relatório</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label class="form-label">Formato:</label>
          <div class="opcoes-exportacao">
            <label class="opcao-exportacao">
              <input type="radio" name="formato" value="pdf" checked>
              <span class="opcao-texto">PDF</span>
            </label>
            <label class="opcao-exportacao">
              <input type="radio" name="formato" value="excel">
              <span class="opcao-texto">Excel</span>
            </label>
            <label class="opcao-exportacao">
              <input type="radio" name="formato" value="csv">
              <span class="opcao-texto">CSV</span>
            </label>
          </div>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Conteúdo:</label>
          <div class="opcoes-exportacao">
            <label class="opcao-exportacao">
              <input type="checkbox" name="conteudo" value="resumo" checked>
              <span class="opcao-texto">Resumo</span>
            </label>
            <label class="opcao-exportacao">
              <input type="checkbox" name="conteudo" value="grafico" checked>
              <span class="opcao-texto">Gráfico</span>
            </label>
            <label class="opcao-exportacao">
              <input type="checkbox" name="conteudo" value="tabela" checked>
              <span class="opcao-texto">Tabela de Dados</span>
            </label>
          </div>
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-confirmar-exportacao">
            <span class="icone icone-exportar"></span>
            <span class="texto">Exportar</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-exportacao">
            <span class="texto">Cancelar</span>
          </button>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-exportacao")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  modal
    .querySelector("#btn-confirmar-exportacao")
    .addEventListener("click", function () {
      const formato = modal.querySelector(
        'input[name="formato"]:checked'
      ).value;
      const conteudo = Array.from(
        modal.querySelectorAll('input[name="conteudo"]:checked')
      ).map((input) => input.value);

      console.log(
        `Exportando relatório em formato ${formato} com conteúdo: ${conteudo.join(
          ", "
        )}`
      );

      // Simulação de download
      setTimeout(() => {
        alert(`Relatório exportado com sucesso em formato ${formato}!`);
        document.body.removeChild(modal);
      }, 1000);
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}

function imprimirRelatorio() {
  // Simulação de impressão de relatório
  console.log("Imprimindo relatório...");

  // Aqui seria utilizada a API de impressão do navegador
  // window.print();

  // Simulação de impressão
  alert("Relatório enviado para impressão!");
}

function aplicarFiltros() {
  // Simulação de aplicação de filtros
  const dataInicial = document.querySelector("#data_inicial").value;
  const dataFinal = document.querySelector("#data_final").value;
  const cliente = document.querySelector("#cliente").value;
  const vendedor = document.querySelector("#vendedor").value;
  const agrupamento = document.querySelector("#agrupamento").value;

  console.log(
    `Aplicando filtros: Data inicial=${dataInicial}, Data final=${dataFinal}, Cliente=${cliente}, Vendedor=${vendedor}, Agrupamento=${agrupamento}`
  );

  // Aqui seria feita uma requisição para a API
  // fetch('/api/relatorios/vendas', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({
  //     data_inicial: dataInicial,
  //     data_final: dataFinal,
  //     cliente,
  //     vendedor,
  //     agrupamento
  //   })
  // })
  // .then(response => response.json())
  // .then(data => {
  //   atualizarRelatorio(data);
  // });

  // Simulação de atualização
  alert("Filtros aplicados com sucesso!");
}

function limparFiltros() {
  // Simulação de limpeza de filtros
  console.log("Limpando filtros...");

  // Define valores padrão
  const hoje = new Date();
  const primeiroDiaMes = new Date(hoje.getFullYear(), hoje.getMonth(), 1);

  document.querySelector("#data_inicial").value = primeiroDiaMes
    .toISOString()
    .split("T")[0];
  document.querySelector("#data_final").value = hoje
    .toISOString()
    .split("T")[0];
  document.querySelector("#cliente").value = "";
  document.querySelector("#vendedor").value = "";
  document.querySelector("#agrupamento").value = "cliente";

  // Aplica os filtros
  aplicarFiltros();
}

function ordenarTabela(coluna) {
  // Simulação de ordenação de tabela
  console.log(`Ordenando tabela pela coluna: ${coluna}`);

  // Aqui seria implementada a lógica de ordenação
  // const tabela = document.querySelector('.tabela-dados');
  // const linhas = Array.from(tabela.querySelectorAll('tbody tr'));
  // const direcao = obterDirecaoOrdenacao(coluna);
  //
  // linhas.sort((a, b) => {
  //   const valorA = a.querySelector(`.coluna-${coluna}`).textContent;
  //   const valorB = b.querySelector(`.coluna-${coluna}`).textContent;
  //
  //   if (coluna === 'valor') {
  //     return direcao * (parseFloat(valorA.replace('R$ ', '').replace('.', '').replace(',', '.')) - parseFloat(valorB.replace('R$ ', '').replace('.', '').replace(',', '.')));
  //   } else if (coluna === 'data') {
  //     return direcao * (new Date(valorA.split('/').reverse().join('-')) - new Date(valorB.split('/').reverse().join('-')));
  //   } else {
  //     return direcao * valorA.localeCompare(valorB);
  //   }
  // });
  //
  // const tbody = tabela.querySelector('tbody');
  // tbody.innerHTML = '';
  // linhas.forEach(linha => tbody.appendChild(linha));
}

function irParaPagina(pagina) {
  // Simulação de navegação para página específica
  console.log(`Indo para página: ${pagina}`);

  // Aqui seria implementada a lógica de paginação
  // carregarPagina(pagina);
}

function irParaPaginaAnterior() {
  // Simulação de navegação para página anterior
  console.log("Indo para página anterior");

  // Aqui seria implementada a lógica de paginação
  // const paginaAtual = obterPaginaAtual();
  // if (paginaAtual > 1) {
  //   carregarPagina(paginaAtual - 1);
  // }
}

function irParaProximaPagina() {
  // Simulação de navegação para próxima página
  console.log("Indo para próxima página");

  // Aqui seria implementada a lógica de paginação
  // const paginaAtual = obterPaginaAtual();
  // const totalPaginas = obterTotalPaginas();
  // if (paginaAtual < totalPaginas) {
  //   carregarPagina(paginaAtual + 1);
  // }
}

function irParaUltimaPagina() {
  // Simulação de navegação para última página
  console.log("Indo para última página");

  // Aqui seria implementada a lógica de paginação
  // const totalPaginas = obterTotalPaginas();
  // carregarPagina(totalPaginas);
}

function alterarItensPorPagina(itensPorPagina) {
  // Simulação de alteração de itens por página
  console.log(`Alterando itens por página para: ${itensPorPagina}`);

  // Aqui seria implementada a lógica de paginação
  // definirItensPorPagina(itensPorPagina);
  // carregarPagina(1);
}

function visualizarDetalhes(documento) {
  // Simulação de visualização de detalhes
  console.log(`Visualizando detalhes do documento: ${documento}`);

  // Cria o modal de detalhes
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Detalhes da Venda - ${documento}</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="detalhes-secao">
          <h3 class="detalhes-titulo">Informações Gerais</h3>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Documento:</span>
              <span class="detalhes-valor">${documento}</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Data:</span>
              <span class="detalhes-valor">19/05/2025</span>
            </div>
          </div>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Cliente:</span>
              <span class="detalhes-valor">Cliente A</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Vendedor:</span>
              <span class="detalhes-valor">Vendedor 1</span>
            </div>
          </div>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Forma de Pagamento:</span>
              <span class="detalhes-valor">Cartão de Crédito</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Parcelas:</span>
              <span class="detalhes-valor">3x</span>
            </div>
          </div>
        </div>
        
        <div class="detalhes-secao">
          <h3 class="detalhes-titulo">Itens</h3>
          <div class="detalhes-tabela">
            <table class="tabela-itens">
              <thead>
                <tr>
                  <th>Produto</th>
                  <th>Quantidade</th>
                  <th>Valor Unitário</th>
                  <th>Desconto</th>
                  <th>Total</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Produto 1</td>
                  <td>2</td>
                  <td>R$ 500,00</td>
                  <td>R$ 0,00</td>
                  <td>R$ 1.000,00</td>
                </tr>
                <tr>
                  <td>Produto 2</td>
                  <td>1</td>
                  <td>R$ 250,00</td>
                  <td>R$ 0,00</td>
                  <td>R$ 250,00</td>
                </tr>
              </tbody>
              <tfoot>
                <tr>
                  <td colspan="4" class="rodape-label">Subtotal:</td>
                  <td class="rodape-valor">R$ 1.250,00</td>
                </tr>
                <tr>
                  <td colspan="4" class="rodape-label">Frete:</td>
                  <td class="rodape-valor">R$ 0,00</td>
                </tr>
                <tr>
                  <td colspan="4" class="rodape-label">Total:</td>
                  <td class="rodape-valor">R$ 1.250,00</td>
                </tr>
              </tfoot>
            </table>
          </div>
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-imprimir-detalhes">
            <span class="icone icone-imprimir"></span>
            <span class="texto">Imprimir</span>
          </button>
          <button class="botao botao-secundario" id="btn-fechar-detalhes">
            <span class="texto">Fechar</span>
          </button>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-fechar-detalhes")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  modal
    .querySelector("#btn-imprimir-detalhes")
    .addEventListener("click", function () {
      // Simulação de impressão
      alert(`Detalhes do documento ${documento} enviados para impressão!`);
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .relatorio-resumo {
    grid-template-columns: repeat(2, 1fr);
  }

  .filtros-container {
    flex-direction: column;
  }

  .filtro-grupo {
    width: 100%;
  }

  .filtro-acoes {
    align-self: flex-end;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .visualizacao-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-start;
  }

  .categorias-container {
    overflow-x: auto;
    padding-bottom: 8px;
  }

  .categoria-item {
    white-space: nowrap;
  }

  .relatorio-resumo {
    grid-template-columns: 1fr;
  }

  .coluna-vendedor {
    display: none;
  }

  .paginacao {
    flex-direction: column;
    gap: 12px;
    align-items: flex-start;
  }

  .paginacao-controles {
    order: -1;
    align-self: center;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .coluna-data {
    display: none;
  }

  .paginacao-pagina {
    display: none;
  }

  .grafico-controles {
    flex-direction: column;
    gap: 4px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Azul muito claro (background): #f0f5ff
- Verde (sucesso): #52c41a
- Verde claro (background sucesso): #f6ffed
- Vermelho (erro): #f5222d
- Vermelho claro (background erro): #fff1f0
- Amarelo (alerta): #faad14
- Amarelo claro (background alerta): #fffbe6
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 24px
  - Subtítulos: 18px
  - Títulos de seção: 16px
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

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao-pequeno {
  padding: 4px 12px;
  font-size: 12px;
}
```

### Campos de Formulário

```css
.filtro-input,
.filtro-select,
.input-pesquisa {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.filtro-input:focus,
.filtro-select:focus,
.input-pesquisa:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-pesquisa {
  position: relative;
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
```

### Modais

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

.modal-conteudo {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 600px;
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
```

### Tabelas

```css
.tabela-dados {
  width: 100%;
  border-collapse: collapse;
}

.tabela-dados th,
.tabela-dados td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-dados th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-dados tbody tr:hover {
  background-color: #f5f5f5;
}

.cabecalho-ordenavel {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-ordenavel .icone {
  margin-left: 4px;
  font-size: 12px;
  opacity: 0.5;
}

.cabecalho-ordenavel:hover .icone {
  opacity: 1;
}

.rodape-label {
  text-align: right;
  font-weight: 500;
  color: #666666;
}

.rodape-valor {
  text-align: right;
  font-weight: 500;
  color: #333333;
}
```

### Paginação

```css
.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
}

.paginacao-info,
.paginacao-pagina {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
  gap: 8px;
}

.botao-paginacao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: white;
  color: #666666;
  cursor: pointer;
}

.botao-paginacao:hover:not(:disabled) {
  background-color: #f5f5f5;
}

.botao-paginacao:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.paginacao-por-pagina {
  display: flex;
  align-items: center;
  gap: 8px;
}

.paginacao-por-pagina .texto {
  font-size: 14px;
  color: #666666;
}

.select-por-pagina {
  padding: 4px 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}
```

## Fluxos de Navegação

1. **Listagem de Relatórios**:

   - O usuário acessa o módulo "Relatórios" na seção de Vendas
   - Visualiza a lista de relatórios disponíveis
   - Pode filtrar por categoria usando as abas
   - Pode acessar outros relatórios clicando no botão "outros relatórios"

2. **Visualização de Relatório**:

   - O usuário clica em um relatório na lista
   - Visualiza o relatório com resumo, gráficos e tabela de dados
   - Pode aplicar filtros para personalizar o relatório
   - Pode exportar ou imprimir o relatório

3. **Exportação de Relatório**:

   - O usuário clica no botão "Exportar"
   - Seleciona o formato de exportação (PDF, Excel, CSV)
   - Seleciona o conteúdo a ser exportado
   - Confirma a exportação e recebe o arquivo

4. **Visualização de Detalhes**:
   - O usuário clica no botão de visualização de uma linha na tabela
   - Visualiza os detalhes da venda
   - Pode imprimir os detalhes

## Conclusão

O módulo "Relatórios" do ERP Revo na seção de Vendas apresenta uma interface completa e funcional para acesso e visualização de relatórios relacionados às operações de vendas. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, visualizar, exportar e imprimir relatórios de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para visualização e análise de dados de vendas, como gráficos, tabelas e filtros, atendendo às necessidades de negócios que precisam monitorar e analisar suas operações de vendas.
