# Análise do Módulo Propostas Comerciais - ERP Revo

## Estrutura Geral

O módulo "Propostas Comerciais" do ERP Revo apresenta uma interface para gerenciamento de propostas e orçamentos. A tela principal exibe uma lista de propostas (vazia no estado atual) com opções de filtragem, pesquisa e ações para criar novas propostas.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Propostas Comerciais"
- Botão "Imprimir"
- Botão "Incluir proposta"
- Botão "Mais ações"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Propostas Comerciais</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <button class="botao botao-primario" id="btn-incluir-proposta">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir proposta</span>
    </button>
    <div class="dropdown">
      <button class="botao botao-secundario" id="btn-mais-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item">Exportar</a>
        <a href="#" class="dropdown-item">Importar</a>
        <a href="#" class="dropdown-item">Configurações</a>
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

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 10;
  min-width: 160px;
  padding: 8px 0;
  margin-top: 4px;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: none;
}

.dropdown.ativo .dropdown-menu {
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

A área de pesquisa e filtros permite buscar e filtrar propostas:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por cliente ou número"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link">
      <span class="icone icone-calendario"></span>
      <span class="texto">por período</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
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
  flex: 1;
  max-width: 500px;
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
}

.filtro-link:hover {
  text-decoration: underline;
}

.filtro-link .icone {
  margin-right: 4px;
}
```

### Abas de Situação

As abas de situação permitem filtrar propostas por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">Em aberto</a>
  <a href="#" class="aba">Rascunhos</a>
  <a href="#" class="aba">Pendentes</a>
  <a href="#" class="aba">Aguardando</a>
  <a href="#" class="aba">Aprovadas</a>
  <a href="#" class="aba aba-mais">
    <span class="icone icone-mais"></span>
    <span class="texto">mais</span>
  </a>
  <div class="filtro-ativo">
    <span class="texto">Situação: Em aberto</span>
    <button class="botao-remover-filtro">
      <span class="icone icone-fechar"></span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.abas-container {
  display: flex;
  align-items: center;
  padding: 0 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  overflow-x: auto;
}

.aba {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  color: #666666;
  text-decoration: none;
  font-size: 14px;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
  white-space: nowrap;
}

.aba:hover {
  color: #1890ff;
}

.aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.aba .icone {
  margin-right: 4px;
}

.aba-mais {
  color: #1890ff;
}

.filtro-ativo {
  display: inline-flex;
  align-items: center;
  margin-left: 16px;
  padding: 4px 8px;
  background-color: #e6f7ff;
  border-radius: 4px;
  font-size: 12px;
  color: #1890ff;
}

.filtro-ativo .texto {
  margin-right: 4px;
}

.botao-remover-filtro {
  background: none;
  border: none;
  color: #1890ff;
  cursor: pointer;
  padding: 0;
  font-size: 12px;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há propostas:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <p class="texto-vazio">Ops! Você ainda não tem propostas comerciais.</p>
    </div>

    <div class="cards-info">
      <div class="card-info">
        <div class="card-info-imagem">
          <img
            src="/assets/images/proposta-comercial.svg"
            alt="Proposta comercial"
          />
        </div>
        <div class="card-info-conteudo">
          <h3 class="card-info-titulo">
            Crie propostas comerciais e orçamentos
          </h3>
          <p class="card-info-descricao">
            Informe dados do orçamento e do cliente para criar uma proposta.
          </p>
        </div>
      </div>

      <div class="card-info">
        <div class="card-info-imagem">
          <img
            src="/assets/images/status-negociacao.svg"
            alt="Status da negociação"
          />
        </div>
        <div class="card-info-conteudo">
          <h3 class="card-info-titulo">Atualize o status da negociação</h3>
          <p class="card-info-descricao">
            Indique o avanço da negociação das propostas comerciais.
          </p>
        </div>
      </div>

      <div class="card-info">
        <div class="card-info-imagem">
          <img src="/assets/images/pedido-venda.svg" alt="Pedido de venda" />
        </div>
        <div class="card-info-conteudo">
          <h3 class="card-info-titulo">
            Gere um pedido a partir de uma proposta comercial
          </h3>
          <p class="card-info-descricao">
            Após a aprovação por parte do cliente, é possível gerar pedidos de
            venda.
          </p>
        </div>
      </div>
    </div>

    <div class="acoes-vazio">
      <button class="botao botao-primario" id="btn-incluir-proposta-vazio">
        <span class="icone icone-adicionar"></span>
        <span class="texto">incluir proposta</span>
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
  max-width: 1200px;
  margin: 0 auto;
}

.mensagem-vazio {
  margin-bottom: 32px;
  text-align: center;
}

.texto-vazio {
  font-size: 18px;
  color: #666666;
  margin: 0;
}

.cards-info {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
  margin-bottom: 32px;
}

.card-info {
  flex: 1;
  min-width: 300px;
  max-width: 350px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.card-info-imagem {
  height: 160px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f0f5ff;
  padding: 16px;
}

.card-info-imagem img {
  max-width: 100%;
  max-height: 100%;
}

.card-info-conteudo {
  padding: 16px;
}

.card-info-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.card-info-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
  line-height: 1.5;
}

.acoes-vazio {
  margin-top: 16px;
}
```

### Área de Conteúdo com Propostas

Quando houver propostas, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-propostas">
      <thead>
        <tr>
          <th class="coluna-selecao">
            <input type="checkbox" class="checkbox-selecionar-todos" />
          </th>
          <th class="coluna-numero">Número</th>
          <th class="coluna-data">Data</th>
          <th class="coluna-cliente">Cliente</th>
          <th class="coluna-valor">Valor</th>
          <th class="coluna-situacao">Situação</th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Propostas serão adicionadas dinamicamente -->
      </tbody>
    </table>

    <div class="paginacao">
      <div class="paginacao-info">
        <span class="texto">Exibindo 0 de 0 registros</span>
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

.tabela-propostas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-propostas th,
.tabela-propostas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-propostas th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-propostas tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
}

.coluna-numero {
  width: 100px;
}

.coluna-data {
  width: 120px;
}

.coluna-valor {
  width: 120px;
  text-align: right;
}

.coluna-situacao {
  width: 120px;
}

.coluna-acoes {
  width: 80px;
  text-align: center;
}

.checkbox-selecionar-todos {
  cursor: pointer;
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

## Formulário de Criação/Edição de Proposta

O formulário para criar ou editar propostas é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-proposta-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Proposta Comercial</h1>
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
          <label for="numero" class="formulario-label">Número</label>
          <input type="text" id="numero" class="formulario-input" value="1" readonly>
        </div>

        <div class="formulario-grupo">
          <label for="data" class="formulario-label">Data</label>
          <input type="date" id="data" class="formulario-input" required>
        </div>

        <div class="formulario-grupo">
          <label for="validade" class="formulario-label">Validade</label>
          <input type="date" id="validade" class="formulario-input" required>
        </div>

        <div class="formulario-grupo">
          <label for="situacao" class="formulario-label">Situação</label>
          <select id="situacao" class="formulario-select" required>
            <option value="em_aberto">Em aberto</option>
            <option value="rascunho">Rascunho</option>
            <option value="pendente">Pendente</option>
            <option value="aguardando">Aguardando</option>
            <option value="aprovada">Aprovada</option>
            <option value="recusada">Recusada</option>
            <option value="cancelada">Cancelada</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Cliente</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="cliente" class="formulario-label">Cliente</label>
          <div class="campo-busca">
            <input type="text" id="cliente" class="formulario-input" placeholder
(Content truncated due to size limit. Use line ranges to read in chunks)
```
