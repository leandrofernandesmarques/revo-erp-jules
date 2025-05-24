# Análise do Módulo Ordens de Serviço - ERP Revo

## Estrutura Geral

O módulo "Ordens de Serviço" do ERP Revo apresenta uma interface para gerenciamento de ordens de serviço. A página exibe uma lista de ordens de serviço com opções de filtragem, pesquisa e ações para gerenciamento.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Ações Principais

A seção superior contém o título da página e botões de ação principais:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Ordens de Serviço</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Ordens de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <a
      href="/ordem_servicos/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-ordem"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir ordem de serviço</span>
    </a>

    <div class="dropdown">
      <button
        class="botao-acao botao-secundario dropdown-toggle"
        id="btn-mais-acoes"
      >
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu" id="menu-mais-acoes">
        <a href="#" class="dropdown-item" id="btn-exportar">Exportar</a>
        <a href="#" class="dropdown-item" id="btn-importar">Importar</a>
        <div class="dropdown-divider"></div>
        <a href="#" class="dropdown-item" id="btn-excluir-selecionados"
          >Excluir selecionados</a
        >
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.cabecalho-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.breadcrumb {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  font-size: 14px;
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

.breadcrumb-item-atual {
  color: #666666;
}

.cabecalho-titulo {
  margin-bottom: 16px;
}

.titulo-pagina {
  font-size: 24px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.cabecalho-acoes {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
}

.botao-acao {
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
  border: 1px solid #1890ff;
}

.botao-primario:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
}

.botao-secundario {
  background-color: #ffffff;
  color: #666666;
  border: 1px solid #d9d9d9;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao-acao .icone {
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
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.dropdown-menu.show {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.dropdown-divider {
  height: 1px;
  margin: 8px 0;
  background-color: #f0f0f0;
}
```

### Área de Pesquisa e Filtros

A seção de pesquisa e filtros permite buscar e filtrar ordens de serviço:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente, nº da ordem ou nº de série"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-adicionais">
      <a href="#" class="filtro-adicional" id="filtro-periodo">
        <span class="icone icone-calendario"></span>
        <span class="texto">por período</span>
      </a>

      <button class="botao-filtros" id="btn-filtros">
        <span class="icone icone-filtro"></span>
        <span class="texto">filtros</span>
      </button>
    </div>
  </div>

  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="todas">
      <span class="texto">Todas</span>
      <span class="contador">26</span>
    </a>
    <a href="#" class="filtro-item filtro-ativo" data-filtro="em-aberto">
      <span class="texto">Em aberto</span>
      <span class="contador">01</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="orcadas">
      <span class="texto">Orçadas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="aprovadas">
      <span class="texto">Aprovadas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="nao-aprovadas">
      <span class="texto">Não aprovadas</span>
      <span class="contador">02</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="em-andamento">
      <span class="texto">Em andamento</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="mais">
      <span class="texto">mais</span>
    </a>
  </div>

  <div class="filtros-aplicados">
    <div class="filtro-aplicado">
      <span class="filtro-aplicado-label">Situação:</span>
      <span class="filtro-aplicado-valor">Em aberto</span>
      <span class="contador">01</span>
    </div>

    <div class="filtros-acoes">
      <button class="botao-acao botao-pequeno" id="btn-limpar-filtros">
        <span class="icone icone-limpar"></span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  padding: 0 24px 16px;
  background-color: #ffffff;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
}

.campo-pesquisa {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-right: none;
  border-radius: 4px 0 0 4px;
  font-size: 14px;
  color: #333333;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 36px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa:hover {
  background-color: #f5f5f5;
}

.botao-pesquisa .icone {
  font-size: 16px;
  color: #666666;
}

.filtros-adicionais {
  display: flex;
  align-items: center;
  margin-left: 16px;
  gap: 8px;
}

.filtro-adicional {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-adicional:hover {
  background-color: #f5f5f5;
}

.filtro-adicional .icone {
  margin-right: 8px;
  font-size: 14px;
}

.botao-filtros {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-filtros:hover {
  background-color: #f5f5f5;
}

.botao-filtros .icone {
  margin-right: 8px;
  font-size: 14px;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  overflow-x: auto;
  padding-bottom: 4px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  white-space: nowrap;
  margin-right: 8px;
}

.filtro-item:hover {
  background-color: #f5f5f5;
}

.filtro-ativo {
  background-color: #1890ff;
  color: white;
}

.filtro-ativo:hover {
  background-color: #40a9ff;
  color: white;
}

.filtro-ativo .contador {
  background-color: white;
  color: #1890ff;
}

.contador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20px;
  height: 20px;
  padding: 0 6px;
  margin-left: 8px;
  background-color: #f5f5f5;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.filtros-aplicados {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 16px;
}

.filtro-aplicado {
  display: flex;
  align-items: center;
  font-size: 14px;
}

.filtro-aplicado-label {
  color: #666666;
  margin-right: 4px;
}

.filtro-aplicado-valor {
  color: #333333;
  font-weight: 500;
  margin-right: 4px;
}

.filtros-acoes {
  display: flex;
  align-items: center;
}

.botao-pequeno {
  padding: 4px;
  width: 28px;
  height: 28px;
}

.botao-pequeno .icone {
  margin-right: 0;
}
```

### Lista de Ordens de Serviço

A tabela que exibe a lista de ordens de serviço:

**Estrutura HTML:**

```html
<div class="ordens-lista-container">
  <table class="ordens-tabela">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-numero">
          <div class="cabecalho-coluna">
            <span class="texto">Número</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data">
          <div class="cabecalho-coluna">
            <span class="texto">Data</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data-prevista">
          <div class="cabecalho-coluna">
            <span class="texto">Data Prevista</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data-conclusao">
          <div class="cabecalho-coluna">
            <span class="texto">Data de conclusão</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-nome-fantasia">
          <div class="cabecalho-coluna">
            <span class="texto">Nome Fantasia</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-total">
          <div class="cabecalho-coluna">
            <span class="texto">Total</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-marcadores">
          <div class="cabecalho-coluna">
            <span class="texto">Marcadores</span>
          </div>
        </th>
        <th class="coluna-integracoes">
          <div class="cabecalho-coluna">
            <span class="texto">Integrações</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-ordem">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-ordem"
            data-id="14840"
          />
        </td>
        <td class="coluna-numero">
          <a href="/ordem_servicos/visualizar/14840" class="link-numero"
            >14840</a
          >
        </td>
        <td class="coluna-data">16/05/2025</td>
        <td class="coluna-data-prevista"></td>
        <td class="coluna-data-conclusao"></td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-nome-fantasia">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-total">0,00</td>
        <td class="coluna-marcadores"></td>
        <td class="coluna-integracoes"></td>
      </tr>
    </tbody>
  </table>

  <div class="resumo-rodape">
    <div class="resumo-item">
      <span class="resumo-valor">1</span>
      <span class="resumo-label">quantidade</span>
    </div>
    <div class="resumo-item">
      <span class="resumo-valor">0,00</span>
      <span class="resumo-label">valor total (R$)</span>
    </div>
  </div>

  <button class="botao-voltar-topo" id="btn-voltar-topo" title="Voltar ao topo">
    <span class="icone icone-seta-cima"></span>
  </button>
</div>
```

**Estilos CSS:**

```css
.ordens-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
  position: relative;
}

.ordens-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.ordens-tabela th,
.ordens-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.ordens-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.cabecalho-coluna {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-coluna .icone-ordenar {
  margin-left: 4px;
  font-size: 12px;
  color: #d9d9d9;
}

.cabecalho-coluna:hover .icone-ordenar {
  color: #1890ff;
}

.linha-ordem {
  transition: background-color 0.2s ease;
}

.linha-ordem:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-numero {
  width: 80px;
}

.link-numero {
  color: #1890ff;
  text-decoration: none;
}

.link-numero:hover {
  text-decoration: underline;
}

.coluna-data,
.coluna-data-prevista,
.coluna-data-conclusao {
  width: 120px;
}

.coluna-cliente,
.coluna-nome-fantasia {
  min-width: 200px;
}

.coluna-total {
  width: 100px;
  text-align: right;
}

.coluna-marcadores,
.coluna-integracoes {
  width: 120px;
}

.resumo-rodape {
  display: flex;
  align-items: center;
  padding: 16px 0;
  border-top: 1px solid #f0f0f0;
}

.resumo-item {
  display: flex;
  flex-direction: column;
  margin-right: 32px;
}

.resumo-valor {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
}

.resumo-label {
  font-size: 12px;
  color: #666666;
}

.botao-voltar-topo {
  position: fixed;
  bottom: 24px;
  right: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-voltar-topo:hover {
  background-color: #f5f5f5;
}

.botao-voltar-topo .icone {
  font-size: 16px;
  color: #666666;
}
```

## Formulário de Inclusão/Edição de Ordem de Serviço

Embora não esteja visível na tela atual, o formulário de inclusão/edição de ordem de serviço é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Incluir Ordem de Serviço</h2>
    <div class="formulario-acoes">
      <button class="botao-acao botao-secundario" id="btn-cancelar">
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao-acao botao-primario" id="btn-salvar">
        <span class="texto">Salvar</span>
      </button>

      (Content truncated due to size limit. Use line ranges to read in chunks)
    </div>
  </div>
</div>
```
