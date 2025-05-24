# Análise do Módulo Relatórios de Finanças - ERP Revo

## Estrutura Geral

O módulo "Relatórios" da seção de Finanças do ERP Revo apresenta uma interface organizada para acesso a diferentes tipos de relatórios financeiros. A página exibe categorias de relatórios e uma lista de relatórios disponíveis, permitindo ao usuário visualizar informações financeiras de forma estruturada e gráfica.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Ações

A seção superior contém o título da página e botões de ação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/financas" class="breadcrumb-item">Finanças</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Relatórios</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Relatórios de Finanças</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao" id="btn-outros-relatorios">
      <span class="icone icone-relatorios"></span>
      <span class="texto">outros relatórios</span>
    </button>
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
  justify-content: flex-end;
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
  background-color: #1890ff;
  color: white;
  border: 1px solid #1890ff;
}

.botao-acao:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
}
```

### Categorias de Relatórios

A seção de categorias permite filtrar os relatórios por tipo:

**Estrutura HTML:**

```html
<div class="categorias-container">
  <div class="categorias-lista">
    <a href="#" class="categoria-item categoria-ativa">
      <span class="texto">Geral</span>
    </a>
    <a href="#" class="categoria-item">
      <span class="texto">Caixa</span>
    </a>
    <a href="#" class="categoria-item">
      <span class="texto">Contas a Pagar</span>
    </a>
    <a href="#" class="categoria-item">
      <span class="texto">Contas a Receber</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.categorias-container {
  margin-bottom: 24px;
}

.categorias-lista {
  display: flex;
  align-items: center;
  border-bottom: 1px solid #f0f0f0;
  overflow-x: auto;
  padding-bottom: 1px;
}

.categoria-item {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
  white-space: nowrap;
}

.categoria-item:hover {
  color: #1890ff;
}

.categoria-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}
```

### Lista de Relatórios

A lista de relatórios disponíveis:

**Estrutura HTML:**

```html
<div class="relatorios-container">
  <div class="relatorios-lista">
    <a href="/relatorios/balancete" class="relatorio-item">
      <div class="relatorio-conteudo">
        <h3 class="relatorio-titulo">Balancete</h3>
        <p class="relatorio-descricao">
          Relatório e gráfico com as entradas e saídas do período.
        </p>
      </div>
    </a>

    <a href="/relatorios/fluxo_caixa" class="relatorio-item">
      <div class="relatorio-conteudo">
        <h3 class="relatorio-titulo">Fluxo de Caixa</h3>
        <p class="relatorio-descricao">
          Relatório e gráfico da projeção das entradas e saídas futuras de
          acordo com as contas a pagar e receber.
        </p>
      </div>
    </a>

    <!-- Outros relatórios seriam listados aqui -->
  </div>
</div>
```

**Estilos CSS:**

```css
.relatorios-container {
  padding: 0 24px;
}

.relatorios-lista {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.relatorio-item {
  display: block;
  padding: 16px;
  border-radius: 4px;
  background-color: #ffffff;
  border: 1px solid #f0f0f0;
  text-decoration: none;
  transition: box-shadow 0.2s ease, border-color 0.2s ease;
}

.relatorio-item:hover {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.09);
  border-color: #d9d9d9;
}

.relatorio-conteudo {
  display: flex;
  flex-direction: column;
}

.relatorio-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.relatorio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}
```

## Interações JavaScript

### Navegação entre Categorias

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Navegação entre categorias
  const categorias = document.querySelectorAll(".categoria-item");

  categorias.forEach((categoria) => {
    categoria.addEventListener("click", function (e) {
      e.preventDefault();

      // Remove a classe ativa de todas as categorias
      categorias.forEach((c) => c.classList.remove("categoria-ativa"));

      // Adiciona a classe ativa à categoria clicada
      this.classList.add("categoria-ativa");

      // Filtra os relatórios de acordo com a categoria selecionada
      const categoriaTexto = this.querySelector(".texto").textContent;
      filtrarRelatoriosPorCategoria(categoriaTexto);
    });
  });

  function filtrarRelatoriosPorCategoria(categoria) {
    // Aqui seria implementada a lógica para filtrar os relatórios
    console.log("Filtrando relatórios por categoria:", categoria);

    // Exemplo de implementação:
    const relatorios = document.querySelectorAll(".relatorio-item");

    relatorios.forEach((relatorio) => {
      const relatorioCategoria = relatorio.getAttribute("data-categoria");

      if (categoria === "Geral" || relatorioCategoria === categoria) {
        relatorio.style.display = "block";
      } else {
        relatorio.style.display = "none";
      }
    });
  }
});
```

### Botão Outros Relatórios

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão outros relatórios
  const botaoOutrosRelatorios = document.getElementById(
    "btn-outros-relatorios"
  );

  if (botaoOutrosRelatorios) {
    botaoOutrosRelatorios.addEventListener("click", function () {
      // Aqui seria implementada a lógica para abrir o modal de outros relatórios
      abrirModalOutrosRelatorios();
    });
  }

  function abrirModalOutrosRelatorios() {
    // Aqui seria implementada a lógica para abrir o modal
    console.log("Abrindo modal de outros relatórios");

    // Exemplo de implementação:
    const modal = document.createElement("div");
    modal.className = "modal";
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h3 class="modal-titulo">Outros Relatórios</h3>
          <button class="modal-fechar" id="btn-fechar-modal">×</button>
        </div>
        <div class="modal-corpo">
          <div class="modal-categorias">
            <a href="#" class="modal-categoria-item modal-categoria-ativa">Finanças</a>
            <a href="#" class="modal-categoria-item">Vendas</a>
            <a href="#" class="modal-categoria-item">Suprimentos</a>
            <a href="#" class="modal-categoria-item">Cadastros</a>
          </div>
          <div class="modal-relatorios-lista">
            <!-- Lista de relatórios de outras categorias -->
          </div>
        </div>
      </div>
    `;

    document.body.appendChild(modal);

    // Adiciona evento para fechar o modal
    const btnFecharModal = modal.querySelector("#btn-fechar-modal");
    btnFecharModal.addEventListener("click", function () {
      document.body.removeChild(modal);
    });
  }
});
```

## Tela de Relatório Específico

Embora não esteja visível na tela inicial, a visualização de um relatório específico é um componente importante deste módulo. Abaixo está a estrutura esperada para o relatório de Balancete:

**Estrutura HTML:**

```html
<div class="relatorio-especifico-container">
  <div class="relatorio-especifico-cabecalho">
    <h2 class="relatorio-especifico-titulo">Balancete</h2>
    <div class="relatorio-especifico-acoes">
      <button class="botao-acao" id="btn-voltar">
        <span class="icone icone-voltar"></span>
        <span class="texto">Voltar</span>
      </button>
      <button class="botao-acao" id="btn-imprimir">
        <span class="icone icone-imprimir"></span>
        <span class="texto">Imprimir</span>
      </button>
      <button class="botao-acao" id="btn-exportar">
        <span class="icone icone-exportar"></span>
        <span class="texto">Exportar</span>
      </button>
    </div>
  </div>

  <div class="relatorio-especifico-filtros">
    <div class="filtro-grupo">
      <label class="filtro-label">Período:</label>
      <div class="filtro-campo-grupo">
        <input
          type="date"
          class="filtro-campo"
          id="data-inicial"
          name="data-inicial"
        />
        <span class="filtro-separador">até</span>
        <input
          type="date"
          class="filtro-campo"
          id="data-final"
          name="data-final"
        />
      </div>
    </div>

    <div class="filtro-grupo">
      <label class="filtro-label">Conta:</label>
      <select class="filtro-campo filtro-select" id="conta" name="conta">
        <option value="todas">Todas as contas</option>
        <option value="caixa">Caixa</option>
        <option value="banco">Banco</option>
      </select>
    </div>

    <button class="botao-acao" id="btn-filtrar">
      <span class="icone icone-filtrar"></span>
      <span class="texto">Filtrar</span>
    </button>
  </div>

  <div class="relatorio-especifico-grafico">
    <div class="grafico-container" id="grafico-balancete">
      <!-- Aqui seria renderizado o gráfico -->
    </div>
  </div>

  <div class="relatorio-especifico-tabela-container">
    <table class="relatorio-especifico-tabela">
      <thead>
        <tr>
          <th class="coluna-data">
            <div class="cabecalho-coluna">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-descricao">
            <div class="cabecalho-coluna">
              <span class="texto">Descrição</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-entradas">
            <div class="cabecalho-coluna">
              <span class="texto">Entradas</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saidas">
            <div class="cabecalho-coluna">
              <span class="texto">Saídas</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saldo">
            <div class="cabecalho-coluna">
              <span class="texto">Saldo</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr class="linha-resumo">
          <td colspan="2" class="coluna-resumo">Saldo Anterior</td>
          <td class="coluna-entradas"></td>
          <td class="coluna-saidas"></td>
          <td class="coluna-saldo">1.500,00</td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">01/05/2025</td>
          <td class="coluna-descricao">Recebimento Cliente ABC</td>
          <td class="coluna-entradas">1.200,00</td>
          <td class="coluna-saidas"></td>
          <td class="coluna-saldo">2.700,00</td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">03/05/2025</td>
          <td class="coluna-descricao">Pagamento Fornecedor XYZ</td>
          <td class="coluna-entradas"></td>
          <td class="coluna-saidas">500,00</td>
          <td class="coluna-saldo">2.200,00</td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">10/05/2025</td>
          <td class="coluna-descricao">Pagamento de Aluguel</td>
          <td class="coluna-entradas"></td>
          <td class="coluna-saidas">800,00</td>
          <td class="coluna-saldo">1.400,00</td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">15/05/2025</td>
          <td class="coluna-descricao">Recebimento Cliente DEF</td>
          <td class="coluna-entradas">950,00</td>
          <td class="coluna-saidas"></td>
          <td class="coluna-saldo">2.350,00</td>
        </tr>
        <tr class="linha-resumo linha-total">
          <td colspan="2" class="coluna-resumo">Total do Período</td>
          <td class="coluna-entradas">2.150,00</td>
          <td class="coluna-saidas">1.300,00</td>
          <td class="coluna-saldo">850,00</td>
        </tr>
        <tr class="linha-resumo linha-saldo-final">
          <td colspan="2" class="coluna-resumo">Saldo Final</td>
          <td class="coluna-entradas"></td>
          <td class="coluna-saidas"></td>
          <td class="coluna-saldo">2.350,00</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

**Estilos CSS:**

```css
.relatorio-especifico-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.relatorio-especifico-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-especifico-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.relatorio-especifico-acoes {
  display: flex;
  gap: 8px;
}

.relatorio-especifico-filtros {
  display: flex;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
  gap: 16px;
  flex-wrap: wrap;
}

.filtro-grupo {
  display: flex;
  align-items: center;
}

.filtro-label {
  font-size: 14px;
  color: #666666;
  margin-right: 8px;
}

.filtro-campo {
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.filtro-campo:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.filtro-campo-grupo {
  display: flex;
  align-items: center;
}

.filtro-separador {
  margin: 0 8px;
  color: #666666;
}

.filtro-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.relatorio-especifico-grafico {
  padding: 24px;
  border-bottom: 1px solid #f0f0f0;
}

.grafico-container {
  width: 100%;
  height: 300px;
  background-color: #fafafa;
  border: 1px solid #f0f0f0;
  border-radius: 4px;
}

.relatorio-especifico-tabela-container {
  overflow-x: auto;
}

.relatorio-especifico-tabela {
  width: 100%;
  border-collapse: collapse;
}

.relatorio-especifico-tabela th,
.relatorio-especifico-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-especifico-tabela th {
  background-color: #fafa
(Content truncated due to size limit. Use line ranges to read in chunks)
```
