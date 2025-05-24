# Análise do Módulo Ordens de Compra - ERP Revo

## Estrutura Geral

O módulo "Ordens de Compra" do ERP Revo apresenta uma interface organizada para gerenciamento de pedidos de compra a fornecedores, com uma estrutura que facilita a visualização, criação e acompanhamento das ordens. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma tabela de dados com informações das ordens cadastradas.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Ordens de compra"
- Botão para imprimir
- Botão para incluir nova ordem de compra
- Menu de ações adicionais

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Ordens de compra</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir ordem de compra</span>
    </a>
    <div class="dropdown">
      <button class="botao botao-secundario dropdown-toggle" id="btn-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
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
  border-bottom: 1px solid #e0e0e0;
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
  text-decoration: none;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao .icone {
  margin-right: 8px;
}

.dropdown {
  position: relative;
}

.dropdown-toggle {
  padding-right: 28px;
}

.dropdown-toggle .icone-seta-baixo {
  position: absolute;
  right: 12px;
  top: 50%;
  transform: translateY(-50%);
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar as ordens de compra:

- Campo de texto para pesquisa por fornecedor, número do pedido ou ordem
- Botão de busca
- Filtro por período

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por fornecedor, nº do pedido ou ordem de compra"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="periodo">
      <span class="icone icone-calendario"></span>
      <span class="texto">por período</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.barra-pesquisa {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #f5f5f5;
  border-bottom: 1px solid #e0e0e0;
}

.campo-pesquisa {
  flex: 1;
  position: relative;
  max-width: 600px;
}

.input-pesquisa {
  width: 100%;
  padding: 10px 16px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.input-pesquisa::placeholder {
  color: #999999;
}

.botao-busca {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  cursor: pointer;
  color: #666666;
}

.filtros-rapidos {
  display: flex;
  gap: 8px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  background-color: #f5f5f5;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-item:hover {
  background-color: #e6f7ff;
}

.filtro-item .icone {
  margin-right: 6px;
  font-size: 16px;
}
```

### Filtros por Status

Os filtros permitem visualizar ordens de compra por status:

- Todos
- Em aberto
- Em andamento
- Atendidas
- Canceladas

**Estrutura HTML:**

```html
<div class="filtros-status">
  <a href="#" class="filtro-status ativo" data-status="todos">
    <span class="indicador indicador-todos"></span>
    <span class="texto">Todos</span>
    <span class="contador">01</span>
  </a>
  <a href="#" class="filtro-status" data-status="em-aberto">
    <span class="indicador indicador-aberto"></span>
    <span class="texto">Em aberto</span>
  </a>
  <a href="#" class="filtro-status" data-status="em-andamento">
    <span class="indicador indicador-andamento"></span>
    <span class="texto">Em andamento</span>
  </a>
  <a href="#" class="filtro-status" data-status="atendidas">
    <span class="indicador indicador-atendidas"></span>
    <span class="texto">Atendidas</span>
  </a>
  <a href="#" class="filtro-status" data-status="canceladas">
    <span class="indicador indicador-canceladas"></span>
    <span class="texto">Canceladas</span>
    <span class="contador">01</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.filtros-status {
  display: flex;
  gap: 4px;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtro-status {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  background-color: #ffffff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease, border-color 0.2s ease;
}

.filtro-status.ativo {
  background-color: #f5f5f5;
  border-color: #e0e0e0;
}

.filtro-status:hover:not(.ativo) {
  background-color: #f5f5f5;
}

.indicador {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-todos {
  background-color: #999999;
}

.indicador-aberto {
  background-color: #722ed1;
}

.indicador-andamento {
  background-color: #fa8c16;
}

.indicador-atendidas {
  background-color: #52c41a;
}

.indicador-canceladas {
  background-color: #f5222d;
}

.contador {
  margin-left: 6px;
  font-size: 12px;
  color: #666666;
}
```

### Tabela de Ordens de Compra

A tabela exibe as ordens de compra cadastradas com suas informações principais:

- Checkbox para seleção
- Número da ordem
- Data
- Data prevista
- Fornecedor
- Valor total
- Marcadores
- Integrações

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-ordens">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-numero">
          Número
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-data">
          Data
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-previsto">
          Previsto
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-fornecedor">
          Fornecedor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-total">
          Total
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-marcadores">Marcadores</th>
        <th class="coluna-integracoes">Integrações</th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-ordem">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-numero">
          <a href="#/ordem/1" class="link-ordem">1</a>
        </td>
        <td class="coluna-data">05/12/2024</td>
        <td class="coluna-previsto"></td>
        <td class="coluna-fornecedor">CHAVEIRO IDEAL</td>
        <td class="coluna-total">100,00</td>
        <td class="coluna-marcadores"></td>
        <td class="coluna-integracoes"></td>
      </tr>
      <!-- Outras linhas de ordens de compra -->
    </tbody>
  </table>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  overflow-x: auto;
  background-color: #ffffff;
}

.tabela-ordens {
  width: 100%;
  border-collapse: collapse;
}

.tabela-ordens th,
.tabela-ordens td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-ordens th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
  white-space: nowrap;
}

.coluna-selecao {
  width: 40px;
}

.coluna-numero {
  width: 80px;
}

.coluna-data,
.coluna-previsto {
  width: 120px;
}

.coluna-fornecedor {
  min-width: 200px;
}

.coluna-total {
  width: 120px;
}

.coluna-marcadores,
.coluna-integracoes {
  width: 100px;
}

.icone-ordenacao {
  display: inline-block;
  width: 12px;
  height: 12px;
  margin-left: 4px;
  vertical-align: middle;
  background-image: url("path/to/sort-icon.svg");
  background-repeat: no-repeat;
  background-position: center;
}

.link-ordem {
  color: #1890ff;
  text-decoration: none;
}

.link-ordem:hover {
  text-decoration: underline;
}
```

### Resumo de Totais

O rodapé exibe um resumo dos totais das ordens de compra:

**Estrutura HTML:**

```html
<div class="resumo-totais">
  <div class="resumo-item">
    <div class="resumo-label">quantidade</div>
    <div class="resumo-valor">1</div>
  </div>
  <div class="resumo-item">
    <div class="resumo-label">valor total (R$)</div>
    <div class="resumo-valor">100,00</div>
  </div>
</div>
```

**Estilos CSS:**

```css
.resumo-totais {
  display: flex;
  justify-content: flex-end;
  gap: 24px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #e0e0e0;
}

.resumo-item {
  text-align: right;
}

.resumo-label {
  font-size: 12px;
  color: #999999;
  margin-bottom: 4px;
}

.resumo-valor {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
}
```

### Botão Voltar ao Topo

Um botão fixo permite voltar ao topo da página:

**Estrutura HTML:**

```html
<button class="botao-voltar-topo" title="Voltar ao topo">
  <span class="icone icone-seta-cima"></span>
</button>
```

**Estilos CSS:**

```css
.botao-voltar-topo {
  position: fixed;
  bottom: 24px;
  right: 24px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #1890ff;
  color: white;
  border: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background-color 0.2s ease;
  z-index: 100;
}

.botao-voltar-topo:hover {
  background-color: #40a9ff;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar ordens de compra:

```javascript
// Código para pesquisa de ordens de compra
document
  .querySelector(".input-pesquisa")
  .addEventListener("keyup", function (e) {
    if (e.key === "Enter") {
      realizarPesquisa(this.value);
    }
  });

document.querySelector(".botao-busca").addEventListener("click", function () {
  const termoPesquisa = document.querySelector(".input-pesquisa").value;
  realizarPesquisa(termoPesquisa);
});

function realizarPesquisa(termo) {
  // Lógica para filtrar ordens pelo termo de pesquisa
  fetch(`/api/pedidos_compra/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaOrdens(data);
    });
}

// Código para filtro por período
document
  .querySelector('.filtro-item[data-filtro="periodo"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre modal de seleção de período
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Filtrar por Período</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="data_inicial">Data Inicial</label>
          <input type="date" id="data_inicial" name="data_inicial">
        </div>
        <div class="form-grupo">
          <label for="data_final">Data Final</label>
          <input type="date" id="data_final" name="data_final">
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input type="checkbox" id="apenas_periodo" name="apenas_periodo">
            <label for="apenas_periodo">Apenas ordens criadas neste período</label>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-limpar-periodo">Limpar</button>
        <button class="botao botao-primario" id="btn-aplicar-periodo">Aplicar</button>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    modal.querySelector("#btn-limpar-periodo").addEventListener("click", () => {
      document.querySelector("#data_inicial").value = "";
      document.querySelector("#data_final").value = "";
      document.querySelector("#apenas_periodo").checked = false;
    });

    modal
      .querySelector("#btn-aplicar-periodo")
      .addEventListener("click", () => {
        // Coleta os dados do formulário
        const dataInicial = document.querySelector("#data_inicial").value;
        const dataFinal = document.querySelector("#data_final").value;
        const apenasPeriodo = document.querySelector("#apenas_periodo").checked;

        // Aplica o filtro por período
        filtrarPorPeriodo(dataInicial, dataFinal, apenasPeriodo);

        // Fecha o modal
        document.body.removeChild(modal);
      });
  });

function filtrarPorPeriodo(dataInicial, dataFinal, apenasPeriodo) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();

  if (dataInicial) {
    params.append("data_inicial", dataInicial);
  }

  if (dataFinal) {
    params.append("data_final", dataFinal);
  }

  if (apenasPeriodo) {
    params.append("apenas_periodo", "true");
  }

  // Faz a requisição com os filtros
  fetch(`/api/pedidos_compra?${params.toString()}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaOrdens(data);
    });
}
```

### Filtros por Status

Os filtros por status permitem visualizar ordens em diferentes estados:

```javascript
// Código para filtrar por status
document.querySelectorAll(".filtro-status").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-status").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por status
    const status = this.getAttribute("data-status");
    filtrarPorStatus(status);
  });
});

function filtrarPorStatus(status) {
  // Lógica para filtrar ordens por status
  let url = "/api/pedidos_compra";

  if (status !== "todos") {
    url += `?status=${status}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaOrdens(data);
    });
}
```

### Seleção de Ordens

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de ordens
const checkboxTodos = document.querySelector('.checkbox-selecionar-todos');
const checkboxesIndividuais = document.querySelectorAll('.checkbox-selecionar');

checkboxTodos.addEventListener('change', function() {
  const isChecked = this.checked;

  // Marca ou desmarca todos os checkboxes individuais
  checkboxesIndividuais.forEach(checkbox => {
    checkbox.checked = isChecked;
  });

  // Atualiza o estado de seleção

(Content truncated due to size limit. Use line ranges to read in chunks)
```
