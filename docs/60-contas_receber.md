# Análise do Módulo Contas a Receber - ERP Revo

## Estrutura Geral

O módulo "Contas a Receber" do ERP Revo apresenta uma interface de gerenciamento financeiro focada no controle de recebimentos de clientes. A página é estruturada com uma área de filtros e pesquisa no topo, seguida por uma tabela principal que lista todas as contas a receber cadastradas no sistema.

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
    <span class="breadcrumb-item-atual">Contas a Receber</span>
  </div>

  <div class="acoes-principais">
    <button class="botao-acao" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <button class="botao-acao botao-destaque" id="btn-gerenciar-recebimentos">
      <span class="icone icone-recebimentos"></span>
      <span class="texto">Gerenciar recebimentos</span>
    </button>

    <a
      href="/contas_receber/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-conta"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir conta a receber</span>
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
        placeholder="Pesquise por cliente, nº no banco ou nº doc"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
      <button class="botao-filtro-avancado">
        <span class="icone icone-filtro-avancado"></span>
      </button>
    </div>

    <div class="filtros-rapidos">
      <a href="#" class="filtro-item filtro-ativo">por meio de recebimento</a>
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
        <span class="texto">Em aberto</span>
        <span class="contador">04</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Emitidas</span>
        <span class="contador">77</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Recebidas</span>
        <span class="contador">69</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Atrasadas</span>
        <span class="contador">04</span>
      </a>
      <a href="#" class="status-item">
        <span class="texto">Canceladas</span>
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
  background-color: #722ed1;
  color: white;
  border: 1px solid #722ed1;
}

.botao-destaque:hover {
  background-color: #9254de;
  border-color: #9254de;
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

### Tabela de Contas a Receber

A tabela principal que lista todas as contas a receber:

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
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-historico">
          <div class="cabecalho-coluna">
            <span class="texto">Histórico</span>
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
        <th class="coluna-valor-liquido">
          <div class="cabecalho-coluna">
            <span class="texto">Valor líquido</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-recebido">
          <div class="cabecalho-coluna">
            <span class="texto">Recebido</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data-emissao">
          <div class="cabecalho-coluna">
            <span class="texto">Data Emissão</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-documento">
          <div class="cabecalho-coluna">
            <span class="texto">Documento</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-conta">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-conta" />
        </td>
        <td class="coluna-cliente">
          <div class="cliente-info">
            <span class="cliente-tag">VALTER GOMES</span>
          </div>
        </td>
        <td class="coluna-historico">
          Mensalidade de Prestação de Serviço de Hosting
        </td>
        <td class="coluna-vencimento">28/04/2025</td>
        <td class="coluna-valor">209,00</td>
        <td class="coluna-saldo">209,00</td>
        <td class="coluna-valor-liquido">209,00</td>
        <td class="coluna-recebido">0,00</td>
        <td class="coluna-data-emissao">07/11/2024</td>
        <td class="coluna-documento"></td>
      </tr>

      <tr class="linha-conta">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-conta" />
        </td>
        <td class="coluna-cliente">
          <div class="cliente-info">
            <span class="cliente-tag">Leandro Fernandes Marques</span>
          </div>
        </td>
        <td class="coluna-historico">Iphone Leandro - Parcela (4/15)</td>
        <td class="coluna-vencimento">28/04/2025</td>
        <td class="coluna-valor">274,77</td>
        <td class="coluna-saldo">274,77</td>
        <td class="coluna-valor-liquido">274,77</td>
        <td class="coluna-recebido">0,00</td>
        <td class="coluna-data-emissao">06/01/2025</td>
        <td class="coluna-documento"></td>
      </tr>

      <tr class="linha-conta">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-conta" />
        </td>
        <td class="coluna-cliente">
          <div class="cliente-info">
            <span class="cliente-tag">REI DO ALHO COM. DE ALIMENTO LTDA</span>
          </div>
        </td>
        <td class="coluna-historico">
          Mensalidade de Prestação de Serviço de Hosting
        </td>
        <td class="coluna-vencimento">10/05/2025</td>
        <td class="coluna-valor">155,75</td>
        <td class="coluna-saldo">155,75</td>
        <td class="coluna-valor-liquido">155,75</td>
        <td class="coluna-recebido">0,00</td>
        <td class="coluna-data-emissao">07/11/2024</td>
        <td class="coluna-documento"></td>
      </tr>

      <tr class="linha-conta">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-conta" />
        </td>
        <td class="coluna-cliente">
          <div class="cliente-info">
            <span class="cliente-tag">V M COSMÉTICOS</span>
          </div>
        </td>
        <td class="coluna-historico">MENSALIDADE DE SUPORTE MARKET PLACES</td>
        <td class="coluna-vencimento">13/05/2025</td>
        <td class="coluna-valor">780,00</td>
        <td class="coluna-saldo">780,00</td>
        <td class="coluna-valor-liquido">780,00</td>
        <td class="coluna-recebido">0,00</td>
        <td class="coluna-data-emissao">13/03/2025</td>
        <td class="coluna-documento"></td>
      </tr>
    </tbody>
  </table>

  <div class="tabela-rodape">
    <div class="rodape-info">
      <div class="info-item">
        <span class="info-label">quantidade</span>
        <span class="info-valor">4</span>
      </div>
      <div class="info-item">
        <span class="info-label">valor total (R$)</span>
        <span class="info-valor">1.419,52</span>
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

.coluna-cliente {
  min-width: 200px;
}

.coluna-historico {
  min-width: 200px;
}

.coluna-vencimento,
.coluna-data-emissao {
  width: 120px;
}

.coluna-valor,
.coluna-saldo,
.coluna-valor-liquido,
.coluna-recebido {
  width: 100px;
  text-align: right;
}

.coluna-documento {
  width: 120px;
}

.linha-conta {
  transition: background-color 0.2s ease;
}

.linha-conta:hover {
  background-color: #f5f5f5;
}

.linha-conta.selecionada {
  background-color: #f0f5ff;
}

.cliente-info {
  display: flex;
  align-items: center;
}

.cliente-tag {
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
  transition: opacity 0.2s ease, visibility 0.2s ease,
    background-color 0.2s ease;
}

.botao-voltar-topo.visivel {
  opacity: 1;
  visibility: visible;
}

.botao-voltar-topo:hover {
  background-color: #f5f5f5;
}

.botao-voltar-topo .icone-seta-cima {
  font-size: 16px;
  color: #666666;
}
```

## Interações JavaScript

### Seleção de Contas

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Seleção de todas as contas
  const checkboxSelecionarTodos = document.getElementById("selecionar-todos");
  const checkboxesContas = document.querySelectorAll(
    ".checkbox-selecionar-conta"
  );

  checkboxSelecionarTodos.addEventListener("change", function () {
    const isChecked = this.checked;

    checkboxesContas.forEach((checkbox) => {
      checkbox.checked = isChecked;

      const linha = checkbox.closest(".linha-conta");
      if (isChecked) {
        linha.classList.add("selecionada");
      } else {
        linha.classList.remove("selecionada");
      }
    });

    atualizarBotoesAcao();
  });

  checkboxesContas.forEach((checkbox) => {
    checkbox.addEventListener("change", function () {
      const linha = this.closest(".linha-conta");

      if (this.checked) {
        linha.classList.add("selecionada");
      } else {
        linha.classList.remove("selecionada");
      }

      // Verifica se todos estão selecionados
      const todosSelecionados = Array.from(checkboxesContas).every(
        (cb) => cb.checked
      );
      checkboxSelecionarTodos.checked = todosSelecionados;

      atualizarBotoesAcao();
    });
  });

  function atualizarBotoesAcao() {
    const contasSelecionadas = document.querySelectorAll(
      ".checkbox-selecionar-conta:checked"
    ).length;
    const botoesAcaoMultipla = document.querySelectorAll(
      ".botao-acao-multipla"
    );

    if (contasSelecionadas > 0) {
      botoesAcaoMultipla.forEach((botao) => {
        botao.removeAttribute("disabled");
      });
    } else {
      botoesAcaoMultipla.forEach((botao) => {
        botao.setAttribute("disabled", "disabled");
      });
    }
  }
});
```

### Filtros e Pesquisa

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Pesquisa
  const campoPesquisa = document.querySelector(".campo-pesquisa");
  const botaoPesquisa = document.querySelector(".botao-pesquisa");

  botaoPesquisa.addEventListener("click", function () {
    realizarPesquisa();
  });

  campoPesquisa.addEventListener("keypress", function (e) {
    if (e.key === "Enter") {
      realizarPesquisa();
    }
  });

  function realizarPesquisa() {
    const termoPesquisa = campoPesquisa.value.trim();
    if (termoPesquisa) {
      // Aqui seria implementada a lógica de pesquisa
      console.log("Pesquisando por:", termoPesquisa);
    }
  }

  // Filtros de status
  const filtrosStatus = document.querySelectorAll(".status-item");

  filtrosStatus.forEach((filtro) => {
    filtro.addEventListener("click", function (e) {
      e.preventDefault();

      // Remove a classe ativa de todos os filtros
      filtrosStatus.forEach((f) => f.classList.remove("status-ativo"));

      // Adiciona a classe ativa ao filtro clicado
      this.classList.add("status-ativo");

      // Aqui seria implementada a lógica de filtragem
      const statusFiltro = this.querySelector(".texto").textContent;
      console.log("Filtrando por status:", statusFiltro);
    });
  });

  // Filtros rápidos
  const filtrosRapidos = document.querySelectorAll(".filtro-item");

  filtrosRapidos.forEach((filtro) => {
    filtro.addEventListener("click", function (e) {
      e.preventDefault();

      if (this.textContent.includes("limpar filtros")) {
        // Limpa todos os filtros
        filtrosRapidos.forEach((f) => {
          if (!f.textContent.includes("limpar filtros")) {
            f.classList.remove("filtro-ativo");
          }
        });

        // Reseta o filtro de status para "Em aberto"
        filtrosStatus.forEach((f) => {
          f.classList.remove("status-ativo");
          if (f.querySelector(".texto").textContent === "Em aberto") {
            f.classList.add("status-ativo");
          }
        });

        // Limpa o campo de pesquisa
        campoPesquisa.value = "";

        console.log("Filtros limpos");
      } else if (this.textContent.includes("filtros")) {
        // Abre o modal de filtros avançados
        abrirModalFiltrosAvancados();
      } else {
        // Alterna o estado do filtro
        this.classList.toggle("filtro-ativo");

        // Aqui seria implementada a lógica de filtragem
        console.log("Filtro alterado:", this.textContent);
      }
    });
  });

  function abrirModalFiltrosAvancados() {
    // Aqui seria implementada a lógica para abrir o modal de filtros avançados
    console.log("Abrindo modal de filtros avançados");
  }
});
```

### Ordenação da Tabela

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Ordenação da tabela
  const cabecalhosOrdenacao = document.querySelectorAll(".cabecalho-coluna");

  cabecalhosOrdenacao.forEach((cabecalho) => {
    cabecalho.addEventListener("click", function () {
      const coluna = this.closest("th").className.replace("coluna-", "");

      // Verifica se já está ordenado
      const isAscendente = this.getAttribute("data-ordem") === "asc";

      // Remove a ordenação de todos os cabeçalhos
      cabecalhosOrdenacao.forEach((c) => {
        c.removeAttribute("data-ordem");
        c.querySelector(".icone-ordenar").className = "icone icone-ordenar";
      });

      // Define a nova ordenação
      if (isAscendente) {
        this.setAttribute("data-ordem", "desc");
        this.querySelector(".icone-ordenar").className =
          "icone icone-ordenar icone-ordenar-desc";
      } else {
        this.setAttribute("data-ordem", "asc");
        this.querySelector(".icone-ordenar").className =
          "icone icone-ordenar icone-ordenar-asc";
      }

      // Aqui seria implementada a lógica de ordenação
      console.log(
        "Ordenando por:",
        coluna,
        "Ordem:",
        this.getAttribute("data-ordem")
      );
    });
  });
});
```

### Botão Voltar ao Topo

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão voltar ao topo
  const botaoVoltarTopo = document.getElementById("btn-voltar-topo");

  window.addEventListener("scroll", function () {
    if (window.pageYOffset > 300) {
      botaoVoltarTopo.classList.add("visivel");
    } else {
      botaoVoltarTopo.classList.remove("visivel");
    }
  });

  botaoVoltarTopo.addEventListener("click", function () {
    window.scrollTo({
      top: 0,
      behavior: "smooth",
    });
  });
});
```

### Ações em Lote

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão de gerenciar recebimentos
  const botaoGerenciarRecebimentos = document.getElementById(
    "btn-gerenciar-recebimentos"
  );

  botaoGerenciarRecebimentos.addEventListener("click", function () {
    const contasSelecionadas = document.querySelectorAll(
      ".checkbox-selecionar-conta:checked"
    );

    if (contasSelecionadas.length > 0) {
      // Abre o modal de gerenciamento de recebimentos com as contas selecionadas
      abrirModalGerenciarRecebimentos(contasSelecionadas);
    } else {
      // Abre o modal de gerenciamento de recebimentos sem contas selecionadas
      abrirModalGerenciarRecebimentos();
    }
  });

  function abrirModalGerenciarRecebimentos(contasSelecionadas = []) {
    // Aqui seria implementada a lógica para abrir o modal de gerenciamento de recebimentos
    console.log("Abrindo modal de gerenciamento de recebimentos");
    console.log("Contas selecionadas:", contasSelecionadas.length);
  }

  // Dropdown de mais ações
  const botaoMaisAcoes = document.getElementById("btn-mais-acoes");
  const dropdownMenu = document.querySelector(".dropdown-menu");

  botaoMaisAcoes.addEventListener("click", function (e) {
    e.preventDefault();
    dropdownMenu.style.display =
      dropdownMenu.style.display === "block" ? "none" : "block";
  });

  // Fecha o dropdown ao clicar fora
  document.addEventListener("click", function (e) {
    if (
      !botaoMaisAcoes.contains(e.target) &&
      !dropdownMenu.contains(e.target)
    ) {
      dropdownMenu.style.display = "none";
    }
  });

  // Ações do dropdown
  const botaoExportar = document.getElementById("btn-exportar");
  const botaoImportar = document.getElementById("btn-importar");
  const botaoConfiguracoes = document.getElementById("btn-configuracoes");

  botaoExportar.addEventListener("click", function (e) {
    e.preventDefault();
    // Aqui seria implementada a lógica para exportar
    console.log("Exportando contas a receber");
  });

  botaoImportar.addEventListener("click", function (e) {
    e.preventDefault();
    // Aqui seria implementada a lógica para importar
    console.log("Importando contas a receber");
  });

  botaoConfiguracoes.addEventListener("click", function (e) {
    e.preventDefault();
    // Aqui seria implementada a lógica para abrir configurações
    console.log("Abrindo configurações");
  });
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .acoes-principais {
    flex-wrap: wrap;
  }

  .banner-promocional {
    flex-direction: column;
  }

  .banner-conteudo {
    margin-bottom: 16px;
  }

  .banner-imagem {
    margin-left: 0;
  }

  .tabela-container {
    overflow-x: auto;
  }

  .tabela-contas {
    min-width: 1000px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .acoes-principais {
    justify-content: space-between;
  }

  .botao-acao {
    flex: 1;
    justify-content: center;
  }

  .banner-conteudo {
    flex-direction: column;
    text-align: center;
  }

  .botao-banner {
    margin-left: 0;
    margin-top: 16px;
  }

  .filtros-rapidos,
  .filtros-status {
    overflow-x: auto;
    white-space: nowrap;
    padding-bottom: 8px;
  }

  .filtro-item,
  .status-item {
    flex-shrink: 0;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .acoes-principais {
    flex-direction: column;
  }

  .botao-acao {
    width: 100%;
    margin-bottom: 8px;
  }

  .banner-titulo {
    font-size: 14px;
  }

  .banner-descricao {
    font-size: 12px;
  }

  .rodape-info {
    flex-direction: column;
    align-items: flex-end;
  }

  .info-item {
    margin-left: 0;
    margin-bottom: 8px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Azul muito claro (background): #f0f5ff
- Roxo (destaque): #722ed1
- Roxo secundário: #9254de
- Roxo claro (background): #f9f0ff
- Verde (sucesso): #52c41a
- Verde secundário: #73d13d
- Verde claro (background): #f6ffed
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
- Amarelo (alerta): #faad14
- Amarelo claro (background): #fffbe6
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (placeholder): #999999
- Cinza muito claro (bordas): #d9d9d9
- Cinza ultra claro (backgrounds): #f5f5f5
- Cinza separador: #f0f0f0
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

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

.botao-padrao {
  background-color: #f5f5f5;
  color: #333333;
  border: 1px solid #d9d9d9;
}

.botao-padrao:hover {
  background-color: #e6e6e6;
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

.botao-roxo {
  background-color: #722ed1;
  color: white;
  border: 1px solid #722ed1;
}

.botao-roxo:hover {
  background-color: #9254de;
  border-color: #9254de;
}

.botao-sucesso {
  background-color: #52c41a;
  color: white;
  border: 1px solid #52c41a;
}

.botao-sucesso:hover {
  background-color: #73d13d;
  border-color: #73d13d;
}

.botao-perigo {
  background-color: #f5222d;
  color: white;
  border: 1px solid #f5222d;
}

.botao-perigo:hover {
  background-color: #ff4d4f;
  border-color: #ff4d4f;
}

.botao-texto {
  background-color: transparent;
  color: #1890ff;
  border: none;
}

.botao-texto:hover {
  background-color: #e6f7ff;
}

.botao-icone {
  padding: 8px;
}

.botao-icone .icone {
  margin-right: 0;
}

.botao[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
}
```

### Campos de Formulário

```css
.campo {
  display: block;
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo::placeholder {
  color: #999999;
}

.campo-grupo {
  display: flex;
  align-items: center;
}

.campo-grupo .campo {
  flex: 1;
  border-radius: 4px 0 0 4px;
}

.campo-grupo .botao {
  border-radius: 0 4px 4px 0;
  border-left: none;
}

.campo-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.campo-ajuda {
  display: block;
  margin-top: 4px;
  font-size: 12px;
  color: #999999;
}

.campo-erro {
  border-color: #f5222d;
}

.campo-erro:focus {
  box-shadow: 0 0 0 2px rgba(245, 34, 45, 0.2);
}

.mensagem-erro {
  display: block;
  margin-top: 4px;
  font-size: 12px;
  color: #f5222d;
}
```

### Badges e Tags

```css
.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20px;
  height: 20px;
  padding: 0 6px;
  font-size: 12px;
  border-radius: 10px;
  background-color: #f5f5f5;
  color: #666666;
}

.badge-primario {
  background-color: #e6f7ff;
  color: #1890ff;
}

.badge-roxo {
  background-color: #f9f0ff;
  color: #722ed1;
}

.badge-sucesso {
  background-color: #f6ffed;
  color: #52c41a;
}

.badge-alerta {
  background-color: #fffbe6;
  color: #faad14;
}

.badge-erro {
  background-color: #fff1f0;
  color: #f5222d;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
  background-color: #f5f5f5;
  color: #666666;
}

.tag-primario {
  background-color: #e6f7ff;
  color: #1890ff;
}

.tag-roxo {
  background-color: #f9f0ff;
  color: #722ed1;
}

.tag-sucesso {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-alerta {
  background-color: #fffbe6;
  color: #faad14;
}

.tag-erro {
  background-color: #fff1f0;
  color: #f5222d;
}

.tag .icone-fechar {
  margin-left: 4px;
  font-size: 10px;
  cursor: pointer;
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
  border-radius: 4px;
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
  font-size: 16px;
  font-weight: 600;
  color: #333333;
}

.modal-fechar {
  background: none;
  border: none;
  font-size: 16px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}

.modal-rodape {
  display: flex;
  justify-content: flex-end;
  padding: 16px 24px;
  border-top: 1px solid #f0f0f0;
}

.modal-rodape .botao {
  margin-left: 8px;
}
```

## Fluxos de Navegação

1. **Visualização de Contas a Receber**:

   - O usuário acessa o módulo "Contas a Receber"
   - Visualiza a lista de contas a receber
   - Pode filtrar por status (Em aberto, Emitidas, Recebidas, Atrasadas, Canceladas)
   - Pode pesquisar por cliente, número no banco ou número de documento
   - Pode ordenar a tabela por qualquer coluna

2. **Inclusão de Nova Conta a Receber**:

   - O usuário clica no botão "Incluir conta a receber"
   - Um formulário é aberto para preenchimento dos dados da nova conta
   - O usuário preenche os campos obrigatórios (cliente, valor, vencimento)
   - O usuário pode adicionar informações adicionais (histórico, número de documento, etc.)
   - O usuário salva a nova conta, que é adicionada à lista

3. **Gerenciamento de Recebimentos**:

   - O usuário seleciona uma ou mais contas a receber
   - Clica no botão "Gerenciar recebimentos"
   - Um modal é aberto com as opções de recebimento
   - O usuário seleciona a forma de recebimento
   - O usuário confirma o recebimento
   - As contas são atualizadas na lista

4. **Exportação e Importação**:
   - O usuário clica no botão "Mais ações"
   - Seleciona "Exportar" para exportar as contas a receber
   - Seleciona o formato de exportação (CSV, Excel, PDF)
   - O arquivo é gerado e baixado
   - Ou seleciona "Importar" para importar contas a receber
   - Seleciona o arquivo a ser importado
   - As contas são importadas e adicionadas à lista

## Diferenças em Relação ao Módulo Contas a Pagar

O módulo "Contas a Receber" compartilha muitas semelhanças estruturais com o módulo "Contas a Pagar", mas apresenta algumas diferenças importantes:

1. **Cores e Estilo Visual**:

   - O módulo "Contas a Receber" utiliza tons de roxo (#722ed1) como cor de destaque para os botões principais, enquanto o módulo "Contas a Pagar" utiliza tons de verde (#52c41a).
   - Os filtros de status e as badges têm cores específicas para cada módulo.

2. **Terminologia**:

   - "Gerenciar recebimentos" em vez de "Gerenciar pagamentos"
   - "Incluir conta a receber" em vez de "Incluir conta a pagar"
   - "Recebidas" em vez de "Pagas"

3. **Estrutura da Tabela**:

   - O módulo "Contas a Receber" inclui colunas adicionais como "Valor líquido" e "Data Emissão"
   - A coluna "Cliente" em vez de "Fornecedor"

4. **Filtros**:

   - O filtro padrão é "por meio de recebimento" em vez de "contas a pagar"
   - Os status disponíveis são adaptados para o contexto de recebimentos

5. **Funcionalidades Específicas**:
   - Opções de antecipação de recebíveis
   - Integração com meios de pagamento para clientes
   - Geração de boletos e links de pagamento

## Conclusão

O módulo "Contas a Receber" do ERP Revo apresenta uma interface funcional e intuitiva para o gerenciamento financeiro de recebimentos de clientes. A estrutura é bem organizada, com uma área de filtros e pesquisa no topo, seguida por uma tabela principal que lista todas as contas a receber cadastradas no sistema.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo selecionar contas, filtrar, pesquisar, ordenar e realizar ações em lote.

A paleta de cores é consistente com o restante do sistema, utilizando o roxo como cor de destaque para este módulo específico, o que ajuda a diferenciá-lo visualmente do módulo "Contas a Pagar". Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento financeiro do negócio, especificamente no que diz respeito ao controle de recebimentos e fluxo de caixa.
