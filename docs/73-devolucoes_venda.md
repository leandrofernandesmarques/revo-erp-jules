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
                  <span class="icone icone-adicionar"></span>
                  <span class="texto">Adicionar Produto</span>
                </button>
              </td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="4" class="rodape-label">Total:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Forma de Devolução</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="forma_devolucao" class="formulario-label"
            >Forma de Devolução</label
          >
          <select id="forma_devolucao" class="formulario-select" required>
            <option value="">Selecione...</option>
            <option value="vale_troca">Vale-Troca</option>
            <option value="estorno">Estorno</option>
            <option value="troca">Troca</option>
          </select>
        </div>

        <div class="formulario-grupo forma-vale-troca" style="display: none;">
          <label for="validade_vale" class="formulario-label"
            >Validade do Vale-Troca</label
          >
          <input type="date" id="validade_vale" class="formulario-input" />
        </div>

        <div class="formulario-grupo forma-estorno" style="display: none;">
          <label for="forma_pagamento" class="formulario-label"
            >Forma de Pagamento</label
          >
          <select id="forma_pagamento" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="credito">Cartão de Crédito</option>
            <option value="debito">Cartão de Débito</option>
            <option value="pix">PIX</option>
            <option value="dinheiro">Dinheiro</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Observações</h2>

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
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-devolucao-container {
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

.formulario-input[readonly] {
  background-color: #f5f5f5;
  cursor: not-allowed;
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

.formulario-tabela {
  padding: 0 16px 16px;
}

.tabela-produtos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos th,
.tabela-produtos td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos th {
  font-weight: 500;
  color: #666666;
}

.coluna-produto {
  width: 30%;
}

.coluna-quantidade,
.coluna-unitario,
.coluna-total {
  width: 15%;
}

.coluna-motivo {
  width: 25%;
}

.coluna-acoes {
  width: 60px;
  text-align: center;
}

.linha-adicionar td {
  padding: 16px 0;
  text-align: center;
}

.botao-adicionar-produto {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  background-color: transparent;
  border: 1px dashed #1890ff;
  border-radius: 4px;
  color: #1890ff;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-adicionar-produto:hover {
  background-color: #e6f7ff;
}

.botao-adicionar-produto .icone {
  margin-right: 8px;
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

## Modal de Gerenciamento de Vales-Troca

O modal para gerenciar vales-troca é exibido ao clicar no botão "Gerenciar vales-troca":

**Estrutura HTML:**

```html
<div class="modal-vales-troca">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Gerenciar Vales-Troca</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <div class="pesquisa-container">
        <div class="campo-pesquisa">
          <input
            type="text"
            placeholder="Pesquise por código ou cliente"
            class="input-pesquisa"
          />
          <button class="botao-pesquisa">
            <span class="icone icone-pesquisa"></span>
          </button>
        </div>
      </div>

      <div class="tabela-container">
        <table class="tabela-vales">
          <thead>
            <tr>
              <th class="coluna-codigo">Código</th>
              <th class="coluna-cliente">Cliente</th>
              <th class="coluna-data">Data</th>
              <th class="coluna-validade">Validade</th>
              <th class="coluna-valor">Valor</th>
              <th class="coluna-situacao">Situação</th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <!-- Vales-troca serão adicionados dinamicamente -->
          </tbody>
        </table>
      </div>

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
      </div>

      <div class="acoes-modal">
        <button class="botao botao-secundario" id="btn-fechar-modal">
          <span class="texto">Fechar</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modal-vales-troca {
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
  margin-bottom: 16px;
}

.tabela-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.tabela-vales {
  width: 100%;
  border-collapse: collapse;
}

.tabela-vales th,
.tabela-vales td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-vales th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
}

.coluna-codigo,
.coluna-data,
.coluna-validade {
  width: 100px;
}

.coluna-valor,
.coluna-situacao {
  width: 120px;
}

.coluna-acoes {
  width: 80px;
  text-align: center;
}

.acoes-modal {
  display: flex;
  justify-content: flex-end;
  margin-top: 16px;
}
```

## Interações JavaScript

### Filtros e Abas

```javascript
// Código para seleção de abas
document.querySelectorAll(".aba").forEach((aba) => {
  aba.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove a classe ativa de todas as abas
    document.querySelectorAll(".aba").forEach((a) => {
      a.classList.remove("aba-ativa");
    });

    // Adiciona a classe ativa na aba clicada
    this.classList.add("aba-ativa");

    // Carrega as devoluções com o filtro selecionado
    const situacao =
      this.querySelector(".texto")?.textContent.trim() ||
      this.textContent.trim();
    carregarDevolucoes(situacao);
  });
});

// Código para filtro de período
document
  .querySelector(".filtro-periodo")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o seletor de período
    const hoje = new Date();
    const dataInicial = new Date(hoje.getFullYear(), hoje.getMonth(), 1);
    const dataFinal = hoje;

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
        <div class="form-grupo">
          <label class="form-label">Data Inicial:</label>
          <input type="date" class="form-input" id="data-inicial" value="${
            dataInicial.toISOString().split("T")[0]
          }">
        </div>
        <div class="form-grupo">
          <label class="form-label">Data Final:</label>
          <input type="date" class="form-input" id="data-final" value="${
            dataFinal.toISOString().split("T")[0]
          }">
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

        // Carrega as devoluções do período
        carregarDevolucoes(null, dataInicial, dataFinal);

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

function carregarDevolucoes(situacao, dataInicial, dataFinal) {
  // Simulação de carregamento de devoluções
  console.log(
    `Carregando devoluções com situação: ${situacao}, período: ${dataInicial} a ${dataFinal}`
  );

  // Aqui seria feita uma requisição para a API
  // fetch('/api/devolucoes', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({
  //     situacao,
  //     data_inicial: dataInicial,
  //     data_final: dataFinal
  //   })
  // })
  // .then(response => response.json())
  // .then(data => {
  //   atualizarTabelaDevolucoes(data);
  // });
}
```

### Pesquisa

```javascript
// Código para pesquisa
document
  .querySelector(".input-pesquisa")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      pesquisarDevolucoes(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarDevolucoes(termoPesquisa);
  });

function pesquisarDevolucoes(termo) {
  if (!termo) return;

  console.log(`Pesquisando devoluções com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/devolucoes/pesquisa?termo=${encodeURIComponent(termo)}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaDevolucoes(data);
  //   });
}
```

### Gerenciamento de Vales-Troca

```javascript
// Código para gerenciamento de vales-troca
document
  .querySelector("#btn-gerenciar-vales")
  .addEventListener("click", function () {
    // Cria o modal de vales-troca
    const modal = document.createElement("div");
    modal.classList.add("modal-vales-troca");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Gerenciar Vales-Troca</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="pesquisa-container">
          <div class="campo-pesquisa">
            <input type="text" placeholder="Pesquise por código ou cliente" class="input-pesquisa">
            <button class="botao-pesquisa">
              <span class="icone icone-pesquisa"></span>
            </button>
          </div>
        </div>
        
        <div class="tabela-container">
          <table class="tabela-vales">
            <thead>
              <tr>
                <th class="coluna-codigo">Código</th>
                <th class="coluna-cliente">Cliente</th>
                <th class="coluna-data">Data</th>
                <th class="coluna-validade">Validade</th>
                <th class="coluna-valor">Valor</th>
                <th class="coluna-situacao">Situação</th>
                <th class="coluna-acoes"></th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="coluna-codigo">VT001</td>
                <td class="coluna-cliente">Cliente A</td>
                <td class="coluna-data">15/05/2025</td>
                <td class="coluna-validade">15/08/2025</td>
                <td class="coluna-valor">R$ 150,00</td>
                <td class="coluna-situacao">Disponível</td>
                <td class="coluna-acoes">
                  <button class="botao-acao botao-visualizar" title="Visualizar">
                    <span class="icone icone-visualizar"></span>
                  </button>
                  <button class="botao-acao botao-imprimir" title="Imprimir">
                    <span class="icone icone-imprimir"></span>
                  </button>
                </td>
              </tr>
              <tr>
                <td class="coluna-codigo">VT002</td>
                <td class="coluna-cliente">Cliente B</td>
                <td class="coluna-data">16/05/2025</td>
                <td class="coluna-validade">16/08/2025</td>
                <td class="coluna-valor">R$ 200,00</td>
                <td class="coluna-situacao">Utilizado</td>
                <td class="coluna-acoes">
                  <button class="botao-acao botao-visualizar" title="Visualizar">
                    <span class="icone icone-visualizar"></span>
                  </button>
                  <button class="botao-acao botao-imprimir" title="Imprimir">
                    <span class="icone icone-imprimir"></span>
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        
        <div class="paginacao">
          <div class="paginacao-info">
            <span class="texto">Exibindo 2 de 2 registros</span>
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
        </div>
        
        <div class="acoes-modal">
          <button class="botao botao-secundario" id="btn-fechar-modal">
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
      .querySelector("#btn-fechar-modal")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    // Pesquisa de vales-troca
    modal
      .querySelector(".botao-pesquisa")
      .addEventListener("click", function () {
        const termoPesquisa = modal.querySelector(".input-pesquisa").value;
        pesquisarValesTroca(termoPesquisa);
      });

    modal
      .querySelector(".input-pesquisa")
      .addEventListener("keydown", function (e) {
        if (e.key === "Enter") {
          const termoPesquisa = this.value;
          pesquisarValesTroca(termoPesquisa);
        }
      });

    // Botões de ação
    modal.querySelectorAll(".botao-visualizar").forEach((botao) => {
      botao.addEventListener("click", function () {
        const linha = this.closest("tr");
        const codigo = linha.querySelector(".coluna-codigo").textContent;
        visualizarValeTroca(codigo);
      });
    });

    modal.querySelectorAll(".botao-imprimir").forEach((botao) => {
      botao.addEventListener("click", function () {
        const linha = this.closest("tr");
        const codigo = linha.querySelector(".coluna-codigo").textContent;
        imprimirValeTroca(codigo);
      });
    });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

function pesquisarValesTroca(termo) {
  console.log(`Pesquisando vales-troca com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/vales-troca/pesquisa?termo=${encodeURIComponent(termo)}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaValesTroca(data);
  //   });
}

function visualizarValeTroca(codigo) {
  console.log(`Visualizando vale-troca: ${codigo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/vales-troca/${codigo}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     exibirDetalhesValeTroca(data);
  //   });

  // Simulação de detalhes
  const detalhes = {
    codigo: codigo,
    cliente: codigo === "VT001" ? "Cliente A" : "Cliente B",
    data: codigo === "VT001" ? "15/05/2025" : "16/05/2025",
    validade: codigo === "VT001" ? "15/08/2025" : "16/08/2025",
    valor: codigo === "VT001" ? 150.0 : 200.0,
    situacao: codigo === "VT001" ? "Disponível" : "Utilizado",
    devolucao: {
      numero: codigo === "VT001" ? "DEV001" : "DEV002",
      data: codigo === "VT001" ? "15/05/2025" : "16/05/2025",
      produtos: [
        {
          nome: "Produto 1",
          quantidade: 1,
          valor_unitario: codigo === "VT001" ? 150.0 : 200.0,
          motivo: "Defeito",
        },
      ],
    },
    utilizacao:
      codigo === "VT001"
        ? null
        : {
            pedido: "PED003",
            data: "17/05/2025",
            valor: 200.0,
          },
  };

  exibirDetalhesValeTroca(detalhes);
}

function exibirDetalhesValeTroca(detalhes) {
  // Cria o modal de detalhes
  const modal = document.createElement("div");
  modal.classList.add("modal-detalhes-vale");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Detalhes do Vale-Troca ${detalhes.codigo}</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="detalhes-secao">
          <h3 class="detalhes-titulo">Informações Gerais</h3>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Código:</span>
              <span class="detalhes-valor">${detalhes.codigo}</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Cliente:</span>
              <span class="detalhes-valor">${detalhes.cliente}</span>
            </div>
          </div>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Data:</span>
              <span class="detalhes-valor">${detalhes.data}</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Validade:</span>
              <span class="detalhes-valor">${detalhes.validade}</span>
            </div>
          </div>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Valor:</span>
              <span class="detalhes-valor">R$ ${detalhes.valor.toFixed(
                2
              )}</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Situação:</span>
              <span class="detalhes-valor">${detalhes.situacao}</span>
            </div>
          </div>
        </div>
        
        <div class="detalhes-secao">
          <h3 class="detalhes-titulo">Devolução</h3>
          <div class="detalhes-linha">
            <div class="detalhes-grupo">
              <span class="detalhes-label">Número:</span>
              <span class="detalhes-valor">${detalhes.devolucao.numero}</span>
            </div>
            <div class="detalhes-grupo">
              <span class="detalhes-label">Data:</span>
              <span class="detalhes-valor">${detalhes.devolucao.data}</span>
            </div>
          </div>
          
          <div class="detalhes-tabela">
            <table class="tabela-produtos-devolucao">
              <thead>
                <tr>
                  <th>Produto</th>
                  <th>Quantidade</th>
                  <th>Valor Unitário</th>
                  <th>Motivo</th>
                  <th>Total</th>
                </tr>
              </thead>
              <tbody>
                ${detalhes.devolucao.produtos
                  .map(
                    (produto) => `
                  <tr>
                    <td>${produto.nome}</td>
                    <td>${produto.quantidade}</td>
                    <td>R$ ${produto.valor_unitario.toFixed(2)}</td>
                    <td>${produto.motivo}</td>
                    <td>R$ ${(
                      produto.quantidade * produto.valor_unitario
                    ).toFixed(2)}</td>
                  </tr>
                `
                  )
                  .join("")}
              </tbody>
            </table>
          </div>
        </div>
        
        ${
          detalhes.utilizacao
            ? `
          <div class="detalhes-secao">
            <h3 class="detalhes-titulo">Utilização</h3>
            <div class="detalhes-linha">
              <div class="detalhes-grupo">
                <span class="detalhes-label">Pedido:</span>
                <span class="detalhes-valor">${
                  detalhes.utilizacao.pedido
                }</span>
              </div>
              <div class="detalhes-grupo">
                <span class="detalhes-label">Data:</span>
                <span class="detalhes-valor">${detalhes.utilizacao.data}</span>
              </div>
            </div>
            <div class="detalhes-linha">
              <div class="detalhes-grupo">
                <span class="detalhes-label">Valor Utilizado:</span>
                <span class="detalhes-valor">R$ ${detalhes.utilizacao.valor.toFixed(
                  2
                )}</span>
              </div>
            </div>
          </div>
        `
            : ""
        }
        
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
      imprimirValeTroca(detalhes.codigo);
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}

function imprimirValeTroca(codigo) {
  console.log(`Imprimindo vale-troca: ${codigo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/vales-troca/${codigo}/imprimir`)
  //   .then(response => response.blob())
  //   .then(blob => {
  //     const url = URL.createObjectURL(blob);
  //     window.open(url, '_blank');
  //   });

  // Simulação de impressão
  alert(`Vale-troca ${codigo} enviado para impressão!`);
}
```

### Formulário de Devolução

```javascript
// Código para formulário de devolução
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioDevolucao = document.querySelector(
    ".formulario-devolucao-container"
  );
  if (!formularioDevolucao) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data_devolucao").value = hoje;

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação da devolução? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/devolucoes_vendas";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-devolucao-container");

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

    // Verifica se há produtos na devolução
    const produtos = document.querySelectorAll(
      ".tabela-produtos tbody tr:not(.linha-adicionar)"
    );
    if (produtos.length === 0) {
      alert("Adicione pelo menos um produto à devolução");
      return;
    }

    // Coleta os dados do formulário
    const devolucao = {
      data_devolucao: document.querySelector("#data_devolucao").value,
      pedido: document.querySelector("#pedido").value,
      nota_fiscal: document.querySelector("#nota_fiscal").value,
      cliente: document.querySelector("#cliente").value,
      situacao: document.querySelector("#situacao").value,
      produtos: [],
      forma_devolucao: document.querySelector("#forma_devolucao").value,
      observacoes: document.querySelector("#observacoes").value,
    };

    // Adiciona dados específicos da forma de devolução
    if (devolucao.forma_devolucao === "vale_troca") {
      devolucao.validade_vale = document.querySelector("#validade_vale").value;
    } else if (devolucao.forma_devolucao === "estorno") {
      devolucao.forma_pagamento =
        document.querySelector("#forma_pagamento").value;
    }

    // Coleta os produtos
    document
      .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
      .forEach((linha) => {
        const produto = {
          produto: linha.querySelector(".coluna-produto input").value,
          quantidade: parseFloat(
            linha.querySelector(".coluna-quantidade input").value
          ),
          valor_unitario: parseFloat(
            linha.querySelector(".coluna-unitario input").value
          ),
          motivo: linha.querySelector(".coluna-motivo select").value,
          total: parseFloat(
            linha.querySelector(".coluna-total").getAttribute("data-valor")
          ),
        };

        devolucao.produtos.push(produto);
      });

    // Envia para a API
    console.log("Salvando devolução:", devolucao);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Devolução salva com sucesso!");
      window.location.href = "/devolucoes_vendas";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/devolucoes', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(devolucao)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Devolução salva com sucesso!');
    //     window.location.href = '/devolucoes_vendas';
    //   } else {
    //     throw new Error('Erro ao salvar devolução');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar devolução: ${error.message}`);
    // });
  });

  // Busca de pedido
  document.querySelector("#pedido").addEventListener("focus", function () {
    // Abre modal de busca de pedidos
    const modal = document.createElement("div");
    modal.classList.add("modal-busca-pedido");
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Selecionar Pedido</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="campo-busca">
            <input type="text" class="formulario-input input-busca-pedido" placeholder="Buscar pedido...">
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
          <div class="lista-pedidos">
            <table class="tabela-selecao-pedidos">
              <thead>
                <tr>
                  <th>Número</th>
                  <th>Data</th>
                  <th>Cliente</th>
                  <th>Valor</th>
                  <th></th>
                </tr>
              </thead>
              <tbody>
                <tr data-pedido-id="1001">
                  <td>1001</td>
                  <td>15/05/2025</td>
                  <td>Cliente A</td>
                  <td>R$ 1.500,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-pedido-id="1002">
                  <td>1002</td>
                  <td>16/05/2025</td>
                  <td>Cliente B</td>
                  <td>R$ 2.000,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-pedido-id="1003">
                  <td>1003</td>
                  <td>17/05/2025</td>
                  <td>Cliente C</td>
                  <td>R$ 1.000,00</td>
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
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    modal.querySelectorAll(".botao-selecionar").forEach((botao) => {
      botao.addEventListener("click", function () {
        const linha = this.closest("tr");
        const pedidoId = linha.getAttribute("data-pedido-id");
        const pedidoNumero = linha.querySelector("td:first-child").textContent;
        const clienteNome = linha.querySelector("td:nth-child(3)").textContent;

        // Preenche os campos
        document.querySelector("#pedido").value = pedidoNumero;
        document.querySelector("#cliente").value = clienteNome;

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

  // Botão de adicionar produto
  document
    .querySelector(".botao-adicionar-produto")
    .addEventListener("click", function () {
      adicionarLinhaProduto();
    });

  // Controle de forma de devolução
  document
    .querySelector("#forma_devolucao")
    .addEventListener("change", function () {
      const formaDevolucao = this.value;
      const formaValeTroca = document.querySelector(".forma-vale-troca");
      const formaEstorno = document.querySelector(".forma-estorno");

      // Esconde todos os campos específicos
      formaValeTroca.style.display = "none";
      formaEstorno.style.display = "none";

      // Mostra os campos específicos da forma selecionada
      if (formaDevolucao === "vale_troca") {
        formaValeTroca.style.display = "block";

        // Define a validade padrão (3 meses a partir de hoje)
        const hoje = new Date();
        const validade = new Date(hoje);
        validade.setMonth(validade.getMonth() + 3);
        document.querySelector("#validade_vale").value = validade
          .toISOString()
          .split("T")[0];
      } else if (formaDevolucao === "estorno") {
        formaEstorno.style.display = "block";
      }
    });
});

function adicionarLinhaProduto() {
  const tbody = document.querySelector(".tabela-produtos tbody");
  const linhaAdicionar = document.querySelector(".linha-adicionar");

  const tr = document.createElement("tr");
  tr.innerHTML = `
    <td class="coluna-produto">
      <div class="campo-busca">
        <input type="text" class="formulario-input input-produto" placeholder="Buscar produto..." required>
        <button class="botao-busca">
          <span class="icone icone-busca"></span>
        </button>
      </div>
    </td>
    <td class="coluna-quantidade">
      <input type="number" class="formulario-input input-quantidade" value="1" min="1" step="1" required>
    </td>
    <td class="coluna-unitario">
      <input type="number" class="formulario-input input-unitario" value="0.00" min="0" step="0.01" required>
    </td>
    <td class="coluna-motivo">
      <select class="formulario-select input-motivo" required>
        <option value="">Selecione...</option>
        <option value="defeito">Defeito</option>
        <option value="troca_tamanho">Troca de Tamanho</option>
        <option value="troca_cor">Troca de Cor</option>
        <option value="arrependimento">Arrependimento</option>
        <option value="produto_errado">Produto Errado</option>
        <option value="outro">Outro</option>
      </select>
    </td>
    <td class="coluna-total" data-valor="0.00">R$ 0,00</td>
    <td class="coluna-acoes">
      <button class="botao-remover">
        <span class="icone icone-remover"></span>
      </button>
    </td>
  `;

  tbody.insertBefore(tr, linhaAdicionar);

  // Adiciona eventos
  const inputProduto = tr.querySelector(".input-produto");
  inputProduto.addEventListener("focus", function () {
    // Abre modal de busca de produtos
    buscarProduto(this);
  });

  const inputQuantidade = tr.querySelector(".input-quantidade");
  const inputUnitario = tr.querySelector(".input-unitario");

  [inputQuantidade, inputUnitario].forEach((input) => {
    input.addEventListener("change", function () {
      atualizarTotalLinha(tr);
      atualizarTotalDevolucao();
    });
  });

  tr.querySelector(".botao-remover").addEventListener("click", function () {
    tr.remove();
    atualizarTotalDevolucao();
  });

  // Foca no campo de produto
  inputProduto.focus();
}

function buscarProduto(input) {
  // Simulação de busca de produto
  const produtos = [
    { id: 1, codigo: "P001", descricao: "Produto 1", preco: 100.0 },
    { id: 2, codigo: "P002", descricao: "Produto 2", preco: 200.0 },
    { id: 3, codigo: "P003", descricao: "Produto 3", preco: 150.0 },
  ];

  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Produto</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="campo-busca">
          <input type="text" class="formulario-input input-busca-produto" placeholder="Buscar produto...">
          <button class="botao-busca">
            <span class="icone icone-busca"></span>
          </button>
        </div>
        <div class="lista-produtos">
          <table class="tabela-selecao-produtos">
            <thead>
              <tr>
                <th>Código</th>
                <th>Descrição</th>
                <th>Preço</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              ${produtos
                .map(
                  (produto) => `
                <tr data-produto-id="${produto.id}">
                  <td>${produto.codigo}</td>
                  <td>${produto.descricao}</td>
                  <td>R$ ${produto.preco.toFixed(2)}</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
              `
                )
                .join("")}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal.querySelectorAll(".botao-selecionar").forEach((botao) => {
    botao.addEventListener("click", function () {
      const linha = this.closest("tr");
      const produtoId = linha.getAttribute("data-produto-id");
      const produto = produtos.find((p) => p.id.toString() === produtoId);

      // Preenche os campos
      const tr = input.closest("tr");
      input.value = produto.descricao;
      tr.querySelector(".input-unitario").value = produto.preco.toFixed(2);

      // Atualiza os totais
      atualizarTotalLinha(tr);
      atualizarTotalDevolucao();

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
}

function atualizarTotalLinha(linha) {
  const quantidade = parseFloat(linha.querySelector(".input-quantidade").value);
  const valorUnitario = parseFloat(
    linha.querySelector(".input-unitario").value
  );

  const total = quantidade * valorUnitario;
  linha.querySelector(".coluna-total").textContent = `R$ ${total.toFixed(2)}`;
  linha
    .querySelector(".coluna-total")
    .setAttribute("data-valor", total.toFixed(2));
}

function atualizarTotalDevolucao() {
  let total = 0;

  // Calcula o total
  document
    .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
    .forEach((linha) => {
      const valorLinha = parseFloat(
        linha.querySelector(".coluna-total").getAttribute("data-valor")
      );
      total += valorLinha;
    });

  // Atualiza o valor no rodapé
  document.querySelector(
    ".tabela-produtos tfoot .rodape-valor"
  ).textContent = `R$ ${total.toFixed(2)}`;
}
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
  }

  .abas-container {
    flex-wrap: wrap;
  }

  .aba {
    flex-grow: 1;
    text-align: center;
  }

  .coluna-nota,
  .coluna-situacao {
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

  .coluna-data,
  .coluna-pedido {
    display: none;
  }

  .paginacao-pagina {
    display: none;
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

### Indicadores de Status

```css
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

## Fluxos de Navegação

1. **Listagem de Devoluções**:

   - O usuário acessa o módulo "Devoluções de venda"
   - Visualiza a lista de devoluções
   - Pode filtrar por situação usando as abas
   - Pode pesquisar por cliente, pedido ou nota fiscal
   - Pode aplicar filtros adicionais por período

2. **Criação de Devolução**:

   - O usuário clica no botão "Incluir devolução"
   - Seleciona um pedido
   - Os dados do cliente são preenchidos automaticamente
   - Adiciona produtos à devolução
   - Seleciona a forma de devolução (vale-troca, estorno ou troca)
   - Salva a devolução

3. **Gerenciamento de Vales-Troca**:

   - O usuário clica no botão "Gerenciar vales-troca"
   - Visualiza a lista de vales-troca
   - Pode pesquisar por código ou cliente
   - Pode visualizar detalhes de um vale-troca
   - Pode imprimir um vale-troca

4. **Visualização de Detalhes**:
   - O usuário clica em uma devolução na lista
   - Visualiza os detalhes da devolução
   - Pode ver os produtos devolvidos
   - Pode ver a forma de devolução
   - Pode imprimir a devolução

## Conclusão

O módulo "Devoluções de Venda" do ERP Revo apresenta uma interface completa e funcional para gerenciamento de devoluções de produtos vendidos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, criar e gerenciar devoluções de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento de devoluções, como criação de devoluções, gerenciamento de vales-troca e impressão de documentos, atendendo às necessidades de negócios que precisam lidar com devoluções de produtos.
