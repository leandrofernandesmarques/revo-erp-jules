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
          <input
            type="text"
            id="numero"
            class="formulario-input"
            value="1"
            readonly
          />
        </div>

        <div class="formulario-grupo">
          <label for="data" class="formulario-label">Data</label>
          <input type="date" id="data" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="validade" class="formulario-label">Validade</label>
          <input type="date" id="validade" class="formulario-input" required />
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
            <input
              type="text"
              id="cliente"
              class="formulario-input"
              placeholder="Buscar cliente..."
              required
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="contato" class="formulario-label">Contato</label>
          <input type="text" id="contato" class="formulario-input" />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="email" class="formulario-label">E-mail</label>
          <input type="email" id="email" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="telefone" class="formulario-label">Telefone</label>
          <input type="tel" id="telefone" class="formulario-input" />
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
              <th class="coluna-desconto">Desconto</th>
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
              <td colspan="3"></td>
              <td class="rodape-label">Subtotal:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Desconto:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Total:</td>
              <td class="rodape-valor total">R$ 0,00</td>
              <td></td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Observações</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
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
.formulario-proposta-container {
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

.coluna-quantidade,
.coluna-unitario,
.coluna-desconto,
.coluna-total {
  width: 120px;
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

.rodape-valor.total {
  font-size: 16px;
  color: #1890ff;
}
```

## Interações JavaScript

### Dropdown de Mais Ações

```javascript
// Código para dropdown de mais ações
document
  .querySelector("#btn-mais-acoes")
  .addEventListener("click", function (e) {
    e.preventDefault();
    const dropdown = this.closest(".dropdown");
    dropdown.classList.toggle("ativo");

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (!dropdown.contains(e.target)) {
        dropdown.classList.remove("ativo");
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });
```

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

    // Atualiza o filtro ativo
    const filtroAtivo = document.querySelector(".filtro-ativo");
    if (this.classList.contains("aba-mais")) {
      filtroAtivo.style.display = "none";
    } else {
      filtroAtivo.style.display = "inline-flex";
      filtroAtivo.querySelector(
        ".texto"
      ).textContent = `Situação: ${this.textContent.trim()}`;
    }

    // Carrega as propostas com o filtro selecionado
    carregarPropostas(this.textContent.trim());
  });
});

// Código para remover filtro
document
  .querySelector(".botao-remover-filtro")
  .addEventListener("click", function () {
    // Ativa a aba "Todas"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim() === "Todas") {
        aba.classList.add("aba-ativa");
      }
    });

    // Esconde o filtro ativo
    document.querySelector(".filtro-ativo").style.display = "none";

    // Carrega todas as propostas
    carregarPropostas("Todas");
  });

function carregarPropostas(filtro) {
  // Simulação de carregamento de propostas
  console.log(`Carregando propostas com filtro: ${filtro}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/propostas?filtro=' + encodeURIComponent(filtro))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaPropostas(data);
  //   });
}
```

### Pesquisa

```javascript
// Código para pesquisa
document
  .querySelector(".input-pesquisa")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      pesquisarPropostas(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarPropostas(termoPesquisa);
  });

function pesquisarPropostas(termo) {
  if (!termo) return;

  console.log(`Pesquisando propostas com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/propostas/pesquisa?termo=' + encodeURIComponent(termo))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaPropostas(data);
  //   });
}
```

### Criação de Proposta

```javascript
// Código para botões de incluir proposta
document
  .querySelector("#btn-incluir-proposta")
  .addEventListener("click", function () {
    window.location.href = "/orcamentos/novo";
  });

document
  .querySelector("#btn-incluir-proposta-vazio")
  .addEventListener("click", function () {
    window.location.href = "/orcamentos/novo";
  });

// Código para formulário de proposta
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioProposta = document.querySelector(
    ".formulario-proposta-container"
  );
  if (!formularioProposta) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data").value = hoje;

  // Define a validade para 15 dias após a data atual
  const validade = new Date();
  validade.setDate(validade.getDate() + 15);
  document.querySelector("#validade").value = validade
    .toISOString()
    .split("T")[0];

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação da proposta? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/orcamentos";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-proposta-container");

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
    const proposta = {
      numero: document.querySelector("#numero").value,
      data: document.querySelector("#data").value,
      validade: document.querySelector("#validade").value,
      situacao: document.querySelector("#situacao").value,
      cliente: document.querySelector("#cliente").value,
      contato: document.querySelector("#contato").value,
      email: document.querySelector("#email").value,
      telefone: document.querySelector("#telefone").value,
      observacoes: document.querySelector("#observacoes").value,
      produtos: [],
    };

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
          desconto: parseFloat(
            linha.querySelector(".coluna-desconto input").value || 0
          ),
          total: parseFloat(
            linha.querySelector(".coluna-total").getAttribute("data-valor")
          ),
        };

        proposta.produtos.push(produto);
      });

    // Envia para a API
    console.log("Salvando proposta:", proposta);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Proposta salva com sucesso!");
      window.location.href = "/orcamentos";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/propostas', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(proposta)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Proposta salva com sucesso!');
    //     window.location.href = '/orcamentos';
    //   } else {
    //     throw new Error('Erro ao salvar proposta');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar proposta: ${error.message}`);
    // });
  });

  // Botão de adicionar produto
  document
    .querySelector(".botao-adicionar-produto")
    .addEventListener("click", function () {
      adicionarLinhaProduto();
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
    <td class="coluna-desconto">
      <input type="number" class="formulario-input input-desconto" value="0.00" min="0" step="0.01">
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
  const inputDesconto = tr.querySelector(".input-desconto");

  [inputQuantidade, inputUnitario, inputDesconto].forEach((input) => {
    input.addEventListener("change", function () {
      atualizarTotalLinha(tr);
      atualizarTotais();
    });
  });

  tr.querySelector(".botao-remover").addEventListener("click", function () {
    tr.remove();
    atualizarTotais();
  });

  // Foca no campo de produto
  inputProduto.focus();
}

function buscarProduto(input) {
  // Simulação de busca de produto
  const produtos = [
    {
      id: 1,
      codigo: "P001",
      descricao: "Produto 1",
      preco: 100.0,
      estoque: 50,
    },
    {
      id: 2,
      codigo: "P002",
      descricao: "Produto 2",
      preco: 200.0,
      estoque: 30,
    },
    {
      id: 3,
      codigo: "P003",
      descricao: "Produto 3",
      preco: 150.0,
      estoque: 20,
    },
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
                <th>Estoque</th>
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
                  <td>${produto.estoque}</td>
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
      atualizarTotais();

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
  const desconto = parseFloat(
    linha.querySelector(".input-desconto").value || 0
  );

  const total = quantidade * valorUnitario - desconto;
  linha.querySelector(".coluna-total").textContent = `R$ ${total.toFixed(2)}`;
  linha
    .querySelector(".coluna-total")
    .setAttribute("data-valor", total.toFixed(2));
}

function atualizarTotais() {
  let subtotal = 0;
  let desconto = 0;

  // Calcula o subtotal e desconto
  document
    .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
    .forEach((linha) => {
      const quantidade = parseFloat(
        linha.querySelector(".input-quantidade").value
      );
      const valorUnitario = parseFloat(
        linha.querySelector(".input-unitario").value
      );
      const descontoLinha = parseFloat(
        linha.querySelector(".input-desconto").value || 0
      );

      subtotal += quantidade * valorUnitario;
      desconto += descontoLinha;
    });

  // Atualiza os valores no rodapé
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(1) .rodape-valor"
  ).textContent = `R$ ${subtotal.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(2) .rodape-valor"
  ).textContent = `R$ ${desconto.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(3) .rodape-valor"
  ).textContent = `R$ ${(subtotal - desconto).toFixed(2)}`;
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .cards-info {
    flex-direction: column;
    align-items: center;
  }

  .card-info {
    max-width: 100%;
  }

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
  .modulo-cabecalho,
  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-end;
  }

  .pesquisa-filtros-container {
    flex-direction: column;
  }

  .pesquisa-container {
    width: 100%;
    max-width: none;
    margin-bottom: 16px;
  }

  .abas-container {
    flex-wrap: wrap;
  }

  .aba {
    flex-grow: 1;
    text-align: center;
  }

  .coluna-data,
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

  .coluna-situacao {
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

## Fluxos de Navegação

1. **Listagem de Propostas**:

   - O usuário acessa o módulo "Propostas Comerciais"
   - Visualiza a lista de propostas (ou mensagem de lista vazia)
   - Pode filtrar por situação usando as abas
   - Pode pesquisar por cliente ou número
   - Pode aplicar filtros adicionais

2. **Criação de Proposta**:

   - O usuário clica no botão "Incluir proposta"
   - Preenche as informações gerais da proposta
   - Seleciona um cliente
   - Adiciona produtos à proposta
   - Preenche observações (opcional)
   - Salva a proposta

3. **Edição de Proposta**:

   - O usuário clica em uma proposta na lista
   - Visualiza os detalhes da proposta
   - Edita as informações necessárias
   - Salva as alterações

4. **Impressão de Proposta**:
   - O usuário seleciona uma ou mais propostas
   - Clica no botão "Imprimir"
   - Visualiza a prévia da impressão
   - Confirma a impressão

## Conclusão

O módulo "Propostas Comerciais" do ERP Revo apresenta uma interface organizada e funcional para gerenciamento de propostas e orçamentos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, criar e editar propostas de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento de propostas comerciais, como criação de orçamentos, acompanhamento de status de negociação e conversão de propostas em pedidos de venda, atendendo às necessidades de negócios que trabalham com vendas consultivas ou personalizadas.
