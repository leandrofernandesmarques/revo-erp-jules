# Análise do Módulo CRM - ERP Revo

## Estrutura Geral

O módulo "CRM" do ERP Revo apresenta uma interface organizada para gestão do relacionamento com os clientes. A tela é composta por um cabeçalho com título e descrição, botões de ação principais, uma barra de pesquisa com filtros e uma área de visualização dos assuntos/oportunidades.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção, uma breve descrição e botões de ação:

- Título "CRM"
- Descrição "Gestão do relacionamento com os clientes"
- Botão para incluir novo assunto

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">CRM</h1>
    <p class="descricao-modulo">Gestão do relacionamento com os clientes</p>
  </div>
  <div class="acoes-container">
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir assunto</span>
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
  border-bottom: 1px solid #e0e0e0;
}

.titulo-modulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.descricao-modulo {
  font-size: 14px;
  color: #666666;
  margin: 4px 0 0 0;
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

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao .icone {
  margin-right: 8px;
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar os assuntos/oportunidades:

- Campo de texto para pesquisa por contato, CPF/CNPJ ou descrição
- Botão de busca
- Opções de visualização (Lista, por estágio)
- Filtros de período e outros filtros avançados

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por contato, CPF/CNPJ ou descrição"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="opcoes-visualizacao">
    <a href="#" class="opcao-item ativo" data-visualizacao="lista">
      <span class="icone icone-lista"></span>
      <span class="texto">Lista</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="estagio">
      <span class="icone icone-estagio"></span>
      <span class="texto">por estágio</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="periodo">
      <span class="icone icone-calendario"></span>
      <span class="texto">por período</span>
    </a>
    <a href="#" class="opcao-item" data-visualizacao="filtros">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
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

.opcoes-visualizacao {
  display: flex;
  gap: 8px;
}

.opcao-item {
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

.opcao-item.ativo {
  background-color: #e6f7ff;
  border-color: #91d5ff;
  color: #1890ff;
}

.opcao-item:hover:not(.ativo) {
  background-color: #f0f0f0;
}

.opcao-item .icone {
  margin-right: 6px;
  font-size: 16px;
}
```

### Filtros por Situação

Os filtros permitem visualizar assuntos/oportunidades por situação:

- Todos
- Com ações pendentes
- Encerrados
- Com estrela
- Arquivados

**Estrutura HTML:**

```html
<div class="filtros-situacao">
  <a href="#" class="filtro-situacao ativo" data-situacao="todos">
    <span class="texto">Todos</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="pendentes">
    <span class="texto">Com ações pendentes</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="encerrados">
    <span class="texto">Encerrados</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="estrela">
    <span class="texto">Com estrela</span>
  </a>
  <a href="#" class="filtro-situacao" data-situacao="arquivados">
    <span class="texto">Arquivados</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.filtros-situacao {
  display: flex;
  gap: 4px;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtro-situacao {
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

.filtro-situacao.ativo {
  background-color: #f6ffed;
  border-color: #b7eb8f;
  color: #52c41a;
}

.filtro-situacao:hover:not(.ativo) {
  background-color: #f5f5f5;
}
```

### Área de Resultados

A área de resultados exibe os assuntos/oportunidades cadastrados ou uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="resultados-container">
  <!-- Quando há resultados -->
  <div class="tabela-assuntos">
    <!-- Conteúdo da tabela de assuntos -->
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

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}
```

### Tabela de Assuntos

Quando há resultados, a tabela exibe os assuntos/oportunidades cadastrados:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-assuntos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-estrela"></th>
        <th class="coluna-contato">
          Contato
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-descricao">
          Descrição
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-estagio">
          Estágio
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-valor">
          Valor
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-data">
          Data
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-responsavel">
          Responsável
          <span class="icone-ordenacao"></span>
        </th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-assunto">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-estrela">
          <button class="botao-estrela">
            <span class="icone icone-estrela-vazia"></span>
          </button>
        </td>
        <td class="coluna-contato">
          <a href="#/contato/12345" class="link-contato"
            >Empresa Exemplo Ltda</a
          >
        </td>
        <td class="coluna-descricao">
          <a href="#/assunto/67890" class="link-assunto"
            >Proposta de serviços de consultoria</a
          >
        </td>
        <td class="coluna-estagio">
          <span class="badge badge-estagio">Negociação</span>
        </td>
        <td class="coluna-valor">R$ 5.000,00</td>
        <td class="coluna-data">05/12/2024</td>
        <td class="coluna-responsavel">João Silva</td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-opcoes"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de assuntos -->
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

.tabela-assuntos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-assuntos th,
.tabela-assuntos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-assuntos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
  white-space: nowrap;
}

.coluna-selecao {
  width: 40px;
}

.coluna-estrela {
  width: 40px;
}

.coluna-contato,
.coluna-responsavel {
  width: 150px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-estagio {
  width: 120px;
}

.coluna-valor,
.coluna-data {
  width: 100px;
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

.link-contato,
.link-assunto {
  color: #1890ff;
  text-decoration: none;
}

.link-contato:hover,
.link-assunto:hover {
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

.badge-estagio {
  background-color: #e6f7ff;
  color: #1890ff;
}

.botao-estrela {
  width: 24px;
  height: 24px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: none;
  cursor: pointer;
  color: #d9d9d9;
  transition: color 0.2s ease;
}

.botao-estrela:hover {
  color: #faad14;
}

.botao-estrela .icone-estrela-cheia {
  color: #faad14;
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

O módulo permite pesquisar e filtrar assuntos/oportunidades:

```javascript
// Código para pesquisa de assuntos
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
  // Lógica para filtrar assuntos pelo termo de pesquisa
  fetch(`/api/crm/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then(response => response.json())
    .then(data => {
      atualizarListaAssuntos(data);
    });
}

// Código para opções de visualização
document.querySelectorAll('.opcao-item').forEach(opcao => {
  opcao.addEventListener('click', function(e) {
    e.preventDefault();

    // Remove classe ativo de todas as opções
    document.querySelectorAll('.opcao-item').forEach(op => {
      op.classList.remove('ativo');
    });

    // Adiciona classe ativo à opção clicada
    this.classList.add('ativo');

    // Altera a visualização
    const visualizacao = this.getAttribute('data-visualizacao');
    alterarVisualizacao(visualizacao);
  });
});

function alterarVisualizacao(tipo) {
  switch (tipo) {
    case 'lista':
      // Exibe visualização em lista
      document.querySelector('.tabela-container').style.display = 'block';
      document.querySelector('.visualizacao-estagio').style.display = 'none';
      break;
    case 'estagio':
      // Exibe visualização por estágio (kanban)
      document.querySelector('.tabela-container').style.display = 'none';
      document.querySelector('.visualizacao-estagio').style.display = 'block';
      carregarVisualizacaoEstagio();
      break;
    case 'periodo':
      // Abre modal de seleção de período
      abrirModalPeriodo();
      break;
    case 'filtros':
      // Abre modal de filtros avançados
      abrirModalFiltros();
      break;
  }
}

function abrirModalPeriodo() {
  // Abre modal para seleção de período
  const modal = document.createElement('div');
  modal.classList.add('modal');
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
            <label for="apenas_periodo">Apenas assuntos criados neste período</label>
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
  modal.querySelector('.botao-fechar').addEventListener('click', () => {
    document.body.removeChild(modal);
  });

  modal.querySelector('#btn-limpar-periodo').addEventListener('click', () => {
    document.querySelector('#data_inicial').value = '';
    document.querySelector('#data_final').value = '';
    document.querySelector('#apenas_periodo').checked = false;
  });

  modal.querySelector('#btn-aplicar-periodo').addEventListener('click', () => {
    // Coleta os dados do formulário
    const d
(Content truncated due to size limit. Use line ranges to read in chunks)
```
