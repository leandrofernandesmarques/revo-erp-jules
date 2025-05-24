# Análise do Módulo Contas a Pagar - ERP Revo

## Estrutura Geral

O módulo "Contas a Pagar" do ERP Revo apresenta uma interface de gerenciamento financeiro focada no controle de pagamentos a fornecedores e despesas. A página é estruturada com uma área de filtros e pesquisa no topo, seguida por uma tabela principal que lista todas as contas a pagar cadastradas no sistema.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Ações e Filtros

A seção superior contém botões de ação e ferramentas de filtragem:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/financas" class="breadcrumb-item">Finanças</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Contas a Pagar</span>
  </div>

  <div class="acoes-principais">
    <button class="botao-acao" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <button class="botao-acao botao-destaque" id="btn-gerenciar-pagamentos">
      <span class="icone icone-pagamentos"></span>
      <span class="texto">Gerenciar pagamentos</span>
    </button>

    <a
      href="/contas_pagar/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-conta"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir conta a pagar</span>
    </a>

    <div class="dropdown">
      <button class="botao-acao botao-dropdown" id="btn-mais-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item" id="btn-exportar">Exportar</a>
        <a href="#" class="dropdown-item" id="btn-importar">Importar</a>
        <a href="#" class="dropdown-item" id="btn-configuracoes"
          >Configurações</a
        >
      </div>
    </div>
  </div>

  <div class="banner-promocional">
    <div class="banner-conteudo">
      <div class="banner-texto">
        <h3 class="banner-titulo">
          Quer economizar tempo no lançamento de suas transações bancárias?
        </h3>
        <p class="banner-descricao">
          Economize até 8 horas* mensais com a conciliação bancária automática.
        </p>
      </div>
      <button class="botao-banner" id="btn-confira-beneficios">
        confira os benefícios
      </button>
    </div>
    <div class="banner-imagem">
      <img
        src="/assets/images/banner-conciliacao.png"
        alt="Conciliação bancária"
      />
    </div>
  </div>

  <div class="filtros-container">
    <div class="pesquisa-container">
      <input
        type="text"
        class="campo-pesquisa"
        placeholder="Pesquise por fornecedor ou nº doc"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
      <button class="botao-filtro-avancado">
        <span class="icone icone-filtro-avancado"></span>
      </button>
    </div>

    <div class="filtros-rapidos">
      <a href="#" class="filtro-item filtro-ativo">contas a pagar</a>
      <a href="#" class="filtro-item">Últimos 30 dias</a>
      <a href="#" class="filtro-item">
        <span class="icone icone-filtro"></span>
        <span class="texto">filtros</span>
      </a>
      <a href="#" class="filtro-item">
        <span class="texto">limpar filtros</span>
      </a>
    </div>

    <div class="filtros-status">
      <a href="#" class="status-item status-ativo">
        <span class="texto">Todas</span>
        <span class="contador">241</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Em aberto</span>
        <span class="contador">11</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Emitidas</span>
        <span class="contador">224</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Pagas</span>
        <span class="contador">220</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Atrasadas</span>
        <span class="contador">15</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Canceladas</span>
        <span class="contador">14</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
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

.acoes-principais {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
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
  background-color: #f5f5f5;
  color: #333333;
  border: 1px solid #d9d9d9;
}

.botao-acao:hover {
  background-color: #e6e6e6;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
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

.botao-destaque {
  background-color: #52c41a;
  color: white;
  border: 1px solid #52c41a;
}

.botao-destaque:hover {
  background-color: #73d13d;
  border-color: #73d13d;
}

.dropdown {
  position: relative;
  display: inline-block;
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

.banner-promocional {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f0f7ff;
  border-radius: 8px;
  padding: 16px 24px;
  margin-bottom: 16px;
}

.banner-conteudo {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex: 1;
}

.banner-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 4px;
}

.banner-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.banner-imagem {
  margin-left: 24px;
}

.banner-imagem img {
  height: 80px;
  width: auto;
}

.botao-banner {
  background-color: #1890ff;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 8px 16px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease;
  white-space: nowrap;
  margin-left: 16px;
}

.botao-banner:hover {
  background-color: #40a9ff;
}

.filtros-container {
  margin-bottom: 16px;
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
  border-radius: 4px 0 0 4px;
  font-size: 14px;
  color: #333333;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa,
.botao-filtro-avancado {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 36px;
  background-color: #f5f5f5;
  border: 1px solid #d9d9d9;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa {
  border-left: none;
  border-radius: 0;
}

.botao-filtro-avancado {
  border-left: none;
  border-radius: 0 4px 4px 0;
}

.botao-pesquisa:hover,
.botao-filtro-avancado:hover {
  background-color: #e6e6e6;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 16px;
  font-size: 14px;
  color: #666666;
  background-color: #f5f5f5;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.filtro-item:hover {
  background-color: #e6e6e6;
}

.filtro-ativo {
  background-color: #e6f7ff;
  color: #1890ff;
}

.filtro-item .icone {
  margin-right: 4px;
  font-size: 14px;
}

.filtros-status {
  display: flex;
  align-items: center;
  border-bottom: 1px solid #f0f0f0;
  flex-wrap: wrap;
}

.status-item {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
}

.status-item:hover {
  color: #1890ff;
}

.status-ativo {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.contador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20px;
  height: 20px;
  padding: 0 6px;
  margin-left: 8px;
  font-size: 12px;
  border-radius: 10px;
  background-color: #f5f5f5;
}

.status-ativo .contador {
  background-color: #e6f7ff;
}
```

### Tabela de Contas a Pagar

A tabela principal que lista todas as contas a pagar:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-contas">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-fornecedor">
          <div class="cabecalho-coluna">
            <span class="texto">Fornecedor</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-historico">
          <div class="cabecalho-coluna">
            <span class="texto">Histórico</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-documento">
          <div class="cabecalho-coluna">
            <span class="texto">Nº documento</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-vencimento">
          <div class="cabecalho-coluna">
            <span class="texto">Vencimento</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-valor">
          <div class="cabecalho-coluna">
            <span class="texto">Valor</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-saldo">
          <div class="cabecalho-coluna">
            <span class="texto">Saldo</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-pago">
          <div class="cabecalho-coluna">
            <span class="texto">Pago</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-buscador">
          <div class="cabecalho-coluna">
            <span class="texto">Buscador</span>
          </div>
        </th>
        <th class="coluna-marcadores">
          <div class="cabecalho-coluna">
            <span class="texto">Marcadores</span>
          </div>
        </th>
        <th class="coluna-forma">
          <div class="cabecalho-coluna">
            <span class="texto">Forma</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-conta">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-conta" />
        </td>
        <td class="coluna-fornecedor">
          <div class="fornecedor-info">
            <span class="fornecedor-tag">Revo Revo TECNOLOGIA LTDA</span>
          </div>
        </td>
        <td class="coluna-historico">MENSALIDADE SISTEMA TOTAL VITA</td>
        <td class="coluna-documento"></td>
        <td class="coluna-vencimento">28/04/2025</td>
        <td class="coluna-valor">44,90</td>
        <td class="coluna-saldo">44,90</td>
        <td class="coluna-pago">0,00</td>
        <td class="coluna-buscador">
          <span class="icone icone-buscador"></span>
        </td>
        <td class="coluna-marcadores"></td>
        <td class="coluna-forma"></td>
      </tr>

      <!-- Outras linhas de contas seguem o mesmo padrão -->
    </tbody>
  </table>

  <div class="tabela-rodape">
    <div class="rodape-info">
      <div class="info-item">
        <span class="info-label">quantidade</span>
        <span class="info-valor">11</span>
      </div>
      <div class="info-item">
        <span class="info-label">valor total (R$)</span>
        <span class="info-valor">1.300,16</span>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  background-color: #ffffff;
  border-radius: 4px;
  overflow: hidden;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.tabela-contas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-contas th,
.tabela-contas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-contas th {
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

.coluna-selecao {
  width: 40px;
}

.coluna-fornecedor {
  min-width: 200px;
}

.coluna-historico {
  min-width: 200px;
}

.coluna-documento {
  width: 120px;
}

.coluna-vencimento {
  width: 120px;
}

.coluna-valor,
.coluna-saldo,
.coluna-pago {
  width: 100px;
  text-align: right;
}

.coluna-buscador,
.coluna-marcadores,
.coluna-forma {
  width: 80px;
  text-align: center;
}

.linha-conta {
  transition: background-color 0.2s ease;
}

.linha-conta:hover {
  background-color: #f5f5f5;
}

.linha-conta.selecionada {
  background-color: #e6f7ff;
}

.fornecedor-info {
  display: flex;
  align-items: center;
}

.fornecedor-tag {
  display: inline-block;
  padding: 2px 6px;
  background-color: #f5f5f5;
  border-radius: 4px;
  font-size: 12px;
  color: #333333;
}

.checkbox-selecionar-todos,
.checkbox-selecionar-conta {
  width: 16px;
  height: 16px;
  cursor: pointer;
}

.icone-buscador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  background-color: #f5f5f5;
  border-radius: 4px;
  color: #666666;
  cursor: pointer;
}

.tabela-rodape {
  display: flex;
  justify-content: flex-end;
  padding: 12px 16px;
  background-color: #fafafa;
  border-top: 1px solid #f0f0f0;
}

.rodape-info {
  display: flex;
  align-items: center;
}

.info-item {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  margin-left: 24px;
}

.info-label {
  font-size: 12px;
  color: #999999;
}

.info-valor {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
}
```

### Botão Voltar ao Topo

O botão flutuante para voltar ao topo da página:

**Estrutura HTML:**

```html
<button class="botao-voltar-topo" id="btn-voltar-topo" title="Voltar ao topo">
  <span class="icone icone-seta-cima"></span>
</button>
```

**Estilos CSS:**

```css
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
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  opacity: 0;
  visibility: hidden;
  transiti
(Content truncated due to size limit. Use line ranges to read in chunks)
```
