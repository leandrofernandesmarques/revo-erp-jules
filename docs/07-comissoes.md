# Análise do Módulo Comissões - ERP Revo

## Estrutura Geral

O módulo "Comissões" do ERP Revo apresenta uma interface para gerenciamento de comissões de vendedores. A tela principal exibe uma mensagem de estado vazio quando não há vendedores cadastrados, com opções para filtrar por período e imprimir relatórios.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Comissões"
- Botão "Compartilhar"
- Botão "Imprimir"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Comissões</h1>
  </div>
  <div class="acoes-container">
    <a href="#" class="botao botao-secundario" id="btn-compartilhar">
      <span class="icone icone-compartilhar"></span>
      <span class="texto">Compartilhar</span>
    </a>
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
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

### Área de Filtros

A área de filtros permite selecionar o período para visualização das comissões:

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtro-periodo">
    <a href="#" class="filtro-link filtro-mes-atual">
      <span class="icone icone-calendario"></span>
      <span class="texto">Maio</span>
    </a>
  </div>
  <div class="filtro-acoes">
    <a href="#" class="filtro-link filtro-limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.filtros-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.filtro-periodo {
  display: flex;
  align-items: center;
}

.filtro-acoes {
  display: flex;
  gap: 16px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  border-radius: 4px;
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-link:hover {
  background-color: #f0f5ff;
}

.filtro-mes-atual {
  background-color: #f0f5ff;
  border: 1px solid #d6e4ff;
}

.filtro-limpar {
  color: #f5222d;
}

.filtro-link .icone {
  margin-right: 8px;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há vendedores cadastrados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <h2 class="titulo-vazio">
        Sua conta ainda não tem nenhum registro cadastrado.
      </h2>
      <p class="texto-vazio">
        Para inserir novos registros você pode acessar
        <a href="/cadastros/vendedores" class="link-acao"
          >Cadastros -> Vendedor</a
        >
        e clicar em incluir vendedor.
      </p>
    </div>
    <div class="ilustracao-vazio">
      <img
        src="/assets/images/ilustracao-vazio.svg"
        alt="Nenhum registro encontrado"
      />
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
  max-width: 800px;
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

.link-acao {
  color: #1890ff;
  text-decoration: none;
}

.link-acao:hover {
  text-decoration: underline;
}

.ilustracao-vazio {
  max-width: 300px;
  margin-top: 24px;
}

.ilustracao-vazio img {
  width: 100%;
  height: auto;
}
```

### Tabela de Comissões

Quando houver vendedores cadastrados, a área de conteúdo exibirá uma tabela de comissões:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-comissoes">
      <thead>
        <tr>
          <th class="coluna-vendedor">
            <div class="cabecalho-ordenavel">
              <span class="texto">Vendedor</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-vendas">
            <div class="cabecalho-ordenavel">
              <span class="texto">Vendas</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-valor-vendas">
            <div class="cabecalho-ordenavel">
              <span class="texto">Valor Vendas</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-comissao">
            <div class="cabecalho-ordenavel">
              <span class="texto">Comissão</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Vendedores serão adicionados dinamicamente -->
      </tbody>
      <tfoot>
        <tr>
          <td class="rodape-label">Total:</td>
          <td class="rodape-valor">0</td>
          <td class="rodape-valor">R$ 0,00</td>
          <td class="rodape-valor">R$ 0,00</td>
          <td></td>
        </tr>
      </tfoot>
    </table>
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

.tabela-comissoes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-comissoes th,
.tabela-comissoes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-comissoes th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-comissoes tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-vendedor {
  width: 40%;
}

.coluna-vendas,
.coluna-valor-vendas,
.coluna-comissao {
  width: 20%;
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

.rodape-label {
  font-weight: 500;
  color: #666666;
}

.rodape-valor {
  font-weight: 500;
  color: #333333;
  text-align: right;
}
```

### Detalhes de Comissão

Ao clicar em um vendedor, é exibido um modal com os detalhes das comissões:

**Estrutura HTML:**

```html
<div class="modal-detalhes-comissao">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h2 class="modal-titulo">Detalhes de Comissão - João Silva</h2>
      <button class="botao-fechar">&times;</button>
    </div>
    <div class="modal-corpo">
      <div class="info-periodo">
        <span class="label">Período:</span>
        <span class="valor">Maio/2025</span>
      </div>

      <div class="tabela-container">
        <table class="tabela-detalhes">
          <thead>
            <tr>
              <th class="coluna-data">Data</th>
              <th class="coluna-pedido">Pedido</th>
              <th class="coluna-cliente">Cliente</th>
              <th class="coluna-valor">Valor</th>
              <th class="coluna-comissao">Comissão</th>
            </tr>
          </thead>
          <tbody>
            <!-- Pedidos serão adicionados dinamicamente -->
          </tbody>
          <tfoot>
            <tr>
              <td colspan="3" class="rodape-label">Total:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td class="rodape-valor">R$ 0,00</td>
            </tr>
          </tfoot>
        </table>
      </div>

      <div class="acoes-modal">
        <button class="botao botao-primario" id="btn-imprimir-detalhes">
          <span class="icone icone-imprimir"></span>
          <span class="texto">Imprimir</span>
        </button>
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
.modal-detalhes-comissao {
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

.info-periodo {
  margin-bottom: 16px;
}

.info-periodo .label {
  font-weight: 500;
  color: #666666;
  margin-right: 8px;
}

.info-periodo .valor {
  color: #333333;
}

.tabela-container {
  margin-bottom: 24px;
  overflow-x: auto;
}

.tabela-detalhes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-detalhes th,
.tabela-detalhes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-detalhes th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
}

.coluna-data,
.coluna-pedido {
  width: 100px;
}

.coluna-valor,
.coluna-comissao {
  width: 120px;
  text-align: right;
}

.acoes-modal {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
}
```

## Interações JavaScript

### Filtro de Período

```javascript
// Código para seleção de período
document
  .querySelector(".filtro-mes-atual")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o seletor de mês
    const meses = [
      "Janeiro",
      "Fevereiro",
      "Março",
      "Abril",
      "Maio",
      "Junho",
      "Julho",
      "Agosto",
      "Setembro",
      "Outubro",
      "Novembro",
      "Dezembro",
    ];

    const anos = [2023, 2024, 2025];

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
        <div class="selecao-ano">
          <label class="selecao-label">Ano:</label>
          <div class="selecao-opcoes">
            ${anos
              .map(
                (ano) => `
              <button class="botao-opcao ${
                ano === 2025 ? "ativo" : ""
              }" data-ano="${ano}">${ano}</button>
            `
              )
              .join("")}
          </div>
        </div>
        <div class="selecao-mes">
          <label class="selecao-label">Mês:</label>
          <div class="selecao-opcoes">
            ${meses
              .map(
                (mes, index) => `
              <button class="botao-opcao ${
                index === 4 ? "ativo" : ""
              }" data-mes="${index + 1}">${mes}</button>
            `
              )
              .join("")}
          </div>
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

    // Seleção de ano
    modal.querySelectorAll(".selecao-ano .botao-opcao").forEach((botao) => {
      botao.addEventListener("click", function () {
        modal.querySelectorAll(".selecao-ano .botao-opcao").forEach((b) => {
          b.classList.remove("ativo");
        });
        this.classList.add("ativo");
      });
    });

    // Seleção de mês
    modal.querySelectorAll(".selecao-mes .botao-opcao").forEach((botao) => {
      botao.addEventListener("click", function () {
        modal.querySelectorAll(".selecao-mes .botao-opcao").forEach((b) => {
          b.classList.remove("ativo");
        });
        this.classList.add("ativo");
      });
    });

    // Aplicar filtro
    modal
      .querySelector("#btn-aplicar-periodo")
      .addEventListener("click", function () {
        const anoSelecionado = modal
          .querySelector(".selecao-ano .botao-opcao.ativo")
          .getAttribute("data-ano");
        const mesSelecionado = modal
          .querySelector(".selecao-mes .botao-opcao.ativo")
          .getAttribute("data-mes");
        const mesNome = meses[parseInt(mesSelecionado) - 1];

        // Atualiza o texto do filtro
        document.querySelector(".filtro-mes-atual .texto").textContent =
          mesNome;

        // Carrega as comissões do período
        carregarComissoes(anoSelecionado, mesSelecionado);

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

// Código para limpar filtros
document
  .querySelector(".filtro-limpar")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Reseta o filtro para o mês atual
    const hoje = new Date();
    const mesAtual = hoje.getMonth();
    const anoAtual = hoje.getFullYear();
    const meses = [
      "Janeiro",
      "Fevereiro",
      "Março",
      "Abril",
      "Maio",
      "Junho",
      "Julho",
      "Agosto",
      "Setembro",
      "Outubro",
      "Novembro",
      "Dezembro",
    ];

    document.querySelector(".filtro-mes-atual .texto").textContent =
      meses[mesAtual];

    // Carrega as comissões do período atual
    carregarComissoes(anoAtual, mesAtual + 1);
  });

function carregarComissoes(ano, mes) {
  console.log(`Carregando comissões de ${mes}/${ano}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/comissoes?ano=${ano}&mes=${mes}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaComissoes(data);
  //   });
}
```

### Impressão de Relatório

```javascript
// Código para impressão de relatório
document.querySelector('#btn-imprimir').addEventListener('click', function() {
  const periodo = document.querySelector('.filtro-mes-atual .texto').textContent;
  const ano = new Date().getFullYear();

  console.log(`Imprimindo relatório de comissões de ${periodo}/${ano}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/comissoes/relatorio?periodo=${periodo}&ano=${ano}`)
  //   .then(response => response.blob())
  //   .then(blob => {
  //     const u
(Content truncated due to size limit. Use line ranges to read in chunks)
```
