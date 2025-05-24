# Análise do Módulo Devoluções de Venda - ERP Revo

## Estrutura Geral

O módulo "Devoluções de Venda" do ERP Revo apresenta uma interface para gerenciamento de devoluções de produtos vendidos. A tela principal exibe uma área de pesquisa, filtros, abas de situação e uma lista de devoluções quando disponíveis.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Devoluções de vendas</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-gerenciar-vales">
      <span class="icone icone-vale"></span>
      <span class="texto">Gerenciar vales-troca</span>
    </button>
    <a
      href="/devolucoes_vendas/novo"
      class="botao botao-primario"
      id="btn-incluir-devolucao"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir devolução</span>
    </a>
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
```

### Área de Pesquisa e Filtros

A área de pesquisa e filtros permite buscar e filtrar devoluções:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por cliente, pedido ou nota fiscal"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link filtro-periodo">
      <span class="icone icone-calendario"></span>
      <span class="texto">por período</span>
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

### Abas de Situação

As abas de situação permitem filtrar devoluções por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">
    <span class="indicador indicador-aberto"></span>
    <span class="texto">Em aberto</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-andamento"></span>
    <span class="texto">Em andamento</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-finalizada"></span>
    <span class="texto">Finalizadas</span>
  </a>
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

.indicador {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-aberto {
  background-color: #faad14;
}

.indicador-andamento {
  background-color: #52c41a;
}

.indicador-finalizada {
  background-color: #8c8c8c;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há devoluções cadastradas:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <h2 class="titulo-vazio">Você não possui nenhum item cadastrado.</h2>
      <p class="texto-vazio">
        Para inserir novos registros você pode clicar em incluir devolução.
      </p>
    </div>

    <div class="ilustracao-vazio">
      <img
        src="/assets/images/ilustracao-vazio.svg"
        alt="Nenhum registro encontrado"
      />
    </div>

    <div class="acoes-vazio">
      <a
        href="/devolucoes_vendas/novo"
        class="botao botao-primario"
        id="btn-incluir-devolucao-vazio"
      >
        <span class="texto">incluir devolução</span>
      </a>
    </div>

    <div class="ajuda-container">
      <p class="texto-ajuda">Ficou com alguma dúvida?</p>
      <a href="/ajuda/devolucoes" class="link-ajuda">Acesse a ajuda do Revo.</a>
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
  margin-bottom: 24px;
}

.ajuda-container {
  text-align: center;
  border-top: 1px solid #f0f0f0;
  padding-top: 16px;
  width: 100%;
}

.texto-ajuda {
  font-size: 14px;
  color: #666666;
  margin: 0 0 8px 0;
}

.link-ajuda {
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
}

.link-ajuda:hover {
  text-decoration: underline;
}
```

### Tabela de Devoluções

Quando houver devoluções, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-devolucoes">
      <thead>
        <tr>
          <th class="coluna-numero">
            <div class="cabecalho-ordenavel">
              <span class="texto">Número</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
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
          <th class="coluna-pedido">
            <div class="cabecalho-ordenavel">
              <span class="texto">Pedido</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-nota">
            <div class="cabecalho-ordenavel">
              <span class="texto">Nota Fiscal</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-situacao">
            <div class="cabecalho-ordenavel">
              <span class="texto">Situação</span>
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
        <!-- Devoluções serão adicionadas dinamicamente -->
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

.tabela-devolucoes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-devolucoes th,
.tabela-devolucoes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-devolucoes th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-devolucoes tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-numero,
.coluna-data,
.coluna-pedido,
.coluna-nota {
  width: 100px;
}

.coluna-situacao {
  width: 120px;
}

.coluna-valor {
  width: 100px;
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

## Formulário de Criação/Edição de Devolução

O formulário para criar ou editar devoluções é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-devolucao-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Devolução</h1>
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
          <label for="data_devolucao" class="formulario-label"
            >Data da Devolução</label
          >
          <input
            type="date"
            id="data_devolucao"
            class="formulario-input"
            required
          />
        </div>

        <div class="formulario-grupo">
          <label for="pedido" class="formulario-label">Pedido</label>
          <div class="campo-busca">
            <input
              type="text"
              id="pedido"
              class="formulario-input"
              placeholder="Buscar pedido..."
              required
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="nota_fiscal" class="formulario-label">Nota Fiscal</label>
          <div class="campo-busca">
            <input
              type="text"
              id="nota_fiscal"
              class="formulario-input"
              placeholder="Buscar nota fiscal..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="cliente" class="formulario-label">Cliente</label>
          <input type="text" id="cliente" class="formulario-input" readonly />
        </div>

        <div class="formulario-grupo">
          <label for="situacao" class="formulario-label">Situação</label>
          <select id="situacao" class="formulario-select" required>
            <option value="em_aberto">Em aberto</option>
            <option value="em_andamento">Em andamento</option>
            <option value="finalizada">Finalizada</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Produtos</h2>

      <div class="formulario-tabela">
        <table class="tabela-produtos">
          <thead>
            <tr>
              <th class="coluna-produto">Produto</th>
              <th class="coluna-quantidade">Quantidade</th>
              <th class="coluna-unitario">Valor Unitário</th>
              <th class="coluna-motivo">Motivo da Devolução</th>
              <th class="coluna-total">Total</th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <tr class="linha-adicionar">
              <td colspan="6">
                <button class="botao-adicionar-produto">
                  < (Content truncated due to size limit. Use line ranges to
                  read in chunks)
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>
```
