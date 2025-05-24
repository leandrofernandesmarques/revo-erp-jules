# Análise do Módulo Notas de Entrada - ERP Revo

## Estrutura Geral

O módulo "Notas de Entrada" do ERP Revo apresenta uma interface organizada para gerenciamento de notas fiscais de entrada, com uma estrutura que facilita a visualização, importação e manipulação dos documentos fiscais. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma área de listagem de notas fiscais com seus respectivos status.

## Componentes Principais

### Alerta de Ambiente

Um alerta no topo da página informa sobre o ambiente atual:

**Estrutura HTML:**

```html
<div class="alerta-ambiente">
  <div class="alerta-icone">
    <span class="icone icone-alerta"></span>
  </div>
  <div class="alerta-mensagem">
    Você está no ambiente para testes de notas fiscais.
    <a href="#" class="alerta-link" id="btn-alterar-ambiente"
      >alterar ambiente</a
    >
    para gerar notas com valor fiscal.
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-ambiente {
  display: flex;
  align-items: center;
  padding: 12px 24px;
  background-color: #fffbe6;
  border: 1px solid #ffe58f;
  margin-bottom: 16px;
}

.alerta-icone {
  margin-right: 12px;
  color: #faad14;
  font-size: 18px;
}

.alerta-mensagem {
  font-size: 14px;
  color: #333333;
}

.alerta-link {
  color: #1890ff;
  text-decoration: none;
  margin: 0 4px;
}

.alerta-link:hover {
  text-decoration: underline;
}
```

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Notas Fiscais de Entrada"
- Botão para importar XML da NFe
- Botão para incluir nota fiscal
- Menu de ações adicionais

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Notas Fiscais de Entrada</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-importar-xml">
      <span class="icone icone-importar"></span>
      <span class="texto">Importar XML da NFe</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
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

A barra de pesquisa permite filtrar as notas fiscais:

- Campo de texto para pesquisa por cliente ou número
- Botão de busca
- Filtros de período e data de emissão

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por cliente ou número"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="periodo">
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="data-emissao">
      <span class="icone icone-calendario"></span>
      <span class="texto">data de emissão</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="avancado">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
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

Os filtros permitem visualizar notas fiscais por status:

- Todas
- Pendentes
- Registradas
- Emitidas
- Canceladas

**Estrutura HTML:**

```html
<div class="filtros-status">
  <a href="#" class="filtro-status ativo" data-status="todas">
    <span class="indicador indicador-todas"></span>
    <span class="texto">Todas</span>
  </a>
  <a href="#" class="filtro-status" data-status="pendentes">
    <span class="indicador indicador-pendentes"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="filtro-status" data-status="registradas">
    <span class="indicador indicador-registradas"></span>
    <span class="texto">Registradas</span>
  </a>
  <a href="#" class="filtro-status" data-status="emitidas">
    <span class="indicador indicador-emitidas"></span>
    <span class="texto">Emitidas</span>
  </a>
  <a href="#" class="filtro-status" data-status="canceladas">
    <span class="indicador indicador-canceladas"></span>
    <span class="texto">Canceladas</span>
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

.indicador-todas {
  background-color: #999999;
}

.indicador-pendentes {
  background-color: #722ed1;
}

.indicador-registradas {
  background-color: #fa8c16;
}

.indicador-emitidas {
  background-color: #52c41a;
}

.indicador-canceladas {
  background-color: #f5222d;
}
```

### Área de Resultados

A área de resultados exibe as notas fiscais cadastradas ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="resultados-container">
  <!-- Quando há resultados -->
  <div class="tabela-notas">
    <!-- Conteúdo da tabela de notas fiscais -->
  </div>

  <!-- Quando não há resultados -->
  <div class="sem-resultados">
    <div class="sem-resultados-conteudo">
      <h2 class="sem-resultados-titulo">
        Sua pesquisa não retornou resultados.
      </h2>
      <p class="sem-resultados-descricao">
        Tente outras opções de pesquisa, situações ou remova os filtros.
      </p>
      <div class="sem-resultados-acoes">
        <button class="botao botao-primario">alterar pesquisa</button>
        <button class="botao botao-secundario">limpar filtros</button>
      </div>
      <div class="sem-resultados-ilustracao">
        <!-- Ilustração -->
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.resultados-container {
  flex: 1;
  background-color: #ffffff;
  padding: 24px;
  overflow: auto;
}

.sem-resultados {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 400px;
}

.sem-resultados-conteudo {
  max-width: 600px;
  text-align: center;
  padding: 24px;
  border: 1px solid #f0f0f0;
  border-radius: 8px;
  background-color: #ffffff;
}

.sem-resultados-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.sem-resultados-descricao {
  font-size: 14px;
  color: #666666;
  margin-bottom: 24px;
}

.sem-resultados-acoes {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-bottom: 24px;
}

.sem-resultados-ilustracao {
  margin-top: 24px;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Tabela de Notas Fiscais

Quando há resultados, a tabela exibe as notas fiscais cadastradas com suas informações:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-notas">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-numero">
          Número
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-serie">
          Série
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-data">
          Data
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-fornecedor">
          Fornecedor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-valor">
          Valor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-status">
          Status
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-nota">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-numero">
          <a href="#/nota/12345" class="link-nota">12345</a>
        </td>
        <td class="coluna-serie">1</td>
        <td class="coluna-data">05/12/2024</td>
        <td class="coluna-fornecedor">FORNECEDOR EXEMPLO LTDA</td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-status">
          <span class="badge badge-registrada">Registrada</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-opcoes"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de notas fiscais -->
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

.tabela-notas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-notas th,
.tabela-notas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-notas th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
  white-space: nowrap;
}

.coluna-selecao {
  width: 40px;
}

.coluna-numero,
.coluna-serie {
  width: 80px;
}

.coluna-data {
  width: 120px;
}

.coluna-fornecedor {
  min-width: 200px;
}

.coluna-valor {
  width: 120px;
}

.coluna-status {
  width: 120px;
}

.coluna-acoes {
  width: 60px;
  text-align: right;
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

.link-nota {
  color: #1890ff;
  text-decoration: none;
}

.link-nota:hover {
  text-decoration: underline;
}

.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.badge-pendente {
  background-color: #f0f5ff;
  color: #722ed1;
}

.badge-registrada {
  background-color: #fff7e6;
  color: #fa8c16;
}

.badge-emitida {
  background-color: #f6ffed;
  color: #52c41a;
}

.badge-cancelada {
  background-color: #fff1f0;
  color: #f5222d;
}

.botao-acao {
  width: 28px;
  height: 28px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  color: #666666;
  transition: background-color 0.2s ease;
}

.botao-acao:hover {
  background-color: #f5f5f5;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar notas fiscais:

```javascript
// Código para pesquisa de notas fiscais
document.querySelector('.input-pesquisa').addEventListener('keyup', function(e) {
  if (e.key === 'Enter') {
    realizarPesquisa(this.value);
  }
});

document.querySelector('.botao-busca').addEventListener('click', function() {
  const termoPesquisa = document.querySelector('.input-pesquisa').value;
  realizarPesquisa(termoPesquisa);
});

function realizarPesquisa(termo) {
  // Lógica para filtrar notas pelo termo de pesquisa
  fetch(`/api/notas_entrada/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then(response => response.json())
    .then(data => {
      atualizarListaNotas(data);
    });
}

// Código para filtro por período
document.querySelector('.filtro-item[data-filtro="periodo"]').addEventListener('click', function(e) {
  e.preventDefault();

  // Abre dropdown de períodos
  const dropdown = document.createElement('div');
  dropdown.classList.add('dropdown-menu');
  dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-periodo="hoje">Hoje</a>
    <a href="#" class="dropdown-item" data-periodo="ontem">Ontem</a>
    <a href="#" class="dropdown-item" data-periodo="7dias">Últimos 7 dias</a>
    <a href="#" class="dropdown-item" data-periodo="30dias">Últimos 30 dias</a>
    <a href="#" class="dropdown-item" data-periodo="mes_atual">Mês atual</a>
    <a href="#" class="dropdown-item" data-periodo="mes_anterior">Mês anterior</a>
    <a href="#" class="dropdown-item" data-periodo="personalizado">Período personalizado</a>
  `;

  // Posiciona o dropdown
  const rect = this.getBoundingClientRect();
  dropdown.style.top = `${rect.bottom}px`;
  dropdown.style.left = `${rect.left}px`;

  // Adiciona ao DOM
  document.body.appendChild(dropdown);

  // Adiciona eventos aos itens do dropdown
  dropdown.querySelectorAll('.dropdown-item').forEach(item => {
    item.addEventListener('click', function(e) {
      e.preventDefault();

      const periodo = this.getAttribute('data-periodo');

      if (periodo === 'personalizado') {
        abrirModalPeriodoPersonalizado();
      } else {
        filtrarPorPeriodo(periodo);

        // Atualiza o texto do filtro
        document.querySelector('.filtro-item[data-filtro="periodo"] .texto').textContent = this.textContent;
      }

      // Remove o dropdown
      document.body.removeChild(dropdown);
    });
  });

  // Fecha o dropdown ao clicar fora
  document.addEventListener('click', function fecharDropdown(e) {
    if (!dropdown.contains(e.target) && e.target !== document.querySelector('.filtro-item[data-filtro="periodo"]')) {
      document.body.removeChild(dropdown);
      document.
(Content truncated due to size limit. Use line ranges to read in chunks)
```
