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
```

**Estilos CSS:**

```css
.conteudo-tabela {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.tabela-lancamentos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-lancamentos th,
.tabela-lancamentos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-lancamentos th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-lancamentos tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-data {
  width: 100px;
}

.coluna-categoria {
  width: 150px;
}

.coluna-entrada,
.coluna-saida,
.coluna-saldo {
  width: 120px;
  text-align: right;
}

.coluna-acoes {
  width: 80px;
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

## Formulário de Inclusão/Edição de Lançamento

O formulário para incluir ou editar lançamentos é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-lancamento-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <div class="breadcrumb">
        <a href="/inicio" class="breadcrumb-item">Início</a>
        <span class="breadcrumb-separador">/</span>
        <a href="/financas" class="breadcrumb-item">Finanças</a>
        <span class="breadcrumb-separador">/</span>
        <a href="/caixa" class="breadcrumb-item">Caixa</a>
        <span class="breadcrumb-separador">/</span>
        <span class="breadcrumb-item breadcrumb-ativo">Novo Lançamento</span>
      </div>
      <h1 class="titulo-formulario">Novo Lançamento</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-cancelar">
        <span class="icone icone-cancelar"></span>
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao botao-primario" id="btn-salvar">
        <span class="icone icone-salvar"></span>
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <div class="formulario-secao">
      <h2 class="secao-titulo">Informações Gerais</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="tipo_lancamento" class="formulario-label"
            >Tipo de Lançamento</label
          >
          <div class="radio-grupo">
            <label class="radio-opcao">
              <input
                type="radio"
                name="tipo_lancamento"
                value="entrada"
                checked
              />
              <span class="radio-texto">Entrada</span>
            </label>
            <label class="radio-opcao">
              <input type="radio" name="tipo_lancamento" value="saida" />
              <span class="radio-texto">Saída</span>
            </label>
            <label class="radio-opcao">
              <input
                type="radio"
                name="tipo_lancamento"
                value="transferencia"
              />
              <span class="radio-texto">Transferência</span>
            </label>
          </div>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="data_lancamento" class="formulario-label">Data</label>
          <input
            type="date"
            id="data_lancamento"
            class="formulario-input"
            required
          />
        </div>

        <div class="formulario-grupo">
          <label for="valor" class="formulario-label">Valor</label>
          <div class="input-prefixo">
            <span class="prefixo">R$</span>
            <input
              type="text"
              id="valor"
              class="formulario-input"
              placeholder="0,00"
              required
            />
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="conta" class="formulario-label">Conta</label>
          <select id="conta" class="formulario-select" required>
            <option value="caixa">Caixa</option>
            <option value="banco">Banco</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="descricao" class="formulario-label">Descrição</label>
          <input type="text" id="descricao" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="categoria" class="formulario-label">Categoria</label>
          <select id="categoria" class="formulario-select" required>
            <option value="">Selecione...</option>
            <option value="vendas">Vendas</option>
            <option value="compras">Compras</option>
            <option value="despesas">Despesas</option>
            <option value="receitas">Receitas</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="cliente_fornecedor" class="formulario-label"
            >Cliente/Fornecedor</label
          >
          <div class="campo-busca">
            <input
              type="text"
              id="cliente_fornecedor"
              class="formulario-input"
              placeholder="Buscar cliente ou fornecedor..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="forma_pagamento" class="formulario-label"
            >Forma de Pagamento</label
          >
          <select id="forma_pagamento" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="dinheiro">Dinheiro</option>
            <option value="cartao_credito">Cartão de Crédito</option>
            <option value="cartao_debito">Cartão de Débito</option>
            <option value="pix">PIX</option>
            <option value="transferencia">Transferência</option>
            <option value="boleto">Boleto</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Informações Adicionais</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="centro_custo" class="formulario-label"
            >Centro de Custo</label
          >
          <select id="centro_custo" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="administrativo">Administrativo</option>
            <option value="comercial">Comercial</option>
            <option value="operacional">Operacional</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="projeto" class="formulario-label">Projeto</label>
          <select id="projeto" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="projeto_a">Projeto A</option>
            <option value="projeto_b">Projeto B</option>
            <option value="projeto_c">Projeto C</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="conciliado" class="formulario-label">Conciliado</label>
          <div class="checkbox-grupo">
            <label class="checkbox-opcao">
              <input type="checkbox" id="conciliado" />
              <span class="checkbox-texto">Sim</span>
            </label>
          </div>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <label for="observacoes" class="formulario-label">Observações</label>
          <textarea
            id="observacoes"
            class="formulario-textarea"
            rows="4"
          ></textarea>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Anexos</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <div class="upload-container">
            <div class="upload-area">
              <span class="icone icone-upload"></span>
              <span class="upload-texto">Arraste e solte arquivos aqui ou</span>
              <label class="botao botao-secundario">
                <span class="texto">Selecionar arquivos</span>
                <input type="file" multiple style="display: none;" />
              </label>
            </div>
            <div class="upload-lista">
              <!-- Arquivos anexados seriam listados aqui -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-lancamento-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-color: #f5f5f5;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.titulo-formulario {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.formulario-conteudo {
  flex: 1;
  padding: 24px;
  overflow: auto;
}

.formulario-secao {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
  overflow: hidden;
}

.secao-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  padding: 16px;
}

.formulario-grupo {
  flex: 1;
  min-width: 200px;
}

.formulario-grupo-grande {
  flex: 2;
  min-width: 300px;
}

.formulario-grupo-completo {
  width: 100%;
}

.formulario-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.formulario-input,
.formulario-select,
.formulario-textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.formulario-input:focus,
.formulario-select:focus,
.formulario-textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.radio-grupo {
  display: flex;
  gap: 16px;
}

.radio-opcao {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.radio-opcao input {
  margin-right: 8px;
}

.radio-texto {
  font-size: 14px;
  color: #333333;
}

.input-prefixo {
  position: relative;
}

.prefixo {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 14px;
  color: #666666;
}

.input-prefixo .formulario-input {
  padding-left: 36px;
}

.campo-busca {
  position: relative;
}

.botao-busca {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #999999;
  cursor: pointer;
}

.checkbox-grupo {
  display: flex;
  gap: 16px;
}

.checkbox-opcao {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.checkbox-opcao input {
  margin-right: 8px;
}

.checkbox-texto {
  font-size: 14px;
  color: #333333;
}

.upload-container {
  width: 100%;
}

.upload-area {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 32px;
  border: 2px dashed #e0e0e0;
  border-radius: 4px;
  background-color: #fafafa;
  transition: border-color 0.2s ease, background-color 0.2s ease;
}

.upload-area:hover {
  border-color: #1890ff;
  background-color: #f0f5ff;
}

.upload-area .icone {
  font-size: 32px;
  color: #999999;
  margin-bottom: 16px;
}

.upload-texto {
  font-size: 14px;
  color: #666666;
  margin-bottom: 16px;
}

.upload-lista {
  margin-top: 16px;
}
```

## Modal de Transferência

O modal para transferência entre contas é exibido ao clicar no botão "Transferir":

**Estrutura HTML:**

```html
<div class="modal-transferencia">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Transferência entre Contas</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <div class="form-grupo">
        <label class="form-label">Data:</label>
        <input
          type="date"
          class="form-input"
          id="data-transferencia"
          value="2025-05-19"
        />
      </div>

      <div class="form-grupo">
        <label class="form-label">Valor:</label>
        <div class="input-prefixo">
          <span class="prefixo">R$</span>
          <input
            type="text"
            class="form-input"
            id="valor-transferencia"
            placeholder="0,00"
          />
        </div>
      </div>

      <div class="form-grupo">
        <label class="form-label">De:</label>
        <select class="form-select" id="conta-origem">
          <option value="caixa">Caixa</option>
          <option value="banco">Banco</option>
        </select>
      </div>

      <div class="form-grupo">
        <label class="form-label">Para:</label>
        <select class="form-select" id="conta-destino">
          <option value="banco">Banco</option>
          <option value="caixa">Caixa</option>
        </select>
      </div>

      <div class="form-grupo">
        <label class="form-label">Descrição:</label>
        <input
          type="text"
          class="form-input"
          id="descricao-transferencia"
          placeholder="Transferência entre contas"
        />
      </div>

      <div class="acoes-modal">
        <button class="botao botao-primario" id="btn-confirmar-transferencia">
          <span class="icone icone-transferir"></span>
          <span class="texto">Transferir</span>
        </button>
        <button class="botao botao-secundario" id="btn-cancelar-transferencia">
          <span class="texto">Cancelar</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modal-transferencia {
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
  max-width: 500px;
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

.form-grupo {
  margin-bottom: 16px;
}

.form-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.form-input,
.form-select {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.form-input:focus,
.form-select:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.acoes-modal {
  display: flex;
  justify-content: flex-end;
  gap: 16px;
  margin-top: 24px;
}
```

## Modal de Filtros

O modal para filtros avançados é exibido ao clicar no botão de filtro avançado:

**Estrutura HTML:**

```html
<div class="modal-filtros">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Filtros Avançados</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <div class="form-grupo">
        <label class="form-label">Período:</label>
        <div class="filtro-periodo">
          <input
            type="date"
            class="form-input"
            id="data-inicial"
            value="2025-04-19"
          />
          <span class="filtro-separador">até</span>
          <input
            type="date"
            class="form-input"
            id="data-final"
            value="2025-05-19"
          />
        </div>
      </div>

      <div class="form-grupo">
        <label class="form-label">Tipo de Lançamento:</label>
        <div class="checkbox-grupo">
          <label class="checkbox-opcao">
            <input type="checkbox" id="tipo-entrada" checked />
            <span class="checkbox-texto">Entrada</span>
          </label>
          <label class="checkbox-opcao">
            <input type="checkbox" id="tipo-saida" checked />
            <span class="checkbox-texto">Saída</span>
          </label>
          <label class="checkbox-opcao">
            <input type="checkbox" id="tipo-transferencia" checked />
            <span class="checkbox-texto">Transferência</span>
          </label>
        </div>
      </div>

      <div class="form-grupo">
        <label class="form-label">Conta:</label>
        <select class="form-select" id="filtro-conta">
          <option value="">Todas</option>
          <option value="caixa">Caixa</option>
          <option value="banco">Banco</option>
        </select>
      </div>

      <div class="form-grupo">
        <label class="form-label">Categoria:</label>
        <select class="form-select" id="filtro-categoria">
          <option value="">Todas</option>
          <option value="vendas">Vendas</option>
          <option value="compras">Compras</option>
          <option value="despesas">Despesas</option>
          <option value="receitas">Receitas</option>
        </select>
      </div>

      <div class="form-grupo">
        <label class="form-label">Cliente/Fornecedor:</label>
        <div class="campo-busca">
          <input
            type="text"
            class="form-input"
            id="filtro-cliente-fornecedor"
            placeholder="Buscar cliente ou fornecedor..."
          />
          <button class="botao-busca">
            <span class="icone icone-busca"></span>
          </button>
        </div>
      </div>

      <div class="form-grupo">
        <label class="form-label">Valor:</label>
        <div class="filtro-valor">
          <div class="input-prefixo">
            <span class="prefixo">R$</span>
            <input
              type="text"
              class="form-input"
              id="valor-minimo"
              placeholder="Mínimo"
            />
          </div>
          <span class="filtro-separador">até</span>
          <div class="input-prefixo">
            <span class="prefixo">R$</span>
            <input
              type="text"
              class="form-input"
              id="valor-maximo"
              placeholder="Máximo"
            />
          </div>
        </div>
      </div>

      <div class="acoes-modal">
        <button class="botao botao-primario" id="btn-aplicar-filtros">
          <span class="icone icone-filtro"></span>
          <span class="texto">Aplicar</span>
        </button>
        <button class="botao botao-secundario" id="btn-limpar-filtros-modal">
          <span class="texto">Limpar</span>
        </button>
        <button class="botao botao-secundario" id="btn-cancelar-filtros">
          <span class="texto">Cancelar</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modal-filtros {
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

.filtro-periodo,
.filtro-valor {
  display: flex;
  align-items: center;
  gap: 8px;
}

.filtro-separador {
  font-size: 14px;
  color: #666666;
}

.checkbox-grupo {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}
```

## Interações JavaScript

### Filtros e Pesquisa

```javascript
// Código para filtro de período
document
  .querySelector(".filtro-periodo")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o seletor de período
    const hoje = new Date();
    const dataInicial = new Date();
    dataInicial.setDate(hoje.getDate() - 30); // Últimos 30 dias

    // Cria o modal de seleção
    const modal = document.createElement("div");
    modal.classList.add("modal-selecao-periodo");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Período</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="opcoes-periodo">
          <button class="botao-periodo" data-dias="7">Últimos 7 dias</button>
          <button class="botao-periodo botao-periodo-ativo" data-dias="30">Últimos 30 dias</button>
          <button class="botao-periodo" data-dias="90">Últimos 90 dias</button>
          <button class="botao-periodo" data-dias="180">Últimos 180 dias</button>
          <button class="botao-periodo" data-dias="365">Último ano</button>
          <button class="botao-periodo" data-tipo="mes-atual">Mês atual</button>
          <button class="botao-periodo" data-tipo="mes-anterior">Mês anterior</button>
          <button class="botao-periodo" data-tipo="ano-atual">Ano atual</button>
        </div>
        
        <div class="periodo-personalizado">
          <h3 class="periodo-titulo">Período personalizado</h3>
          <div class="filtro-periodo">
            <input type="date" class="form-input" id="data-inicial" value="${
              dataInicial.toISOString().split("T")[0]
            }">
            <span class="filtro-separador">até</span>
            <input type="date" class="form-input" id="data-final" value="${
              hoje.toISOString().split("T")[0]
            }">
          </div>
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-aplicar-periodo">
            <span class="texto">Aplicar</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-periodo">
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
      .querySelector("#btn-cancelar-periodo")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    // Botões de período pré-definido
    modal.querySelectorAll(".botao-periodo").forEach((botao) => {
      botao.addEventListener("click", function () {
        // Remove a classe ativa de todos os botões
        modal.querySelectorAll(".botao-periodo").forEach((b) => {
          b.classList.remove("botao-periodo-ativo");
        });

        // Adiciona a classe ativa no botão clicado
        this.classList.add("botao-periodo-ativo");

        // Atualiza as datas
        const dias = this.getAttribute("data-dias");
        const tipo = this.getAttribute("data-tipo");

        if (dias) {
          const dataFinal = new Date();
          const dataInicial = new Date();
          dataInicial.setDate(dataFinal.getDate() - parseInt(dias));

          modal.querySelector("#data-inicial").value = dataInicial
            .toISOString()
            .split("T")[0];
          modal.querySelector("#data-final").value = dataFinal
            .toISOString()
            .split("T")[0];
        } else if (tipo) {
          const hoje = new Date();
          let dataInicial, dataFinal;

          if (tipo === "mes-atual") {
            dataInicial = new Date(hoje.getFullYear(), hoje.getMonth(), 1);
            dataFinal = hoje;
          } else if (tipo === "mes-anterior") {
            dataInicial = new Date(hoje.getFullYear(), hoje.getMonth() - 1, 1);
            dataFinal = new Date(hoje.getFullYear(), hoje.getMonth(), 0);
          } else if (tipo === "ano-atual") {
            dataInicial = new Date(hoje.getFullYear(), 0, 1);
            dataFinal = hoje;
          }

          modal.querySelector("#data-inicial").value = dataInicial
            .toISOString()
            .split("T")[0];
          modal.querySelector("#data-final").value = dataFinal
            .toISOString()
            .split("T")[0];
        }
      });
    });

    // Aplicar filtro
    modal
      .querySelector("#btn-aplicar-periodo")
      .addEventListener("click", function () {
        const dataInicial = modal.querySelector("#data-inicial").value;
        const dataFinal = modal.querySelector("#data-final").value;

        // Atualiza o texto do filtro
        document.querySelector(
          ".filtro-periodo .texto"
        ).textContent = `${formatarData(dataInicial)} a ${formatarData(
          dataFinal
        )}`;

        // Carrega os lançamentos do período
        carregarLancamentos(dataInicial, dataFinal);

        // Fecha o modal
        document.body.removeChild(modal);
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

function formatarData(dataISO) {
  const partes = dataISO.split("-");
  return `${partes[2]}/${partes[1]}/${partes[0]}`;
}

// Código para filtros avançados
document
  .querySelector(".botao-filtro-avancado")
  .addEventListener("click", function () {
    // Cria o modal de filtros
    const modal = document.createElement("div");
    modal.classList.add("modal-filtros");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Filtros Avançados</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label class="form-label">Período:</label>
          <div class="filtro-periodo">
            <input type="date" class="form-input" id="data-inicial" value="2025-04-19">
            <span class="filtro-separador">até</span>
            <input type="date" class="form-input" id="data-final" value="2025-05-19">
          </div>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Tipo de Lançamento:</label>
          <div class="checkbox-grupo">
            <label class="checkbox-opcao">
              <input type="checkbox" id="tipo-entrada" checked>
              <span class="checkbox-texto">Entrada</span>
            </label>
            <label class="checkbox-opcao">
              <input type="checkbox" id="tipo-saida" checked>
              <span class="checkbox-texto">Saída</span>
            </label>
            <label class="checkbox-opcao">
              <input type="checkbox" id="tipo-transferencia" checked>
              <span class="checkbox-texto">Transferência</span>
            </label>
          </div>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Conta:</label>
          <select class="form-select" id="filtro-conta">
            <option value="">Todas</option>
            <option value="caixa">Caixa</option>
            <option value="banco">Banco</option>
          </select>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Categoria:</label>
          <select class="form-select" id="filtro-categoria">
            <option value="">Todas</option>
            <option value="vendas">Vendas</option>
            <option value="compras">Compras</option>
            <option value="despesas">Despesas</option>
            <option value="receitas">Receitas</option>
          </select>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Cliente/Fornecedor:</label>
          <div class="campo-busca">
            <input type="text" class="form-input" id="filtro-cliente-fornecedor" placeholder="Buscar cliente ou fornecedor...">
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Valor:</label>
          <div class="filtro-valor">
            <div class="input-prefixo">
              <span class="prefixo">R$</span>
              <input type="text" class="form-input" id="valor-minimo" placeholder="Mínimo">
            </div>
            <span class="filtro-separador">até</span>
            <div class="input-prefixo">
              <span class="prefixo">R$</span>
              <input type="text" class="form-input" id="valor-maximo" placeholder="Máximo">
            </div>
          </div>
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-aplicar-filtros">
            <span class="icone icone-filtro"></span>
            <span class="texto">Aplicar</span>
          </button>
          <button class="botao botao-secundario" id="btn-limpar-filtros-modal">
            <span class="texto">Limpar</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-filtros">
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
      .querySelector("#btn-cancelar-filtros")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    modal
      .querySelector("#btn-limpar-filtros-modal")
      .addEventListener("click", function () {
        // Limpa os filtros
        modal.querySelector("#filtro-conta").value = "";
        modal.querySelector("#filtro-categoria").value = "";
        modal.querySelector("#filtro-cliente-fornecedor").value = "";
        modal.querySelector("#valor-minimo").value = "";
        modal.querySelector("#valor-maximo").value = "";

        // Marca todos os tipos de lançamento
        modal.querySelector("#tipo-entrada").checked = true;
        modal.querySelector("#tipo-saida").checked = true;
        modal.querySelector("#tipo-transferencia").checked = true;

        // Define o período para os últimos 30 dias
        const hoje = new Date();
        const dataInicial = new Date();
        dataInicial.setDate(hoje.getDate() - 30);

        modal.querySelector("#data-inicial").value = dataInicial
          .toISOString()
          .split("T")[0];
        modal.querySelector("#data-final").value = hoje
          .toISOString()
          .split("T")[0];
      });

    modal
      .querySelector("#btn-aplicar-filtros")
      .addEventListener("click", function () {
        // Coleta os filtros
        const filtros = {
          dataInicial: modal.querySelector("#data-inicial").value,
          dataFinal: modal.querySelector("#data-final").value,
          tipoEntrada: modal.querySelector("#tipo-entrada").checked,
          tipoSaida: modal.querySelector("#tipo-saida").checked,
          tipoTransferencia: modal.querySelector("#tipo-transferencia").checked,
          conta: modal.querySelector("#filtro-conta").value,
          categoria: modal.querySelector("#filtro-categoria").value,
          clienteFornecedor: modal.querySelector("#filtro-cliente-fornecedor")
            .value,
          valorMinimo: modal.querySelector("#valor-minimo").value,
          valorMaximo: modal.querySelector("#valor-maximo").value,
        };

        // Aplica os filtros
        aplicarFiltros(filtros);

        // Fecha o modal
        document.body.removeChild(modal);
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

// Código para pesquisa
document
  .querySelector(".input-pesquisa")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      pesquisarLancamentos(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarLancamentos(termoPesquisa);
  });

function pesquisarLancamentos(termo) {
  if (!termo) return;

  console.log(`Pesquisando lançamentos com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/caixa/pesquisa?termo=${encodeURIComponent(termo)}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaLancamentos(data);
  //   });
}

function carregarLancamentos(dataInicial, dataFinal) {
  console.log(`Carregando lançamentos de ${dataInicial} a ${dataFinal}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/caixa?data_inicial=${dataInicial}&data_final=${dataFinal}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaLancamentos(data);
  //   });
}

function aplicarFiltros(filtros) {
  console.log("Aplicando filtros:", filtros);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/caixa/filtrar', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify(filtros)
  // })
  // .then(response => response.json())
  // .then(data => {
  //   atualizarTabelaLancamentos(data);
  // });
}

function atualizarTabelaLancamentos(data) {
  // Atualiza a tabela com os dados recebidos
  console.log("Atualizando tabela com dados:", data);

  // Implementação da atualização da tabela
}
```

### Transferência entre Contas

```javascript
// Código para transferência entre contas
document
  .querySelector("#btn-transferir")
  .addEventListener("click", function () {
    // Cria o modal de transferência
    const modal = document.createElement("div");
    modal.classList.add("modal-transferencia");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Transferência entre Contas</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label class="form-label">Data:</label>
          <input type="date" class="form-input" id="data-transferencia" value="${
            new Date().toISOString().split("T")[0]
          }">
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Valor:</label>
          <div class="input-prefixo">
            <span class="prefixo">R$</span>
            <input type="text" class="form-input" id="valor-transferencia" placeholder="0,00">
          </div>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">De:</label>
          <select class="form-select" id="conta-origem">
            <option value="caixa">Caixa</option>
            <option value="banco">Banco</option>
          </select>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Para:</label>
          <select class="form-select" id="conta-destino">
            <option value="banco">Banco</option>
            <option value="caixa">Caixa</option>
          </select>
        </div>
        
        <div class="form-grupo">
          <label class="form-label">Descrição:</label>
          <input type="text" class="form-input" id="descricao-transferencia" placeholder="Transferência entre contas">
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-confirmar-transferencia">
            <span class="icone icone-transferir"></span>
            <span class="texto">Transferir</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-transferencia">
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
      .querySelector("#btn-cancelar-transferencia")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    modal
      .querySelector("#btn-confirmar-transferencia")
      .addEventListener("click", function () {
        // Coleta os dados da transferência
        const transferencia = {
          data: modal.querySelector("#data-transferencia").value,
          valor: modal.querySelector("#valor-transferencia").value,
          contaOrigem: modal.querySelector("#conta-origem").value,
          contaDestino: modal.querySelector("#conta-destino").value,
          descricao:
            modal.querySelector("#descricao-transferencia").value ||
            "Transferência entre contas",
        };

        // Valida os dados
        if (
          !transferencia.valor ||
          parseFloat(transferencia.valor.replace(",", ".")) <= 0
        ) {
          alert("Informe um valor válido para a transferência");
          return;
        }

        if (transferencia.contaOrigem === transferencia.contaDestino) {
          alert("As contas de origem e destino devem ser diferentes");
          return;
        }

        // Realiza a transferência
        realizarTransferencia(transferencia);

        // Fecha o modal
        document.body.removeChild(modal);
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

function realizarTransferencia(transferencia) {
  console.log("Realizando transferência:", transferencia);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/caixa/transferir', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify(transferencia)
  // })
  // .then(response => {
  //   if (response.ok) {
  //     alert('Transferência realizada com sucesso!');
  //     // Recarrega os lançamentos
  //     carregarLancamentos();
  //   } else {
  //     throw new Error('Erro ao realizar transferência');
  //   }
  // })
  // .catch(error => {
  //   alert(`Erro ao realizar transferência: ${error.message}`);
  // });

  // Simulação de transferência
  setTimeout(() => {
    alert("Transferência realizada com sucesso!");
  }, 1000);
}
```

### Formulário de Lançamento

```javascript
// Código para formulário de lançamento
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioLancamento = document.querySelector(
    ".formulario-lancamento-container"
  );
  if (!formularioLancamento) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data_lancamento").value = hoje;

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação do lançamento? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/caixa";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-lancamento-container");

    // Verifica campos obrigatórios
    const camposObrigatorios = form.querySelectorAll("[required]");
    let valido = true;

    camposObrigatorios.forEach((campo) => {
      if (!campo.value) {
        campo.classList.add("campo-invalido");
        valido = false;
      } else {
        campo.classList.remove("campo-invalido");
      }
    });

    if (!valido) {
      alert("Preencha todos os campos obrigatórios");
      return;
    }

    // Coleta os dados do formulário
    const tipoLancamento = document.querySelector(
      'input[name="tipo_lancamento"]:checked'
    ).value;
    const lancamento = {
      tipo: tipoLancamento,
      data: document.querySelector("#data_lancamento").value,
      valor: document.querySelector("#valor").value,
      conta: document.querySelector("#conta").value,
      descricao: document.querySelector("#descricao").value,
      categoria: document.querySelector("#categoria").value,
      clienteFornecedor: document.querySelector("#cliente_fornecedor").value,
      formaPagamento: document.querySelector("#forma_pagamento").value,
      centroCusto: document.querySelector("#centro_custo").value,
      projeto: document.querySelector("#projeto").value,
      conciliado: document.querySelector("#conciliado").checked,
      observacoes: document.querySelector("#observacoes").value,
    };

    // Envia para a API
    console.log("Salvando lançamento:", lancamento);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Lançamento salvo com sucesso!");
      window.location.href = "/caixa";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/caixa', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(lancamento)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Lançamento salvo com sucesso!');
    //     window.location.href = '/caixa';
    //   } else {
    //     throw new Error('Erro ao salvar lançamento');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar lançamento: ${error.message}`);
    // });
  });

  // Busca de cliente/fornecedor
  document
    .querySelector("#cliente_fornecedor")
    .addEventListener("focus", function () {
      // Abre modal de busca de clientes/fornecedores
      const modal = document.createElement("div");
      modal.classList.add("modal-busca-cliente");
      modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Selecionar Cliente/Fornecedor</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="campo-busca">
            <input type="text" class="formulario-input input-busca-cliente" placeholder="Buscar cliente ou fornecedor...">
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
          <div class="lista-clientes">
            <table class="tabela-selecao-clientes">
              <thead>
                <tr>
                  <th>Nome</th>
                  <th>Tipo</th>
                  <th>Documento</th>
                  <th></th>
                </tr>
              </thead>
              <tbody>
                <tr data-cliente-id="1">
                  <td>Cliente A</td>
                  <td>Cliente</td>
                  <td>123.456.789-00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-cliente-id="2">
                  <td>Fornecedor B</td>
                  <td>Fornecedor</td>
                  <td>12.345.678/0001-90</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-cliente-id="3">
                  <td>Cliente C</td>
                  <td>Cliente</td>
                  <td>987.654.321-00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    `;

      document.body.appendChild(modal);

      // Adiciona eventos
      modal
        .querySelector(".botao-fechar")
        .addEventListener("click", function () {
          document.body.removeChild(modal);
        });

      modal.querySelectorAll(".botao-selecionar").forEach((botao) => {
        botao.addEventListener("click", function () {
          const linha = this.closest("tr");
          const clienteNome = linha.querySelector("td:first-child").textContent;

          // Preenche o campo
          document.querySelector("#cliente_fornecedor").value = clienteNome;

          // Fecha o modal
          document.body.removeChild(modal);
        });
      });

      // Fecha o modal ao clicar fora
      modal.addEventListener("click", function (e) {
        if (e.target === modal) {
          document.body.removeChild(modal);
        }
      });
    });

  // Tipo de lançamento
  document
    .querySelectorAll('input[name="tipo_lancamento"]')
    .forEach((radio) => {
      radio.addEventListener("change", function () {
        const tipoLancamento = this.value;

        // Atualiza a interface de acordo com o tipo de lançamento
        if (tipoLancamento === "transferencia") {
          // Esconde campos não aplicáveis a transferências
          document
            .querySelector("#categoria")
            .closest(".formulario-grupo").style.display = "none";
          document
            .querySelector("#cliente_fornecedor")
            .closest(".formulario-grupo").style.display = "none";
          document
            .querySelector("#forma_pagamento")
            .closest(".formulario-grupo").style.display = "none";
        } else {
          // Mostra campos para entrada e saída
          document
            .querySelector("#categoria")
            .closest(".formulario-grupo").style.display = "block";
          document
            .querySelector("#cliente_fornecedor")
            .closest(".formulario-grupo").style.display = "block";
          document
            .querySelector("#forma_pagamento")
            .closest(".formulario-grupo").style.display = "block";
        }
      });
    });

  // Upload de arquivos
  const uploadArea = document.querySelector(".upload-area");
  if (uploadArea) {
    uploadArea.addEventListener("dragover", function (e) {
      e.preventDefault();
      this.classList.add("upload-area-ativa");
    });

    uploadArea.addEventListener("dragleave", function (e) {
      e.preventDefault();
      this.classList.remove("upload-area-ativa");
    });

    uploadArea.addEventListener("drop", function (e) {
      e.preventDefault();
      this.classList.remove("upload-area-ativa");

      const arquivos = e.dataTransfer.files;
      processarArquivos(arquivos);
    });

    const inputArquivo = uploadArea.querySelector('input[type="file"]');
    inputArquivo.addEventListener("change", function () {
      const arquivos = this.files;
      processarArquivos(arquivos);
    });
  }

  function processarArquivos(arquivos) {
    const listaArquivos = document.querySelector(".upload-lista");

    for (let i = 0; i < arquivos.length; i++) {
      const arquivo = arquivos[i];

      // Cria o item de arquivo
      const itemArquivo = document.createElement("div");
      itemArquivo.classList.add("upload-item");
      itemArquivo.innerHTML = `
        <div class="upload-item-info">
          <span class="upload-item-nome">${arquivo.name}</span>
          <span class="upload-item-tamanho">${formatarTamanho(
            arquivo.size
          )}</span>
        </div>
        <button class="botao-remover-arquivo">
          <span class="icone icone-remover"></span>
        </button>
      `;

      // Adiciona o item à lista
      listaArquivos.appendChild(itemArquivo);

      // Adiciona evento para remover o arquivo
      itemArquivo
        .querySelector(".botao-remover-arquivo")
        .addEventListener("click", function () {
          listaArquivos.removeChild(itemArquivo);
        });
    }
  }

  function formatarTamanho(bytes) {
    if (bytes < 1024) {
      return bytes + " B";
    } else if (bytes < 1024 * 1024) {
      return (bytes / 1024).toFixed(2) + " KB";
    } else if (bytes < 1024 * 1024 * 1024) {
      return (bytes / (1024 * 1024)).toFixed(2) + " MB";
    } else {
      return (bytes / (1024 * 1024 * 1024)).toFixed(2) + " GB";
    }
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .formulario-linha {
    flex-direction: column;
  }

  .formulario-grupo,
  .formulario-grupo-grande {
    width: 100%;
  }

  .filtro-valor {
    flex-direction: column;
    gap: 16px;
  }

  .filtro-valor .filtro-separador {
    display: none;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .modulo-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-start;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pesquisa-filtros-container {
    flex-direction: column;
    align-items: flex-start;
  }

  .pesquisa-container {
    width: 100%;
    max-width: none;
    margin-bottom: 16px;
  }

  .filtros-container {
    width: 100%;
    flex-wrap: wrap;
  }

  .coluna-categoria,
  .coluna-cliente {
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

  .radio-grupo {
    flex-direction: column;
    gap: 8px;
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
```

### Campos de Formulário

```css
.formulario-input,
.formulario-select,
.formulario-textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.formulario-input:focus,
.formulario-select:focus,
.formulario-textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-invalido {
  border-color: #f5222d;
}

.campo-invalido:focus {
  border-color: #f5222d;
  box-shadow: 0 0 0 2px rgba(245, 34, 45, 0.2);
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
.tabela-lancamentos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-lancamentos th,
.tabela-lancamentos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-lancamentos th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-lancamentos tbody tr:hover {
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
```

## Fluxos de Navegação

1. **Listagem de Lançamentos**:

   - O usuário acessa o módulo "Caixa"
   - Visualiza a lista de lançamentos
   - Pode filtrar por período
   - Pode pesquisar por cliente ou fornecedor
   - Pode aplicar filtros avançados

2. **Inclusão de Lançamento**:

   - O usuário clica no botão "Incluir lançamento"
   - Seleciona o tipo de lançamento (entrada, saída ou transferência)
   - Preenche os dados do lançamento
   - Salva o lançamento

3. **Transferência entre Contas**:

   - O usuário clica no botão "Transferir"
   - Preenche os dados da transferência
   - Confirma a transferência

4. **Edição de Lançamento**:

   - O usuário clica no botão de edição de um lançamento na lista
   - Altera os dados do lançamento
   - Salva as alterações

5. **Exclusão de Lançamento**:
   - O usuário clica no botão de exclusão de um lançamento na lista
   - Confirma a exclusão
   - O lançamento é removido da lista

## Conclusão

O módulo "Caixa" do ERP Revo apresenta uma interface completa e funcional para gerenciamento de fluxo de caixa e controle financeiro. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, incluir, editar e excluir lançamentos de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento financeiro, como inclusão de lançamentos, transferência entre contas, filtros avançados e relatórios, atendendo às necessidades de negócios que precisam controlar seu fluxo de caixa.
