# Análise do Módulo Caixa - ERP Revo

## Estrutura Geral

O módulo "Caixa" do ERP Revo apresenta uma interface para gerenciamento de fluxo de caixa e controle financeiro. A tela principal exibe um cabeçalho com título e ações, uma área de pesquisa e filtros, e uma visualização do saldo atual com listagem de lançamentos.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <div class="breadcrumb">
      <a href="/inicio" class="breadcrumb-item">Início</a>
      <span class="breadcrumb-separador">/</span>
      <a href="/financas" class="breadcrumb-item">Finanças</a>
      <span class="breadcrumb-separador">/</span>
      <span class="breadcrumb-item breadcrumb-ativo">Caixa</span>
    </div>
    <h1 class="titulo-modulo">Caixa e Bancos</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <button class="botao botao-secundario" id="btn-transferir">
      <span class="icone icone-transferir"></span>
      <span class="texto">Transferir</span>
    </button>
    <a
      href="/caixa/novo"
      class="botao botao-primario"
      id="btn-incluir-lancamento"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir lançamento</span>
    </a>
    <div class="dropdown">
      <button
        class="botao botao-secundario dropdown-toggle"
        id="btn-mais-acoes"
      >
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item" id="btn-exportar">Exportar</a>
        <a href="#" class="dropdown-item" id="btn-conciliar">Conciliar</a>
        <a href="#" class="dropdown-item" id="btn-configuracoes"
          >Configurações</a
        >
      </div>
    </div>
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

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao .icone {
  margin-right: 8px;
  font-size: 16px;
}

.dropdown {
  position: relative;
}

.dropdown-toggle {
  display: inline-flex;
  align-items: center;
}

.dropdown-toggle .icone-seta-baixo {
  margin-left: 8px;
  font-size: 12px;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 1000;
  display: none;
  min-width: 160px;
  padding: 8px 0;
  margin: 4px 0 0;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.dropdown:hover .dropdown-menu {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
}
```

### Área de Pesquisa e Filtros

A área de pesquisa e filtros permite buscar e filtrar lançamentos:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por cliente"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
    <button class="botao-filtro-avancado">
      <span class="icone icone-filtro-avancado"></span>
    </button>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link filtro-periodo">
      <span class="icone icone-calendario"></span>
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  gap: 8px;
  flex: 1;
  max-width: 500px;
}

.campo-pesquisa {
  position: relative;
  flex: 1;
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

.botao-filtro-avancado {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: white;
  color: #666666;
  cursor: pointer;
}

.botao-filtro-avancado:hover {
  background-color: #f5f5f5;
}

.filtros-container {
  display: flex;
  gap: 16px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
  padding: 6px 12px;
  border-radius: 4px;
  transition: background-color 0.2s ease;
}

.filtro-link:hover {
  background-color: #f0f5ff;
}

.filtro-periodo {
  background-color: #f0f5ff;
  border: 1px solid #d6e4ff;
}

.filtro-link .icone {
  margin-right: 8px;
}
```

### Banner de Conta Digital

O banner promocional para a conta digital:

**Estrutura HTML:**

```html
<div class="banner-conta-digital">
  <div class="banner-conteudo">
    <div class="banner-texto">
      <span class="banner-titulo">Conheça a nova conta digital do Revo!</span>
      <a href="#" class="banner-link">Saiba mais clicando aqui</a>
    </div>
    <div class="banner-imagem">
      <img src="/assets/images/banner-conta-digital.png" alt="Conta Digital" />
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.banner-conta-digital {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.banner-conteudo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f9f9f9;
  border-radius: 8px;
  padding: 12px 16px;
}

.banner-texto {
  display: flex;
  align-items: center;
  gap: 16px;
}

.banner-titulo {
  font-size: 14px;
  color: #333333;
}

.banner-link {
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
}

.banner-link:hover {
  text-decoration: underline;
}

.banner-imagem img {
  height: 32px;
  width: auto;
}
```

### Resumo de Saldo

A área de resumo de saldo exibe o saldo atual:

**Estrutura HTML:**

```html
<div class="resumo-saldo-container">
  <div class="saldo-card">
    <div class="saldo-icone">
      <span class="icone icone-caixa"></span>
    </div>
    <div class="saldo-info">
      <div class="saldo-titulo">Caixa</div>
      <div class="saldo-valor">119,65</div>
      <div class="saldo-descricao">saldo atual (R$)</div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.resumo-saldo-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.saldo-card {
  display: flex;
  align-items: center;
  gap: 16px;
  background-color: #fffbe6;
  border: 1px solid #ffe58f;
  border-radius: 8px;
  padding: 16px;
  width: fit-content;
}

.saldo-icone {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background-color: #faad14;
  border-radius: 8px;
  color: white;
}

.saldo-icone .icone {
  font-size: 24px;
}

.saldo-info {
  display: flex;
  flex-direction: column;
}

.saldo-titulo {
  font-size: 14px;
  color: #666666;
  margin-bottom: 4px;
}

.saldo-valor {
  font-size: 20px;
  font-weight: 500;
  color: #333333;
}

.saldo-descricao {
  font-size: 12px;
  color: #999999;
}
```

### Área de Conteúdo

A área de conteúdo exibe a lista de lançamentos ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <h2 class="titulo-vazio">Sua pesquisa não retornou resultados.</h2>
      <p class="texto-vazio">
        Tente outras opções de pesquisa, períodos ou remova os filtros.
      </p>
    </div>

    <div class="ilustracao-vazio">
      <img
        src="/assets/images/ilustracao-vazio.svg"
        alt="Nenhum resultado encontrado"
      />
    </div>

    <div class="acoes-vazio">
      <button class="botao botao-primario" id="btn-alterar-pesquisa">
        <span class="texto">alterar pesquisa</span>
      </button>
      <button class="botao botao-secundario" id="btn-limpar-filtros">
        <span class="texto">limpar filtros</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  flex: 1;
  padding: 24px;
  background-color: #f5f5f5;
  overflow: auto;
}

.conteudo-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 600px;
  margin: 0 auto;
  padding: 32px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.mensagem-vazio {
  text-align: center;
  margin-bottom: 24px;
}

.titulo-vazio {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.texto-vazio {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.ilustracao-vazio {
  margin-bottom: 24px;
}

.ilustracao-vazio img {
  max-width: 100%;
  height: auto;
  max-height: 200px;
}

.acoes-vazio {
  display: flex;
  gap: 16px;
}
```

### Tabela de Lançamentos

Quando houver lançamentos, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-lancamentos">
      <thead>
        <tr>
          <th class="coluna-data">
            <div class="cabecalho-ordenavel">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-descricao">
            <div class="cabecalho-ordenavel">
              <span class="texto">Descrição</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-cliente">
            <div class="cabecalho-ordenavel">
              <span class="texto">Cliente/Fornecedor</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-categoria">
            <div class="cabecalho-ordenavel">
              <span class="texto">Categoria</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-entrada">
            <div class="cabecalho-ordenavel">
              <span class="texto">Entrada</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saida">
            <div class="cabecalho-ordenavel">
              <span class="texto">Saída</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saldo">
            <div class="cabecalho-ordenavel">
              <span class="texto">Saldo</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="coluna-data">19/05/2025</td>
          <td class="coluna-descricao">Venda à vista</td>
          <td class="coluna-cliente">Cliente A</td>
          <td class="coluna-categoria">Vendas</td>
          <td class="coluna-entrada">R$ 150,00</td>
          <td class="coluna-saida">-</td>
          <td class="coluna-saldo">R$ 150,00</td>
          <td class="coluna-acoes">
            <button class="botao-acao" title="Editar">
              <span class="icone icone-editar"></span>
            </button>
            <button class="botao-acao" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr>
          <td class="coluna-data">18/05/2025</td>
          <td class="coluna-descricao">Pagamento de fornecedor</td>
          <td class="coluna-cliente">Fornecedor B</td>
          <td class="coluna-categoria">Compras</td>
          <td class="coluna-entrada">-</td>
          <td class="coluna-saida">R$ 80,00</td>
          <td class="coluna-saldo">R$ 70,00</td>
          <td class="coluna-acoes">
            <button class="botao-acao" title="Editar">
              <span class="icone icone-editar"></span>
            </button>
            <button class="botao-acao" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr>
          <td class="coluna-data">17/05/2025</td>
          <td class="coluna-descricao">Saldo inicial</td>
          <td class="coluna-cliente">-</td>
          <td class="coluna-categoria">Saldo Inicial</td>
          <td class="coluna-entrada">R$ 150,00</td>
          <td class="coluna-saida">-</td>
          <td class="coluna-saldo">R$ 150,00</td>
          <td class="coluna-acoes">
            <button class="botao-acao" title="Editar">
              <span class="icone icone-editar"></span>
            </button>
            <button class="botao-acao" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td colspan="4" class="rodape-label">Total:</td>
          <td class="rodape-valor">R$ 300,00</td>
          <td class="rodape-valor">R$ 80,00</td>
          <td class="rodape-valor">R$ 220,00</td>
          <td></td>
        </tr>
      </tfoot>
    </table>

    <div class="paginacao">
      <div class="paginacao-info">
        <span class="texto">Exibindo 1-3 de 3 registros</span>
      </div>
      <div class="paginacao-controles">
        <button class="botao-paginacao" disabled>
          <span class="icone icone-primeira-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-pagina-anterior"></span>
        </button>
        <span class="paginacao-pagina">Página 1 de 1</span>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-proxima-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-ultima-pagina"></span>
        </button>
      </div>
      <div class="paginacao-por-pagina">
        <span class="texto"
          >Itens por (Content truncated due to size limit. Use line ranges to
          read in chunks)</span
        >
      </div>
    </div>
  </div>
</div>
```
