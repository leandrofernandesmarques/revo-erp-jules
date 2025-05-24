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
const checkboxTodos = document.querySelector(".checkbox-selecionar-todos");
const checkboxesIndividuais = document.querySelectorAll(".checkbox-selecionar");

checkboxTodos.addEventListener("change", function () {
  const isChecked = this.checked;

  // Marca ou desmarca todos os checkboxes individuais
  checkboxesIndividuais.forEach((checkbox) => {
    checkbox.checked = isChecked;
  });

  // Atualiza o estado de seleção
  atualizarEstadoSelecao();
});

checkboxesIndividuais.forEach((checkbox) => {
  checkbox.addEventListener("change", function () {
    // Verifica se todos estão marcados para atualizar o checkbox geral
    const todosMarcados = Array.from(checkboxesIndividuais).every(
      (cb) => cb.checked
    );
    checkboxTodos.checked = todosMarcados;

    // Atualiza o estado de seleção
    atualizarEstadoSelecao();
  });
});

function atualizarEstadoSelecao() {
  const selecionados = Array.from(checkboxesIndividuais).filter(
    (cb) => cb.checked
  );

  // Atualiza a interface com base na quantidade de itens selecionados
  if (selecionados.length > 0) {
    // Exibe barra de ações em lote
    exibirBarraAcoesLote(selecionados.length);
  } else {
    // Oculta barra de ações em lote
    ocultarBarraAcoesLote();
  }
}
```

### Ordenação de Colunas

As colunas da tabela podem ser ordenadas:

```javascript
// Código para ordenação de colunas
document.querySelectorAll('th[class^="coluna-"]').forEach((coluna) => {
  if (coluna.querySelector(".icone-ordenacao")) {
    coluna.addEventListener("click", function () {
      // Obtém o nome da coluna a partir da classe
      const classeColuna = Array.from(this.classList).find((classe) =>
        classe.startsWith("coluna-")
      );
      const nomeColuna = classeColuna.replace("coluna-", "");

      // Verifica se já está ordenado e em qual direção
      const direcaoAtual = this.getAttribute("data-ordem") || "nenhuma";
      let novaDirecao;

      if (direcaoAtual === "nenhuma") {
        novaDirecao = "asc";
      } else if (direcaoAtual === "asc") {
        novaDirecao = "desc";
      } else {
        novaDirecao = "nenhuma";
      }

      // Remove a ordenação de todas as colunas
      document.querySelectorAll('th[class^="coluna-"]').forEach((col) => {
        col.removeAttribute("data-ordem");
        col.querySelector(".icone-ordenacao")?.classList.remove("asc", "desc");
      });

      // Aplica a nova ordenação
      if (novaDirecao !== "nenhuma") {
        this.setAttribute("data-ordem", novaDirecao);
        this.querySelector(".icone-ordenacao").classList.add(novaDirecao);

        // Ordena a tabela
        ordenarTabela(nomeColuna, novaDirecao);
      } else {
        // Restaura a ordem original
        carregarOrdens();
      }
    });
  }
});

function ordenarTabela(coluna, direcao) {
  // Lógica para ordenar a tabela
  fetch(`/api/pedidos_compra?ordenar_por=${coluna}&direcao=${direcao}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaOrdens(data);
    });
}
```

### Inclusão de Nova Ordem de Compra

O botão de inclusão redireciona para o formulário de cadastro:

```javascript
// Código para inclusão de nova ordem de compra
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/pedidos_compra/novo";
});
```

### Impressão de Ordens

O botão de impressão permite gerar relatórios:

```javascript
// Código para impressão de ordens
document.querySelector("#btn-imprimir").addEventListener("click", function () {
  // Verifica se há ordens selecionadas
  const ordensSelecionadas = Array.from(
    document.querySelectorAll(".checkbox-selecionar:checked")
  ).map((checkbox) => {
    const linha = checkbox.closest("tr");
    return linha.querySelector(".link-ordem").textContent.trim();
  });

  if (ordensSelecionadas.length > 0) {
    // Abre modal de opções de impressão para ordens selecionadas
    abrirModalImpressaoSelecionadas(ordensSelecionadas);
  } else {
    // Abre modal de opções de impressão geral
    abrirModalImpressaoGeral();
  }
});

function abrirModalImpressaoSelecionadas(ordens) {
  // Abre modal para impressão de ordens selecionadas
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Imprimir Ordens Selecionadas</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <p class="modal-descricao">
          Você selecionou ${ordens.length} ${
    ordens.length === 1 ? "ordem" : "ordens"
  } de compra para impressão.
        </p>
        <div class="form-grupo">
          <label for="formato_impressao">Formato</label>
          <select id="formato_impressao" name="formato_impressao">
            <option value="pdf">PDF</option>
            <option value="excel">Excel</option>
          </select>
        </div>
        <div class="form-grupo">
          <div class="opcao-checkbox">
            <input type="checkbox" id="incluir_itens" name="incluir_itens" checked>
            <label for="incluir_itens">Incluir itens das ordens</label>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-impressao">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar-impressao">Imprimir</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-impressao")
    .addEventListener("click", () => {
      document.body.removeChild(modal);
    });

  modal
    .querySelector("#btn-confirmar-impressao")
    .addEventListener("click", () => {
      // Coleta os dados do formulário
      const formato = document.querySelector("#formato_impressao").value;
      const incluirItens = document.querySelector("#incluir_itens").checked;

      // Realiza a impressão
      imprimirOrdens(ordens, formato, incluirItens);

      // Fecha o modal
      document.body.removeChild(modal);
    });
}

function abrirModalImpressaoGeral() {
  // Abre modal para impressão geral
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Imprimir Relatório de Ordens</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="tipo_relatorio">Tipo de Relatório</label>
          <select id="tipo_relatorio" name="tipo_relatorio">
            <option value="completo">Relatório Completo</option>
            <option value="resumido">Relatório Resumido</option>
            <option value="analitico">Relatório Analítico</option>
          </select>
        </div>
        <div class="form-grupo">
          <label for="periodo_relatorio">Período</label>
          <select id="periodo_relatorio" name="periodo_relatorio">
            <option value="hoje">Hoje</option>
            <option value="ontem">Ontem</option>
            <option value="7dias">Últimos 7 dias</option>
            <option value="30dias">Últimos 30 dias</option>
            <option value="mes_atual">Mês atual</option>
            <option value="mes_anterior">Mês anterior</option>
            <option value="personalizado">Personalizado</option>
          </select>
        </div>
        <div class="periodo-personalizado" style="display: none;">
          <div class="form-grupo">
            <label for="data_inicial_relatorio">Data Inicial</label>
            <input type="date" id="data_inicial_relatorio" name="data_inicial_relatorio">
          </div>
          <div class="form-grupo">
            <label for="data_final_relatorio">Data Final</label>
            <input type="date" id="data_final_relatorio" name="data_final_relatorio">
          </div>
        </div>
        <div class="form-grupo">
          <label for="formato_relatorio">Formato</label>
          <select id="formato_relatorio" name="formato_relatorio">
            <option value="pdf">PDF</option>
            <option value="excel">Excel</option>
            <option value="csv">CSV</option>
          </select>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-relatorio">Cancelar</button>
        <button class="botao botao-primario" id="btn-gerar-relatorio">Gerar Relatório</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-relatorio")
    .addEventListener("click", () => {
      document.body.removeChild(modal);
    });

  // Exibe campos de período personalizado quando selecionado
  modal
    .querySelector("#periodo_relatorio")
    .addEventListener("change", function () {
      const periodoPersonalizado = modal.querySelector(
        ".periodo-personalizado"
      );

      if (this.value === "personalizado") {
        periodoPersonalizado.style.display = "block";
      } else {
        periodoPersonalizado.style.display = "none";
      }
    });

  modal.querySelector("#btn-gerar-relatorio").addEventListener("click", () => {
    // Coleta os dados do formulário
    const tipoRelatorio = document.querySelector("#tipo_relatorio").value;
    const periodoRelatorio = document.querySelector("#periodo_relatorio").value;
    const formatoRelatorio = document.querySelector("#formato_relatorio").value;

    let dataInicial = null;
    let dataFinal = null;

    if (periodoRelatorio === "personalizado") {
      dataInicial = document.querySelector("#data_inicial_relatorio").value;
      dataFinal = document.querySelector("#data_final_relatorio").value;

      if (!dataInicial || !dataFinal) {
        alert(
          "Preencha as datas inicial e final para o período personalizado."
        );
        return;
      }
    }

    // Gera o relatório
    gerarRelatorio(
      tipoRelatorio,
      periodoRelatorio,
      formatoRelatorio,
      dataInicial,
      dataFinal
    );

    // Fecha o modal
    document.body.removeChild(modal);
  });
}

function imprimirOrdens(ordens, formato, incluirItens) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();
  params.append("ordens", ordens.join(","));
  params.append("formato", formato);
  params.append("incluir_itens", incluirItens ? "true" : "false");

  // Abre a URL em uma nova janela/aba
  window.open(`/pedidos_compra/imprimir?${params.toString()}`, "_blank");
}

function gerarRelatorio(tipo, periodo, formato, dataInicial, dataFinal) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();
  params.append("tipo", tipo);
  params.append("periodo", periodo);
  params.append("formato", formato);

  if (dataInicial && dataFinal) {
    params.append("data_inicial", dataInicial);
    params.append("data_final", dataFinal);
  }

  // Abre a URL em uma nova janela/aba
  window.open(`/pedidos_compra/relatorio?${params.toString()}`, "_blank");
}
```

### Menu de Ações Adicionais

O menu de ações adicionais oferece opções extras:

```javascript
// Código para menu de ações adicionais
document.querySelector("#btn-acoes").addEventListener("click", function () {
  // Verifica se o dropdown já está aberto
  const dropdownExistente = document.querySelector(".dropdown-menu");

  if (dropdownExistente) {
    // Remove o dropdown existente
    document.body.removeChild(dropdownExistente);
    return;
  }

  // Cria o dropdown
  const dropdown = document.createElement("div");
  dropdown.classList.add("dropdown-menu");
  dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-acao="exportar">
      <span class="icone icone-exportar"></span>
      <span class="texto">Exportar ordens</span>
    </a>
    <a href="#" class="dropdown-item" data-acao="importar">
      <span class="icone icone-importar"></span>
      <span class="texto">Importar ordens</span>
    </a>
    <div class="dropdown-divider"></div>
    <a href="#" class="dropdown-item" data-acao="configuracoes">
      <span class="icone icone-configuracoes"></span>
      <span class="texto">Configurações</span>
    </a>
  `;

  // Posiciona o dropdown
  const rect = this.getBoundingClientRect();
  dropdown.style.top = `${rect.bottom}px`;
  dropdown.style.right = `${window.innerWidth - rect.right}px`;

  // Adiciona ao DOM
  document.body.appendChild(dropdown);

  // Adiciona eventos aos itens do dropdown
  dropdown.querySelectorAll(".dropdown-item").forEach((item) => {
    item.addEventListener("click", function (e) {
      e.preventDefault();

      const acao = this.getAttribute("data-acao");
      executarAcao(acao);

      // Remove o dropdown
      document.body.removeChild(dropdown);
    });
  });

  // Fecha o dropdown ao clicar fora
  document.addEventListener("click", function fecharDropdown(e) {
    if (
      !dropdown.contains(e.target) &&
      e.target !== document.querySelector("#btn-acoes")
    ) {
      document.body.removeChild(dropdown);
      document.removeEventListener("click", fecharDropdown);
    }
  });
});

function executarAcao(acao) {
  switch (acao) {
    case "exportar":
      abrirModalExportacao();
      break;
    case "importar":
      abrirModalImportacao();
      break;
    case "configuracoes":
      window.location.href = "/pedidos_compra/configuracoes";
      break;
  }
}
```

### Botão Voltar ao Topo

O botão permite voltar ao topo da página:

```javascript
// Código para botão voltar ao topo
const botaoVoltarTopo = document.querySelector(".botao-voltar-topo");

// Exibe ou oculta o botão conforme o scroll
window.addEventListener("scroll", function () {
  if (window.pageYOffset > 300) {
    botaoVoltarTopo.style.display = "flex";
  } else {
    botaoVoltarTopo.style.display = "none";
  }
});

// Ação de voltar ao topo
botaoVoltarTopo.addEventListener("click", function () {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
});
```

## Formulário de Cadastro de Ordem de Compra

Quando o usuário clica em "Incluir ordem de compra", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Nova Ordem de Compra</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-ordem">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Básicas</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="fornecedor">Fornecedor *</label>
            <select id="fornecedor" name="fornecedor" required>
              <option value="">Selecione...</option>
              <!-- Opções de fornecedores serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="data">Data *</label>
            <input type="date" id="data" name="data" required />
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="previsao">Previsão de Entrega</label>
            <input type="date" id="previsao" name="previsao" />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="observacoes">Observações</label>
            <textarea id="observacoes" name="observacoes" rows="3"></textarea>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Produtos</h2>
        <div class="form-linha">
          <button
            type="button"
            class="botao botao-secundario"
            id="btn-adicionar-produto"
          >
            <span class="icone icone-adicionar"></span>
            <span class="texto">Adicionar Produto</span>
          </button>
        </div>
        <div class="tabela-produtos-container">
          <table class="tabela-produtos-ordem">
            <thead>
              <tr>
                <th class="coluna-produto">Produto</th>
                <th class="coluna-quantidade">Quantidade</th>
                <th class="coluna-valor">Valor Unitário</th>
                <th class="coluna-desconto">Desconto</th>
                <th class="coluna-subtotal">Subtotal</th>
                <th class="coluna-acoes"></th>
              </tr>
            </thead>
            <tbody id="produtos-ordem">
              <!-- Produtos serão adicionados dinamicamente -->
            </tbody>
          </table>
        </div>
        <div class="form-linha totais-ordem">
          <div class="totais-item">
            <span class="totais-label">Subtotal:</span>
            <span class="totais-valor" id="subtotal-ordem">R$ 0,00</span>
          </div>
          <div class="totais-item">
            <span class="totais-label">Descontos:</span>
            <span class="totais-valor" id="descontos-ordem">R$ 0,00</span>
          </div>
          <div class="totais-item totais-item-destaque">
            <span class="totais-label">Total:</span>
            <span class="totais-valor" id="total-ordem">R$ 0,00</span>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Pagamento</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="condicao_pagamento">Condição de Pagamento</label>
            <select id="condicao_pagamento" name="condicao_pagamento">
              <option value="">Selecione...</option>
              <option value="a_vista">À Vista</option>
              <option value="30_dias">30 Dias</option>
              <option value="30_60_dias">30/60 Dias</option>
              <option value="personalizado">Personalizado</option>
            </select>
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="forma_pagamento">Forma de Pagamento</label>
            <select id="forma_pagamento" name="forma_pagamento">
              <option value="">Selecione...</option>
              <option value="boleto">Boleto</option>
              <option value="pix">PIX</option>
              <option value="transferencia">Transferência</option>
              <option value="cartao">Cartão de Crédito</option>
              <option value="dinheiro">Dinheiro</option>
            </select>
          </div>
        </div>
      </div>
    </form>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  background-color: #ffffff;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.formulario-titulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.formulario-acoes {
  display: flex;
  gap: 8px;
}

.formulario-corpo {
  padding: 24px;
}

.form-secao {
  margin-bottom: 32px;
  padding-bottom: 24px;
  border-bottom: 1px solid #f0f0f0;
}

.form-secao:last-child {
  border-bottom: none;
  margin-bottom: 0;
  padding-bottom: 0;
}

.form-secao-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 16px 0;
}

.form-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 16px;
}

.form-grupo {
  flex: 1;
  min-width: 200px;
}

.form-grupo-pequeno {
  flex: 0 0 150px;
}

.form-grupo-medio {
  flex: 0 0 300px;
}

.form-grupo label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input,
.form-grupo select,
.form-grupo textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.form-grupo input:focus,
.form-grupo select:focus,
.form-grupo textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.tabela-produtos-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.tabela-produtos-ordem {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos-ordem th,
.tabela-produtos-ordem td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos-ordem th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-produto {
  min-width: 250px;
}

.coluna-quantidade,
.coluna-valor,
.coluna-desconto,
.coluna-subtotal {
  width: 120px;
}

.coluna-acoes {
  width: 80px;
  text-align: right;
}

.totais-ordem {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 8px;
}

.totais-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.totais-label {
  font-size: 14px;
  color: #666666;
}

.totais-valor {
  font-size: 14px;
  color: #333333;
  min-width: 100px;
  text-align: right;
}

.totais-item-destaque .totais-label,
.totais-item-destaque .totais-valor {
  font-size: 16px;
  font-weight: 500;
  color: #1890ff;
}
```

## Interações JavaScript do Formulário

```javascript
// Código para manipulação do formulário de ordem de compra
document.addEventListener("DOMContentLoaded", function () {
  // Carrega a lista de fornecedores
  carregarFornecedores();

  // Define a data atual como padrão
  document.querySelector("#data").valueAsDate = new Date();

  // Botão para adicionar produto
  document
    .querySelector("#btn-adicionar-produto")
    .addEventListener("click", function () {
      abrirModalAdicionarProduto();
    });

  // Botão cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      // Confirma se há alterações não salvas
      if (formularioAlterado()) {
        if (confirm("Há alterações não salvas. Deseja realmente sair?")) {
          window.location.href = "/pedidos_compra";
        }
      } else {
        window.location.href = "/pedidos_compra";
      }
    });

  // Botão salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector("#form-ordem");
    if (form.checkValidity()) {
      salvarOrdem();
    } else {
      form.reportValidity();
    }
  });
});

function carregarFornecedores() {
  // Carrega a lista de fornecedores para o select
  fetch("/api/fornecedores")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#fornecedor");

      data.forEach((fornecedor) => {
        const option = document.createElement("option");
        option.value = fornecedor.id;
        option.textContent = fornecedor.nome;
        select.appendChild(option);
      });
    });
}

function abrirModalAdicionarProduto() {
  // Abre modal para adicionar produto
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Adicionar Produto</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="produto">Produto *</label>
          <select id="produto" name="produto" required>
            <option value="">Selecione...</option>
            <!-- Opções de produtos serão carregadas dinamicamente -->
          </select>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="quantidade">Quantidade *</label>
            <input type="number" id="quantidade" name="quantidade" min="1" step="1" value="1" required>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_unitario">Valor Unitário *</label>
            <input type="text" id="valor_unitario" name="valor_unitario" placeholder="0,00" required>
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="desconto">Desconto</label>
            <input type="text" id="desconto" name="desconto" placeholder="0,00">
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="subtotal">Subtotal</label>
            <input type="text" id="subtotal" name="subtotal" placeholder="0,00" readonly>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-produto">Cancelar</button>
        <button class="botao botao-primario" id="btn-adicionar">Adicionar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Carrega a lista de produtos
  carregarProdutos();

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-produto").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  // Calcula subtotal ao alterar quantidade, valor ou desconto
  const calcularSubtotal = () => {
    const quantidade =
      parseFloat(document.querySelector("#quantidade").value) || 0;
    const valorUnitario =
      parseFloat(
        document.querySelector("#valor_unitario").value.replace(",", ".")
      ) || 0;
    const desconto =
      parseFloat(document.querySelector("#desconto").value.replace(",", ".")) ||
      0;

    const subtotal = quantidade * valorUnitario - desconto;
    document.querySelector("#subtotal").value = subtotal
      .toFixed(2)
      .replace(".", ",");
  };

  modal
    .querySelector("#quantidade")
    .addEventListener("input", calcularSubtotal);
  modal
    .querySelector("#valor_unitario")
    .addEventListener("input", calcularSubtotal);
  modal.querySelector("#desconto").addEventListener("input", calcularSubtotal);

  // Formata valores monetários
  const formatarValor = (input) => {
    input.addEventListener("input", function () {
      let valor = this.value.replace(/\D/g, "");
      valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
      this.value = valor;
    });
  };

  formatarValor(modal.querySelector("#valor_unitario"));
  formatarValor(modal.querySelector("#desconto"));

  modal.querySelector("#btn-adicionar").addEventListener("click", () => {
    // Coleta os dados do formulário
    const produtoId = document.querySelector("#produto").value;
    const produtoNome = document.querySelector(
      "#produto option:checked"
    ).textContent;
    const quantidade = document.querySelector("#quantidade").value;
    const valorUnitario = document.querySelector("#valor_unitario").value;
    const desconto = document.querySelector("#desconto").value || "0,00";
    const subtotal = document.querySelector("#subtotal").value;

    if (produtoId && quantidade && valorUnitario) {
      // Adiciona o produto à tabela
      adicionarProdutoTabela(
        produtoId,
        produtoNome,
        quantidade,
        valorUnitario,
        desconto,
        subtotal
      );

      // Atualiza os totais
      atualizarTotaisOrdem();

      // Fecha o modal
      document.body.removeChild(modal);
    } else {
      alert("Preencha todos os campos obrigatórios.");
    }
  });
}

function carregarProdutos() {
  // Carrega a lista de produtos para o select
  fetch("/api/produtos")
    .then((response) => response.json())
    .then((data) => {
      const select = document.querySelector("#produto");

      data.forEach((produto) => {
        const option = document.createElement("option");
        option.value = produto.id;
        option.textContent = produto.nome;
        option.setAttribute("data-valor", produto.preco_custo);
        select.appendChild(option);
      });

      // Adiciona evento para preencher o valor unitário ao selecionar um produto
      select.addEventListener("change", function () {
        const option = this.options[this.selectedIndex];
        const valorPadrao = option.getAttribute("data-valor");

        if (valorPadrao) {
          document.querySelector("#valor_unitario").value = valorPadrao.replace(
            ".",
            ","
          );

          // Recalcula o subtotal
          const quantidade =
            parseFloat(document.querySelector("#quantidade").value) || 0;
          const valorUnitario = parseFloat(valorPadrao) || 0;
          const desconto =
            parseFloat(
              document.querySelector("#desconto").value.replace(",", ".")
            ) || 0;

          const subtotal = quantidade * valorUnitario - desconto;
          document.querySelector("#subtotal").value = subtotal
            .toFixed(2)
            .replace(".", ",");
        }
      });
    });
}

function adicionarProdutoTabela(
  id,
  nome,
  quantidade,
  valorUnitario,
  desconto,
  subtotal
) {
  const tbody = document.querySelector("#produtos-ordem");

  // Cria uma nova linha
  const tr = document.createElement("tr");
  tr.setAttribute("data-produto-id", id);

  tr.innerHTML = `
    <td class="coluna-produto">${nome}</td>
    <td class="coluna-quantidade">${quantidade}</td>
    <td class="coluna-valor">R$ ${valorUnitario}</td>
    <td class="coluna-desconto">R$ ${desconto}</td>
    <td class="coluna-subtotal">R$ ${subtotal}</td>
    <td class="coluna-acoes">
      <button type="button" class="botao-acao btn-editar-produto">
        <span class="icone icone-editar"></span>
      </button>
      <button type="button" class="botao-acao btn-remover-produto">
        <span class="icone icone-remover"></span>
      </button>
    </td>
  `;

  // Adiciona eventos aos botões
  tr.querySelector(".btn-editar-produto").addEventListener(
    "click",
    function () {
      editarProduto(tr);
    }
  );

  tr.querySelector(".btn-remover-produto").addEventListener(
    "click",
    function () {
      if (confirm("Deseja realmente remover este produto?")) {
        tr.remove();
        atualizarTotaisOrdem();
      }
    }
  );

  // Adiciona a linha à tabela
  tbody.appendChild(tr);
}

function editarProduto(linha) {
  // Obtém os dados do produto
  const id = linha.getAttribute("data-produto-id");
  const nome = linha.querySelector(".coluna-produto").textContent;
  const quantidade = linha.querySelector(".coluna-quantidade").textContent;
  const valorUnitario = linha
    .querySelector(".coluna-valor")
    .textContent.replace("R$ ", "");
  const desconto = linha
    .querySelector(".coluna-desconto")
    .textContent.replace("R$ ", "");
  const subtotal = linha
    .querySelector(".coluna-subtotal")
    .textContent.replace("R$ ", "");

  // Abre modal para editar produto
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Editar Produto</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label for="produto_edit">Produto *</label>
          <input type="text" id="produto_edit" name="produto_edit" value="${nome}" readonly>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="quantidade_edit">Quantidade *</label>
            <input type="number" id="quantidade_edit" name="quantidade_edit" min="1" step="1" value="${quantidade}" required>
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="valor_unitario_edit">Valor Unitário *</label>
            <input type="text" id="valor_unitario_edit" name="valor_unitario_edit" value="${valorUnitario}" required>
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="desconto_edit">Desconto</label>
            <input type="text" id="desconto_edit" name="desconto_edit" value="${desconto}">
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="subtotal_edit">Subtotal</label>
            <input type="text" id="subtotal_edit" name="subtotal_edit" value="${subtotal}" readonly>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-edicao">Cancelar</button>
        <button class="botao botao-primario" id="btn-salvar-edicao">Salvar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar-edicao").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  // Calcula subtotal ao alterar quantidade, valor ou desconto
  const calcularSubtotal = () => {
    const quantidade =
      parseFloat(document.querySelector("#quantidade_edit").value) || 0;
    const valorUnitario =
      parseFloat(
        document.querySelector("#valor_unitario_edit").value.replace(",", ".")
      ) || 0;
    const desconto =
      parseFloat(
        document.querySelector("#desconto_edit").value.replace(",", ".")
      ) || 0;

    const subtotal = quantidade * valorUnitario - desconto;
    document.querySelector("#subtotal_edit").value = subtotal
      .toFixed(2)
      .replace(".", ",");
  };

  modal
    .querySelector("#quantidade_edit")
    .addEventListener("input", calcularSubtotal);
  modal
    .querySelector("#valor_unitario_edit")
    .addEventListener("input", calcularSubtotal);
  modal
    .querySelector("#desconto_edit")
    .addEventListener("input", calcularSubtotal);

  // Formata valores monetários
  const formatarValor = (input) => {
    input.addEventListener("input", function () {
      let valor = this.value.replace(/\D/g, "");
      valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
      this.value = valor;
    });
  };

  formatarValor(modal.querySelector("#valor_unitario_edit"));
  formatarValor(modal.querySelector("#desconto_edit"));

  modal.querySelector("#btn-salvar-edicao").addEventListener("click", () => {
    // Coleta os dados do formulário
    const quantidade = document.querySelector("#quantidade_edit").value;
    const valorUnitario = document.querySelector("#valor_unitario_edit").value;
    const desconto = document.querySelector("#desconto_edit").value;
    const subtotal = document.querySelector("#subtotal_edit").value;

    if (quantidade && valorUnitario) {
      // Atualiza os dados na linha
      linha.querySelector(".coluna-quantidade").textContent = quantidade;
      linha.querySelector(".coluna-valor").textContent = `R$ ${valorUnitario}`;
      linha.querySelector(".coluna-desconto").textContent = `R$ ${desconto}`;
      linha.querySelector(".coluna-subtotal").textContent = `R$ ${subtotal}`;

      // Atualiza os totais
      atualizarTotaisOrdem();

      // Fecha o modal
      document.body.removeChild(modal);
    } else {
      alert("Preencha todos os campos obrigatórios.");
    }
  });
}

function atualizarTotaisOrdem() {
  // Calcula os totais da ordem
  let subtotal = 0;
  let descontos = 0;

  document.querySelectorAll("#produtos-ordem tr").forEach((linha) => {
    const valorSubtotal =
      parseFloat(
        linha
          .querySelector(".coluna-subtotal")
          .textContent.replace("R$ ", "")
          .replace(",", ".")
      ) || 0;
    const valorDesconto =
      parseFloat(
        linha
          .querySelector(".coluna-desconto")
          .textContent.replace("R$ ", "")
          .replace(",", ".")
      ) || 0;

    subtotal += valorSubtotal + valorDesconto;
    descontos += valorDesconto;
  });

  const total = subtotal - descontos;

  // Atualiza os valores na interface
  document.querySelector("#subtotal-ordem").textContent = `R$ ${subtotal
    .toFixed(2)
    .replace(".", ",")}`;
  document.querySelector("#descontos-ordem").textContent = `R$ ${descontos
    .toFixed(2)
    .replace(".", ",")}`;
  document.querySelector("#total-ordem").textContent = `R$ ${total
    .toFixed(2)
    .replace(".", ",")}`;
}

function formularioAlterado() {
  // Verifica se houve alterações no formulário
  return (
    document.querySelectorAll("#produtos-ordem tr").length > 0 ||
    document.querySelector("#fornecedor").value !== "" ||
    document.querySelector("#observacoes").value !== "" ||
    document.querySelector("#condicao_pagamento").value !== "" ||
    document.querySelector("#forma_pagamento").value !== ""
  );
}

function salvarOrdem() {
  // Coleta os dados do formulário
  const fornecedor = document.querySelector("#fornecedor").value;
  const data = document.querySelector("#data").value;
  const previsao = document.querySelector("#previsao").value;
  const observacoes = document.querySelector("#observacoes").value;
  const condicaoPagamento = document.querySelector("#condicao_pagamento").value;
  const formaPagamento = document.querySelector("#forma_pagamento").value;

  // Coleta os produtos
  const produtos = [];
  document.querySelectorAll("#produtos-ordem tr").forEach((linha) => {
    const produto = {
      id: linha.getAttribute("data-produto-id"),
      quantidade: linha.querySelector(".coluna-quantidade").textContent,
      valor_unitario: linha
        .querySelector(".coluna-valor")
        .textContent.replace("R$ ", "")
        .replace(",", "."),
      desconto: linha
        .querySelector(".coluna-desconto")
        .textContent.replace("R$ ", "")
        .replace(",", "."),
    };

    produtos.push(produto);
  });

  // Verifica se há produtos
  if (produtos.length === 0) {
    alert("Adicione pelo menos um produto à ordem de compra.");
    return;
  }

  // Cria o objeto com os dados da ordem
  const ordem = {
    fornecedor_id: fornecedor,
    data: data,
    previsao_entrega: previsao,
    observacoes: observacoes,
    condicao_pagamento: condicaoPagamento,
    forma_pagamento: formaPagamento,
    produtos: produtos,
  };

  // Envia para a API
  fetch("/api/pedidos_compra", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(ordem),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar ordem de compra");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Ordem de compra salva com sucesso!");

      // Redireciona para a listagem
      window.location.href = "/pedidos_compra";
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao salvar ordem de compra: ${error.message}`);
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .filtros-status {
    flex-wrap: wrap;
  }

  .filtro-status {
    flex: 1;
    min-width: 120px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .modulo-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 12px;
    width: 100%;
  }

  .barra-pesquisa {
    flex-direction: column;
    align-items: stretch;
  }

  .filtros-rapidos {
    margin-top: 12px;
  }

  .coluna-previsto,
  .coluna-marcadores,
  .coluna-integracoes {
    display: none;
  }

  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 12px;
    width: 100%;
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

  .filtro-status {
    min-width: 100%;
  }

  .coluna-data {
    display: none;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Roxo (indicador aberto): #722ed1
- Laranja (indicador andamento): #fa8c16
- Verde (indicador atendidas): #52c41a
- Vermelho (indicador canceladas): #f5222d
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
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Indicadores de Status

```css
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

.modal-rodape {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  padding: 16px 24px;
  border-top: 1px solid #f0f0f0;
}
```

### Dropdowns

```css
.dropdown-menu {
  position: absolute;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  z-index: 1000;
  min-width: 160px;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
}

.dropdown-divider {
  height: 1px;
  background-color: #e0e0e0;
  margin: 4px 0;
}
```

## Fluxos de Navegação

1. **Listagem de Ordens de Compra**:

   - A tela inicial exibe todas as ordens de compra cadastradas
   - Filtros permitem refinar a visualização por status ou período
   - Pesquisa permite localizar ordens específicas por fornecedor ou número

2. **Cadastro de Nova Ordem de Compra**:

   - Clique no botão "Incluir ordem de compra" redireciona para o formulário de cadastro
   - Preenchimento do formulário com dados da ordem e adição de produtos
   - Salvamento adiciona a ordem à listagem

3. **Impressão de Ordens**:

   - Seleção de ordens específicas ou geração de relatório geral
   - Configuração de parâmetros de impressão
   - Geração do relatório em formato PDF, Excel ou CSV

4. **Exportação e Importação**:
   - Acesso via menu de ações adicionais
   - Configuração de parâmetros de exportação
   - Upload de arquivo para importação

## Conclusão

O módulo "Ordens de Compra" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente de pedidos a fornecedores. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, cadastro e manipulação de dados de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para indicar os diferentes status das ordens. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para a gestão de ordens de compra, como cadastro, impressão, exportação e importação, atendendo às necessidades de negócios que trabalham com compras de produtos e serviços.
