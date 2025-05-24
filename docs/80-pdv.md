# Análise do Módulo PDV - ERP Revo

## Estrutura Geral

O módulo "PDV" (Ponto de Venda) do ERP Revo apresenta uma interface minimalista para operações de caixa. A tela inicial exibe informações básicas como horário e data atual, além de botões para abrir o caixa e visualizar detalhes do caixa.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção:

- Título "PDV"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">PDV</h1>
  </div>
</div>
```

**Estilos CSS:**

```css
.modulo-cabecalho {
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
```

### Área Central

A área central exibe o horário atual, a data e os botões de ação:

**Estrutura HTML:**

```html
<div class="pdv-container">
  <div class="pdv-info">
    <div class="pdv-relogio">18:39</div>
    <div class="pdv-data">segunda, 19 de Maio de 2025</div>
  </div>

  <div class="pdv-acoes">
    <button class="botao botao-primario botao-grande" id="btn-abrir-caixa">
      <span class="texto">Abrir caixa</span>
      <span class="atalho">CTRL+ENTER</span>
    </button>

    <a href="#/caixa/detalhes" class="link-detalhes">ver detalhes do caixa</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.pdv-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: calc(100vh - 120px);
  padding: 24px;
}

.pdv-info {
  text-align: center;
  margin-bottom: 48px;
}

.pdv-relogio {
  font-size: 64px;
  font-weight: 300;
  color: #333333;
  margin-bottom: 8px;
}

.pdv-data {
  font-size: 16px;
  color: #666666;
}

.pdv-acoes {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.botao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
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

.botao-grande {
  padding: 16px 32px;
  font-size: 18px;
  min-width: 200px;
}

.botao .texto {
  margin-right: 8px;
}

.botao .atalho {
  font-size: 12px;
  opacity: 0.8;
}

.link-detalhes {
  margin-top: 16px;
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.link-detalhes:hover {
  text-decoration: underline;
}
```

## Interações JavaScript

### Atualização do Relógio

O módulo atualiza o relógio em tempo real:

```javascript
// Código para atualização do relógio
function atualizarRelogio() {
  const agora = new Date();
  const horas = agora.getHours().toString().padStart(2, "0");
  const minutos = agora.getMinutes().toString().padStart(2, "0");

  document.querySelector(".pdv-relogio").textContent = `${horas}:${minutos}`;
}

// Atualiza o relógio a cada minuto
setInterval(atualizarRelogio, 60000);

// Atualiza o relógio imediatamente
atualizarRelogio();
```

### Abertura do Caixa

O botão de abertura do caixa exibe um modal para iniciar as operações:

```javascript
// Código para abertura do caixa
document
  .querySelector("#btn-abrir-caixa")
  .addEventListener("click", function () {
    abrirModalCaixa();
  });

// Atalho de teclado para abrir o caixa (Ctrl+Enter)
document.addEventListener("keydown", function (e) {
  if (e.ctrlKey && e.key === "Enter") {
    abrirModalCaixa();
  }
});

function abrirModalCaixa() {
  // Verifica se já existe um caixa aberto
  fetch("/api/pdv/status")
    .then((response) => response.json())
    .then((data) => {
      if (data.caixa_aberto) {
        // Redireciona para a tela de PDV com caixa aberto
        window.location.href = "/pdv/venda";
      } else {
        // Abre o modal para abertura de caixa
        exibirModalAberturaCaixa();
      }
    });
}

function exibirModalAberturaCaixa() {
  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Abertura de Caixa</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <form id="form-abertura-caixa">
          <div class="form-grupo">
            <label for="valor_inicial">Valor Inicial (R$)</label>
            <input type="text" id="valor_inicial" name="valor_inicial" placeholder="0,00" required>
          </div>
          <div class="form-grupo">
            <label for="observacoes">Observações</label>
            <textarea id="observacoes" name="observacoes" rows="3"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar">Confirmar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Formata o campo de valor
  const inputValor = document.querySelector("#valor_inicial");
  inputValor.addEventListener("input", function () {
    let valor = this.value.replace(/\D/g, "");
    valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
    this.value = valor;
  });

  // Foca no campo de valor inicial
  inputValor.focus();

  // Adiciona eventos aos botões
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  document
    .querySelector(".botao-fechar")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  document
    .querySelector("#btn-confirmar")
    .addEventListener("click", function () {
      const form = document.querySelector("#form-abertura-caixa");

      if (form.checkValidity()) {
        // Coleta os dados do formulário
        const valorInicial = form.valor_inicial.value.replace(",", ".");
        const observacoes = form.observacoes.value;

        // Envia para a API
        fetch("/api/pdv/abrir", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            valor_inicial: valorInicial,
            observacoes: observacoes,
          }),
        })
          .then((response) => {
            if (response.ok) {
              // Redireciona para a tela de PDV com caixa aberto
              window.location.href = "/pdv/venda";
            } else {
              throw new Error("Erro ao abrir caixa");
            }
          })
          .catch((error) => {
            alert(`Erro ao abrir caixa: ${error.message}`);
          });
      } else {
        // Exibe mensagem de validação
        form.reportValidity();
      }
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}
```

## Tela de PDV com Caixa Aberto

Quando o caixa é aberto, o usuário é redirecionado para a tela de PDV com funcionalidades completas:

**Estrutura HTML:**

```html
<div class="pdv-venda-container">
  <div class="pdv-venda-cabecalho">
    <div class="pdv-venda-info">
      <div class="pdv-venda-operador">
        <span class="label">Operador:</span>
        <span class="valor">João Silva</span>
      </div>
      <div class="pdv-venda-caixa">
        <span class="label">Caixa:</span>
        <span class="valor">Caixa 1</span>
      </div>
      <div class="pdv-venda-data">
        <span class="label">Data:</span>
        <span class="valor">19/05/2025</span>
      </div>
    </div>
    <div class="pdv-venda-acoes">
      <button class="botao botao-secundario" id="btn-fechar-caixa">
        <span class="icone icone-fechar"></span>
        <span class="texto">Fechar Caixa</span>
      </button>
    </div>
  </div>

  <div class="pdv-venda-conteudo">
    <div class="pdv-venda-esquerda">
      <div class="pdv-venda-cliente">
        <div class="pdv-venda-cliente-cabecalho">
          <h2 class="titulo">Cliente</h2>
          <button class="botao botao-link" id="btn-selecionar-cliente">
            <span class="icone icone-cliente"></span>
            <span class="texto">Selecionar Cliente</span>
          </button>
        </div>
        <div class="pdv-venda-cliente-info">
          <div class="info-item">
            <span class="label">Nome:</span>
            <span class="valor">Consumidor Final</span>
          </div>
          <div class="info-item">
            <span class="label">CPF/CNPJ:</span>
            <span class="valor">-</span>
          </div>
        </div>
      </div>

      <div class="pdv-venda-produtos">
        <div class="pdv-venda-produtos-cabecalho">
          <h2 class="titulo">Produtos</h2>
        </div>
        <div class="pdv-venda-produtos-busca">
          <div class="campo-busca">
            <input
              type="text"
              placeholder="Código, nome ou código de barras"
              id="input-busca-produto"
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>
        <div class="pdv-venda-produtos-lista">
          <table class="tabela-produtos">
            <thead>
              <tr>
                <th class="coluna-codigo">Código</th>
                <th class="coluna-descricao">Descrição</th>
                <th class="coluna-quantidade">Qtde</th>
                <th class="coluna-unitario">Unitário</th>
                <th class="coluna-total">Total</th>
                <th class="coluna-acoes"></th>
              </tr>
            </thead>
            <tbody>
              <!-- Produtos serão adicionados dinamicamente -->
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <div class="pdv-venda-direita">
      <div class="pdv-venda-resumo">
        <div class="pdv-venda-resumo-cabecalho">
          <h2 class="titulo">Resumo</h2>
        </div>
        <div class="pdv-venda-resumo-valores">
          <div class="resumo-item">
            <span class="label">Subtotal:</span>
            <span class="valor">R$ 0,00</span>
          </div>
          <div class="resumo-item">
            <span class="label">Desconto:</span>
            <span class="valor">R$ 0,00</span>
          </div>
          <div class="resumo-item total">
            <span class="label">Total:</span>
            <span class="valor">R$ 0,00</span>
          </div>
        </div>
      </div>

      <div class="pdv-venda-pagamento">
        <div class="pdv-venda-pagamento-cabecalho">
          <h2 class="titulo">Pagamento</h2>
        </div>
        <div class="pdv-venda-pagamento-opcoes">
          <button class="botao-pagamento" data-forma="dinheiro">
            <span class="icone icone-dinheiro"></span>
            <span class="texto">Dinheiro</span>
          </button>
          <button class="botao-pagamento" data-forma="cartao">
            <span class="icone icone-cartao"></span>
            <span class="texto">Cartão</span>
          </button>
          <button class="botao-pagamento" data-forma="pix">
            <span class="icone icone-pix"></span>
            <span class="texto">PIX</span>
          </button>
          <button class="botao-pagamento" data-forma="outros">
            <span class="icone icone-outros"></span>
            <span class="texto">Outros</span>
          </button>
        </div>
      </div>

      <div class="pdv-venda-acoes-finais">
        <button class="botao botao-secundario" id="btn-cancelar-venda">
          <span class="icone icone-cancelar"></span>
          <span class="texto">Cancelar</span>
        </button>
        <button class="botao botao-primario" id="btn-finalizar-venda" disabled>
          <span class="icone icone-finalizar"></span>
          <span class="texto">Finalizar Venda</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pdv-venda-container {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 60px);
  background-color: #f5f5f5;
}

.pdv-venda-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.pdv-venda-info {
  display: flex;
  gap: 24px;
}

.pdv-venda-operador,
.pdv-venda-caixa,
.pdv-venda-data {
  display: flex;
  align-items: center;
}

.label {
  font-size: 14px;
  color: #666666;
  margin-right: 4px;
}

.valor {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.pdv-venda-conteudo {
  display: flex;
  flex: 1;
  overflow: hidden;
}

.pdv-venda-esquerda {
  flex: 3;
  display: flex;
  flex-direction: column;
  padding: 16px;
  overflow: auto;
}

.pdv-venda-direita {
  flex: 1;
  min-width: 300px;
  display: flex;
  flex-direction: column;
  padding: 16px;
  background-color: #ffffff;
  border-left: 1px solid #e0e0e0;
}

.pdv-venda-cliente,
.pdv-venda-produtos,
.pdv-venda-resumo,
.pdv-venda-pagamento {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 16px;
}

.pdv-venda-cliente-cabecalho,
.pdv-venda-produtos-cabecalho,
.pdv-venda-resumo-cabecalho,
.pdv-venda-pagamento-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-bottom: 1px solid #f0f0f0;
}

.titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.pdv-venda-cliente-info {
  padding: 12px 16px;
}

.info-item {
  margin-bottom: 8px;
}

.info-item:last-child {
  margin-bottom: 0;
}

.pdv-venda-produtos-busca {
  padding: 12px 16px;
  border-bottom: 1px solid #f0f0f0;
}

.campo-busca {
  position: relative;
}

.campo-busca input {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
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

.pdv-venda-produtos-lista {
  padding: 0 16px 16px;
  overflow: auto;
  max-height: 300px;
}

.tabela-produtos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos th,
.tabela-produtos td {
  padding: 8px 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-codigo {
  width: 80px;
}

.coluna-quantidade,
.coluna-unitario,
.coluna-total {
  width: 100px;
  text-align: right;
}

.coluna-acoes {
  width: 40px;
  text-align: center;
}

.pdv-venda-resumo-valores {
  padding: 16px;
}

.resumo-item {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}

.resumo-item.total {
  margin-top: 16px;
  padding-top: 16px;
  border-top: 1px solid #f0f0f0;
}

.resumo-item.total .label,
.resumo-item.total .valor {
  font-size: 18px;
  font-weight: 500;
}

.pdv-venda-pagamento-opcoes {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 8px;
  padding: 16px;
}

.botao-pagamento {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 16px;
  background-color: #f5f5f5;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pagamento:hover {
  background-color: #e6f7ff;
  border-color: #91d5ff;
}

.botao-pagamento .icone {
  font-size: 24px;
  margin-bottom: 8px;
  color: #1890ff;
}

.botao-pagamento .texto {
  font-size: 14px;
  color: #333333;
}

.pdv-venda-acoes-finais {
  display: flex;
  justify-content: space-between;
  margin-top: auto;
  padding-top: 16px;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao-link {
  background: none;
  border: none;
  color: #1890ff;
  padding: 0;
  font-size: 14px;
  cursor: pointer;
}

.botao-link:hover {
  text-decoration: underline;
}

.botao[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
}
```

## Interações JavaScript da Tela de PDV

```javascript
// Código para busca de produtos
document
  .querySelector("#input-busca-produto")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      buscarProduto(this.value);
    }
  });

document.querySelector(".botao-busca").addEventListener("click", function () {
  const termoBusca = document.querySelector("#input-busca-produto").value;
  buscarProduto(termoBusca);
});

function buscarProduto(termo) {
  if (!termo) return;

  fetch(`/api/produtos/busca?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      if (data.length === 0) {
        alert("Produto não encontrado");
        return;
      }

      if (data.length === 1) {
        // Adiciona o produto diretamente
        adicionarProduto(data[0]);
      } else {
        // Exibe modal para seleção do produto
        exibirModalSelecaoProduto(data);
      }
    })
    .catch((error) => {
      console.error("Erro ao buscar produto:", error);
      alert("Erro ao buscar produto");
    });

  // Limpa o campo de busca
  document.querySelector("#input-busca-produto").value = "";
}

function adicionarProduto(produto) {
  // Verifica se o produto já está na lista
  const tbody = document.querySelector(".tabela-produtos tbody");
  const linhas = tbody.querySelectorAll("tr");

  for (const linha of linhas) {
    if (linha.getAttribute("data-produto-id") === produto.id.toString()) {
      // Incrementa a quantidade
      const tdQuantidade = linha.querySelector(".coluna-quantidade");
      const inputQuantidade = tdQuantidade.querySelector("input");
      const quantidade = parseInt(inputQuantidade.value) + 1;
      inputQuantidade.value = quantidade;

      // Atualiza o total
      const tdUnitario = linha.querySelector(".coluna-unitario");
      const valorUnitario = parseFloat(tdUnitario.getAttribute("data-valor"));
      const tdTotal = linha.querySelector(".coluna-total");
      const total = valorUnitario * quantidade;
      tdTotal.textContent = `R$ ${total.toFixed(2)}`;
      tdTotal.setAttribute("data-valor", total.toFixed(2));

      // Atualiza o resumo
      atualizarResumo();
      return;
    }
  }

  // Adiciona o produto à tabela
  const tr = document.createElement("tr");
  tr.setAttribute("data-produto-id", produto.id);

  tr.innerHTML = `
    <td class="coluna-codigo">${produto.codigo}</td>
    <td class="coluna-descricao">${produto.descricao}</td>
    <td class="coluna-quantidade">
      <input type="number" min="1" value="1" class="input-quantidade">
    </td>
    <td class="coluna-unitario" data-valor="${produto.preco}">${formatarMoeda(
    produto.preco
  )}</td>
    <td class="coluna-total" data-valor="${produto.preco}">${formatarMoeda(
    produto.preco
  )}</td>
    <td class="coluna-acoes">
      <button class="botao-remover">
        <span class="icone icone-remover"></span>
      </button>
    </td>
  `;

  tbody.appendChild(tr);

  // Adiciona eventos
  const inputQuantidade = tr.querySelector(".input-quantidade");
  inputQuantidade.addEventListener("change", function () {
    if (parseInt(this.value) < 1) {
      this.value = 1;
    }

    const linha = this.closest("tr");
    const tdUnitario = linha.querySelector(".coluna-unitario");
    const valorUnitario = parseFloat(tdUnitario.getAttribute("data-valor"));
    const quantidade = parseInt(this.value);

    const tdTotal = linha.querySelector(".coluna-total");
    const total = valorUnitario * quantidade;
    tdTotal.textContent = formatarMoeda(total);
    tdTotal.setAttribute("data-valor", total.toFixed(2));

    atualizarResumo();
  });

  const botaoRemover = tr.querySelector(".botao-remover");
  botaoRemover.addEventListener("click", function () {
    const linha = this.closest("tr");
    linha.remove();
    atualizarResumo();
  });

  // Atualiza o resumo
  atualizarResumo();

  // Habilita o botão de finalizar venda
  document.querySelector("#btn-finalizar-venda").disabled = false;
}

function exibirModalSelecaoProduto(produtos) {
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
                  <td>${formatarMoeda(produto.preco)}</td>
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

      adicionarProduto(produto);
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

function atualizarResumo() {
  let subtotal = 0;

  // Calcula o subtotal
  document.querySelectorAll(".tabela-produtos tbody tr").forEach((linha) => {
    const tdTotal = linha.querySelector(".coluna-total");
    subtotal += parseFloat(tdTotal.getAttribute("data-valor"));
  });

  // Atualiza os valores no resumo
  document.querySelector(".resumo-item:nth-child(1) .valor").textContent =
    formatarMoeda(subtotal);

  // Por enquanto, o desconto é zero
  const desconto = 0;
  document.querySelector(".resumo-item:nth-child(2) .valor").textContent =
    formatarMoeda(desconto);

  // Calcula o total
  const total = subtotal - desconto;
  document.querySelector(".resumo-item.total .valor").textContent =
    formatarMoeda(total);

  // Habilita ou desabilita o botão de finalizar venda
  document.querySelector("#btn-finalizar-venda").disabled = total <= 0;
}

function formatarMoeda(valor) {
  return `R$ ${parseFloat(valor).toFixed(2)}`;
}

// Código para seleção de cliente
document
  .querySelector("#btn-selecionar-cliente")
  .addEventListener("click", function () {
    exibirModalSelecaoCliente();
  });

function exibirModalSelecaoCliente() {
  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Cliente</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="campo-busca">
          <input type="text" placeholder="Buscar cliente por nome, CPF ou CNPJ" id="input-busca-cliente">
          <button class="botao-busca">
            <span class="icone icone-busca"></span>
          </button>
        </div>
        <div class="lista-clientes">
          <table class="tabela-selecao-clientes">
            <thead>
              <tr>
                <th>Nome</th>
                <th>CPF/CNPJ</th>
                <th>Telefone</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              <!-- Clientes serão adicionados dinamicamente -->
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

  const inputBuscaCliente = modal.querySelector("#input-busca-cliente");
  inputBuscaCliente.addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      buscarCliente(this.value);
    }
  });

  modal.querySelector(".botao-busca").addEventListener("click", function () {
    buscarCliente(inputBuscaCliente.value);
  });

  // Foca no campo de busca
  inputBuscaCliente.focus();

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });

  function buscarCliente(termo) {
    if (!termo) return;

    fetch(`/api/clientes/busca?termo=${encodeURIComponent(termo)}`)
      .then((response) => response.json())
      .then((data) => {
        const tbody = modal.querySelector(".tabela-selecao-clientes tbody");
        tbody.innerHTML = "";

        if (data.length === 0) {
          tbody.innerHTML = `
            <tr>
              <td colspan="4" class="sem-resultados">Nenhum cliente encontrado</td>
            </tr>
          `;
          return;
        }

        data.forEach((cliente) => {
          const tr = document.createElement("tr");
          tr.innerHTML = `
            <td>${cliente.nome}</td>
            <td>${cliente.cpf_cnpj || "-"}</td>
            <td>${cliente.telefone || "-"}</td>
            <td>
              <button class="botao botao-primario botao-selecionar">Selecionar</button>
            </td>
          `;

          tr.querySelector(".botao-selecionar").addEventListener(
            "click",
            function () {
              selecionarCliente(cliente);
              document.body.removeChild(modal);
            }
          );

          tbody.appendChild(tr);
        });
      })
      .catch((error) => {
        console.error("Erro ao buscar cliente:", error);
        alert("Erro ao buscar cliente");
      });
  }
}

function selecionarCliente(cliente) {
  // Atualiza as informações do cliente na tela
  document.querySelector(
    ".pdv-venda-cliente-info .info-item:nth-child(1) .valor"
  ).textContent = cliente.nome;
  document.querySelector(
    ".pdv-venda-cliente-info .info-item:nth-child(2) .valor"
  ).textContent = cliente.cpf_cnpj || "-";

  // Armazena o ID do cliente para uso posterior
  document
    .querySelector(".pdv-venda-cliente")
    .setAttribute("data-cliente-id", cliente.id);
}

// Código para pagamento
document.querySelectorAll(".botao-pagamento").forEach((botao) => {
  botao.addEventListener("click", function () {
    const formaPagamento = this.getAttribute("data-forma");
    exibirModalPagamento(formaPagamento);
  });
});

function exibirModalPagamento(formaPagamento) {
  // Obtém o valor total da venda
  const valorTotal = parseFloat(
    document
      .querySelector(".resumo-item.total .valor")
      .textContent.replace("R$ ", "")
      .replace(",", ".")
  );

  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");

  let conteudoEspecifico = "";

  if (formaPagamento === "dinheiro") {
    conteudoEspecifico = `
      <div class="form-grupo">
        <label for="valor_recebido">Valor Recebido (R$)</label>
        <input type="text" id="valor_recebido" name="valor_recebido" placeholder="0,00" value="${valorTotal
          .toFixed(2)
          .replace(".", ",")}" required>
      </div>
      <div class="form-grupo">
        <label for="troco">Troco (R$)</label>
        <input type="text" id="troco" name="troco" placeholder="0,00" value="0,00" readonly>
      </div>
    `;
  } else if (formaPagamento === "cartao") {
    conteudoEspecifico = `
      <div class="form-grupo">
        <label for="tipo_cartao">Tipo de Cartão</label>
        <select id="tipo_cartao" name="tipo_cartao" required>
          <option value="">Selecione...</option>
          <option value="credito">Crédito</option>
          <option value="debito">Débito</option>
        </select>
      </div>
      <div class="form-grupo">
        <label for="parcelas">Parcelas</label>
        <select id="parcelas" name="parcelas" disabled>
          <option value="1">À vista</option>
          <option value="2">2x</option>
          <option value="3">3x</option>
          <option value="4">4x</option>
          <option value="5">5x</option>
          <option value="6">6x</option>
        </select>
      </div>
    `;
  } else if (formaPagamento === "pix") {
    conteudoEspecifico = `
      <div class="pix-qrcode">
        <img src="/api/pdv/pix/qrcode?valor=${valorTotal}" alt="QR Code PIX">
      </div>
      <div class="pix-instrucoes">
        <p>Escaneie o QR Code acima com o aplicativo do seu banco para realizar o pagamento via PIX.</p>
        <p>Após o pagamento, clique em "Confirmar Pagamento".</p>
      </div>
    `;
  } else {
    conteudoEspecifico = `
      <div class="form-grupo">
        <label for="forma_pagamento">Forma de Pagamento</label>
        <select id="forma_pagamento" name="forma_pagamento" required>
          <option value="">Selecione...</option>
          <option value="boleto">Boleto</option>
          <option value="transferencia">Transferência Bancária</option>
          <option value="cheque">Cheque</option>
          <option value="crediario">Crediário</option>
        </select>
      </div>
      <div class="form-grupo">
        <label for="observacoes_pagamento">Observações</label>
        <textarea id="observacoes_pagamento" name="observacoes_pagamento" rows="3"></textarea>
      </div>
    `;
  }

  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Pagamento - ${obterNomeFormaPagamento(
          formaPagamento
        )}</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <form id="form-pagamento">
          <div class="form-grupo">
            <label for="valor_total">Valor Total (R$)</label>
            <input type="text" id="valor_total" name="valor_total" value="${valorTotal
              .toFixed(2)
              .replace(".", ",")}" readonly>
          </div>
          ${conteudoEspecifico}
        </form>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar-pagamento">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar-pagamento">Confirmar Pagamento</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos específicos para cada forma de pagamento
  if (formaPagamento === "dinheiro") {
    const inputValorRecebido = modal.querySelector("#valor_recebido");
    const inputTroco = modal.querySelector("#troco");

    // Formata o campo de valor recebido
    inputValorRecebido.addEventListener("input", function () {
      let valor = this.value.replace(/\D/g, "");
      valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
      this.value = valor;

      // Calcula o troco
      const valorRecebido = parseFloat(this.value.replace(",", "."));
      const troco = valorRecebido - valorTotal;
      inputTroco.value =
        troco > 0 ? troco.toFixed(2).replace(".", ",") : "0,00";
    });

    // Foca no campo de valor recebido
    inputValorRecebido.focus();
    inputValorRecebido.select();
  } else if (formaPagamento === "cartao") {
    const selectTipoCartao = modal.querySelector("#tipo_cartao");
    const selectParcelas = modal.querySelector("#parcelas");

    selectTipoCartao.addEventListener("change", function () {
      if (this.value === "credito") {
        selectParcelas.disabled = false;
      } else {
        selectParcelas.value = "1";
        selectParcelas.disabled = true;
      }
    });
  }

  // Adiciona eventos comuns
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-pagamento")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  modal
    .querySelector("#btn-confirmar-pagamento")
    .addEventListener("click", function () {
      const form = modal.querySelector("#form-pagamento");

      if (form.checkValidity()) {
        // Coleta os dados do pagamento
        const dadosPagamento = {
          forma: formaPagamento,
          valor: valorTotal,
        };

        // Adiciona dados específicos de cada forma de pagamento
        if (formaPagamento === "dinheiro") {
          dadosPagamento.valor_recebido = parseFloat(
            form.valor_recebido.value.replace(",", ".")
          );
          dadosPagamento.troco = parseFloat(form.troco.value.replace(",", "."));
        } else if (formaPagamento === "cartao") {
          dadosPagamento.tipo_cartao = form.tipo_cartao.value;
          dadosPagamento.parcelas = parseInt(form.parcelas.value);
        } else if (formaPagamento === "outros") {
          dadosPagamento.forma_especifica = form.forma_pagamento.value;
          dadosPagamento.observacoes = form.observacoes_pagamento.value;
        }

        // Finaliza a venda
        finalizarVenda(dadosPagamento);

        // Fecha o modal
        document.body.removeChild(modal);
      } else {
        // Exibe mensagem de validação
        form.reportValidity();
      }
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}

function obterNomeFormaPagamento(forma) {
  switch (forma) {
    case "dinheiro":
      return "Dinheiro";
    case "cartao":
      return "Cartão";
    case "pix":
      return "PIX";
    case "outros":
      return "Outros";
    default:
      return forma;
  }
}

// Código para finalização da venda
document
  .querySelector("#btn-finalizar-venda")
  .addEventListener("click", function () {
    // Verifica se há produtos na venda
    const tbody = document.querySelector(".tabela-produtos tbody");
    if (tbody.querySelectorAll("tr").length === 0) {
      alert("Adicione pelo menos um produto para finalizar a venda");
      return;
    }

    // Exibe o modal de pagamento padrão (dinheiro)
    exibirModalPagamento("dinheiro");
  });

function finalizarVenda(dadosPagamento) {
  // Coleta os dados da venda
  const clienteId =
    document
      .querySelector(".pdv-venda-cliente")
      .getAttribute("data-cliente-id") || null;

  const produtos = [];
  document.querySelectorAll(".tabela-produtos tbody tr").forEach((linha) => {
    const produtoId = linha.getAttribute("data-produto-id");
    const quantidade = parseInt(linha.querySelector(".input-quantidade").value);
    const valorUnitario = parseFloat(
      linha.querySelector(".coluna-unitario").getAttribute("data-valor")
    );

    produtos.push({
      produto_id: produtoId,
      quantidade: quantidade,
      valor_unitario: valorUnitario,
    });
  });

  const venda = {
    cliente_id: clienteId,
    produtos: produtos,
    pagamento: dadosPagamento,
  };

  // Envia para a API
  fetch("/api/pdv/venda", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(venda),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao finalizar venda");
    })
    .then((data) => {
      // Exibe modal de sucesso
      exibirModalSucesso(data);
    })
    .catch((error) => {
      console.error("Erro ao finalizar venda:", error);
      alert(`Erro ao finalizar venda: ${error.message}`);
    });
}

function exibirModalSucesso(dadosVenda) {
  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Venda Finalizada com Sucesso</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="venda-sucesso">
          <div class="venda-sucesso-icone">
            <span class="icone icone-sucesso"></span>
          </div>
          <div class="venda-sucesso-info">
            <p>Venda #${dadosVenda.id} finalizada com sucesso!</p>
            <p>Valor total: ${formatarMoeda(dadosVenda.valor_total)}</p>
            <p>Forma de pagamento: ${obterNomeFormaPagamento(
              dadosVenda.pagamento.forma
            )}</p>
          </div>
        </div>
        <div class="venda-sucesso-acoes">
          <button class="botao botao-secundario" id="btn-imprimir-comprovante">
            <span class="icone icone-imprimir"></span>
            <span class="texto">Imprimir Comprovante</span>
          </button>
          <button class="botao botao-secundario" id="btn-enviar-email">
            <span class="icone icone-email"></span>
            <span class="texto">Enviar por E-mail</span>
          </button>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-primario" id="btn-nova-venda">Nova Venda</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
    limparVenda();
  });

  modal
    .querySelector("#btn-imprimir-comprovante")
    .addEventListener("click", function () {
      window.open(`/pdv/comprovante/${dadosVenda.id}`, "_blank");
    });

  modal
    .querySelector("#btn-enviar-email")
    .addEventListener("click", function () {
      // Verifica se há cliente selecionado
      if (!dadosVenda.cliente_id) {
        alert(
          "Não é possível enviar o comprovante por e-mail para Consumidor Final"
        );
        return;
      }

      fetch(`/api/pdv/comprovante/${dadosVenda.id}/email`, {
        method: "POST",
      })
        .then((response) => {
          if (response.ok) {
            alert("Comprovante enviado por e-mail com sucesso!");
          } else {
            throw new Error("Erro ao enviar comprovante por e-mail");
          }
        })
        .catch((error) => {
          console.error("Erro ao enviar comprovante por e-mail:", error);
          alert(`Erro ao enviar comprovante por e-mail: ${error.message}`);
        });
    });

  modal.querySelector("#btn-nova-venda").addEventListener("click", function () {
    document.body.removeChild(modal);
    limparVenda();
  });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
      limparVenda();
    }
  });
}

function limparVenda() {
  // Limpa a tabela de produtos
  document.querySelector(".tabela-produtos tbody").innerHTML = "";

  // Reseta o cliente para Consumidor Final
  document.querySelector(
    ".pdv-venda-cliente-info .info-item:nth-child(1) .valor"
  ).textContent = "Consumidor Final";
  document.querySelector(
    ".pdv-venda-cliente-info .info-item:nth-child(2) .valor"
  ).textContent = "-";
  document
    .querySelector(".pdv-venda-cliente")
    .removeAttribute("data-cliente-id");

  // Atualiza o resumo
  atualizarResumo();

  // Desabilita o botão de finalizar venda
  document.querySelector("#btn-finalizar-venda").disabled = true;

  // Foca no campo de busca de produtos
  document.querySelector("#input-busca-produto").focus();
}

// Código para cancelamento da venda
document
  .querySelector("#btn-cancelar-venda")
  .addEventListener("click", function () {
    // Verifica se há produtos na venda
    const tbody = document.querySelector(".tabela-produtos tbody");
    if (tbody.querySelectorAll("tr").length === 0) {
      return;
    }

    // Confirma o cancelamento
    if (confirm("Tem certeza que deseja cancelar esta venda?")) {
      limparVenda();
    }
  });

// Código para fechamento do caixa
document
  .querySelector("#btn-fechar-caixa")
  .addEventListener("click", function () {
    // Verifica se há uma venda em andamento
    const tbody = document.querySelector(".tabela-produtos tbody");
    if (tbody.querySelectorAll("tr").length > 0) {
      alert("Finalize ou cancele a venda atual antes de fechar o caixa");
      return;
    }

    // Confirma o fechamento
    if (confirm("Tem certeza que deseja fechar o caixa?")) {
      exibirModalFechamentoCaixa();
    }
  });

function exibirModalFechamentoCaixa() {
  // Obtém os dados do caixa
  fetch("/api/pdv/caixa")
    .then((response) => response.json())
    .then((data) => {
      // Cria o modal
      const modal = document.createElement("div");
      modal.classList.add("modal");
      modal.innerHTML = `
        <div class="modal-conteudo modal-grande">
          <div class="modal-cabecalho">
            <h2 class="modal-titulo">Fechamento de Caixa</h2>
            <button class="botao-fechar">&times;</button>
          </div>
          <div class="modal-corpo">
            <div class="resumo-caixa">
              <div class="resumo-caixa-item">
                <span class="label">Valor Inicial:</span>
                <span class="valor">${formatarMoeda(data.valor_inicial)}</span>
              </div>
              <div class="resumo-caixa-item">
                <span class="label">Total de Vendas:</span>
                <span class="valor">${formatarMoeda(data.total_vendas)}</span>
              </div>
              <div class="resumo-caixa-item">
                <span class="label">Dinheiro:</span>
                <span class="valor">${formatarMoeda(data.total_dinheiro)}</span>
              </div>
              <div class="resumo-caixa-item">
                <span class="label">Cartão:</span>
                <span class="valor">${formatarMoeda(data.total_cartao)}</span>
              </div>
              <div class="resumo-caixa-item">
                <span class="label">PIX:</span>
                <span class="valor">${formatarMoeda(data.total_pix)}</span>
              </div>
              <div class="resumo-caixa-item">
                <span class="label">Outros:</span>
                <span class="valor">${formatarMoeda(data.total_outros)}</span>
              </div>
              <div class="resumo-caixa-item total">
                <span class="label">Saldo Final:</span>
                <span class="valor">${formatarMoeda(data.saldo_final)}</span>
              </div>
            </div>
            
            <form id="form-fechamento-caixa">
              <div class="form-grupo">
                <label for="valor_informado">Valor em Caixa (R$)</label>
                <input type="text" id="valor_informado" name="valor_informado" placeholder="0,00" required>
              </div>
              <div class="form-grupo">
                <label for="diferenca">Diferença (R$)</label>
                <input type="text" id="diferenca" name="diferenca" placeholder="0,00" readonly>
              </div>
              <div class="form-grupo">
                <label for="observacoes_fechamento">Observações</label>
                <textarea id="observacoes_fechamento" name="observacoes_fechamento" rows="3"></textarea>
              </div>
            </form>
          </div>
          <div class="modal-rodape">
            <button class="botao botao-secundario" id="btn-cancelar-fechamento">Cancelar</button>
            <button class="botao botao-primario" id="btn-confirmar-fechamento">Confirmar Fechamento</button>
          </div>
        </div>
      `;

      document.body.appendChild(modal);

      // Adiciona eventos
      const inputValorInformado = modal.querySelector("#valor_informado");
      const inputDiferenca = modal.querySelector("#diferenca");
      const saldoFinal = data.saldo_final;

      // Formata o campo de valor informado
      inputValorInformado.addEventListener("input", function () {
        let valor = this.value.replace(/\D/g, "");
        valor = (parseFloat(valor) / 100).toFixed(2).replace(".", ",");
        this.value = valor;

        // Calcula a diferença
        const valorInformado = parseFloat(this.value.replace(",", "."));
        const diferenca = valorInformado - saldoFinal;
        inputDiferenca.value = diferenca.toFixed(2).replace(".", ",");

        // Adiciona classe para destacar diferença
        if (diferenca > 0) {
          inputDiferenca.classList.remove("diferenca-negativa");
          inputDiferenca.classList.add("diferenca-positiva");
        } else if (diferenca < 0) {
          inputDiferenca.classList.remove("diferenca-positiva");
          inputDiferenca.classList.add("diferenca-negativa");
        } else {
          inputDiferenca.classList.remove(
            "diferenca-positiva",
            "diferenca-negativa"
          );
        }
      });

      // Foca no campo de valor informado
      inputValorInformado.focus();

      modal
        .querySelector(".botao-fechar")
        .addEventListener("click", function () {
          document.body.removeChild(modal);
        });

      modal
        .querySelector("#btn-cancelar-fechamento")
        .addEventListener("click", function () {
          document.body.removeChild(modal);
        });

      modal
        .querySelector("#btn-confirmar-fechamento")
        .addEventListener("click", function () {
          const form = modal.querySelector("#form-fechamento-caixa");

          if (form.checkValidity()) {
            // Coleta os dados do fechamento
            const valorInformado = parseFloat(
              form.valor_informado.value.replace(",", ".")
            );
            const diferenca = parseFloat(
              form.diferenca.value.replace(",", ".")
            );
            const observacoes = form.observacoes_fechamento.value;

            // Envia para a API
            fetch("/api/pdv/caixa/fechar", {
              method: "POST",
              headers: {
                "Content-Type": "application/json",
              },
              body: JSON.stringify({
                valor_informado: valorInformado,
                diferenca: diferenca,
                observacoes: observacoes,
              }),
            })
              .then((response) => {
                if (response.ok) {
                  // Redireciona para a tela inicial do PDV
                  window.location.href = "/pdv";
                } else {
                  throw new Error("Erro ao fechar caixa");
                }
              })
              .catch((error) => {
                console.error("Erro ao fechar caixa:", error);
                alert(`Erro ao fechar caixa: ${error.message}`);
              });
          } else {
            // Exibe mensagem de validação
            form.reportValidity();
          }
        });

      // Fecha o modal ao clicar fora
      modal.addEventListener("click", function (e) {
        if (e.target === modal) {
          document.body.removeChild(modal);
        }
      });
    })
    .catch((error) => {
      console.error("Erro ao obter dados do caixa:", error);
      alert(`Erro ao obter dados do caixa: ${error.message}`);
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .pdv-venda-conteudo {
    flex-direction: column;
  }

  .pdv-venda-esquerda,
  .pdv-venda-direita {
    flex: none;
    width: 100%;
  }

  .pdv-venda-direita {
    border-left: none;
    border-top: 1px solid #e0e0e0;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .pdv-venda-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .pdv-venda-info {
    margin-bottom: 12px;
  }

  .pdv-venda-pagamento-opcoes {
    grid-template-columns: 1fr;
  }

  .coluna-codigo,
  .coluna-unitario {
    display: none;
  }

  .pdv-relogio {
    font-size: 48px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .pdv-venda-info {
    flex-direction: column;
    gap: 8px;
  }

  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .pdv-relogio {
    font-size: 36px;
  }

  .botao-grande {
    padding: 12px 24px;
    font-size: 16px;
    min-width: 160px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Verde (sucesso): #52c41a
- Verde claro (background sucesso): #f6ffed
- Verde muito claro (borda sucesso): #b7eb8f
- Vermelho (erro): #f5222d
- Vermelho claro (background erro): #fff1f0
- Vermelho muito claro (borda erro): #ffa39e
- Amarelo (alerta): #faad14
- Amarelo claro (background alerta): #fffbe6
- Amarelo muito claro (borda alerta): #ffe58f
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Relógio: 64px (desktop), 48px (tablet), 36px (mobile)
  - Títulos principais: 24px
  - Subtítulos: 18px
  - Botões grandes: 18px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Light: 300 (relógio)
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

.botao-grande {
  padding: 16px 32px;
  font-size: 18px;
  min-width: 200px;
}

.botao[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
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

.modal-grande {
  max-width: 700px;
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

### Formulários

```css
.form-grupo {
  margin-bottom: 16px;
}

.form-grupo:last-child {
  margin-bottom: 0;
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

.diferenca-positiva {
  color: #52c41a;
}

.diferenca-negativa {
  color: #f5222d;
}
```

## Fluxos de Navegação

1. **Abertura de Caixa**:

   - O usuário acessa a tela inicial do PDV
   - Clica no botão "Abrir caixa" ou usa o atalho Ctrl+Enter
   - Preenche o valor inicial e observações no modal
   - Confirma a abertura do caixa
   - É redirecionado para a tela de PDV com caixa aberto

2. **Realização de Venda**:

   - O usuário busca produtos pelo código, nome ou código de barras
   - Seleciona o cliente (opcional)
   - Ajusta as quantidades dos produtos
   - Clica em "Finalizar Venda"
   - Seleciona a forma de pagamento
   - Preenche os dados do pagamento
   - Confirma o pagamento
   - Visualiza o comprovante e pode imprimir ou enviar por e-mail
   - Inicia uma nova venda

3. **Fechamento de Caixa**:
   - O usuário clica no botão "Fechar Caixa"
   - Visualiza o resumo das operações do caixa
   - Informa o valor em caixa
   - Preenche observações (opcional)
   - Confirma o fechamento
   - É redirecionado para a tela inicial do PDV

## Conclusão

O módulo "PDV" do ERP Revo apresenta uma interface funcional e intuitiva para operações de ponto de venda. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo abertura e fechamento de caixa, busca de produtos, seleção de clientes, realização de vendas e processamento de pagamentos de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para operações de ponto de venda, como controle de caixa, cadastro de vendas, processamento de pagamentos e emissão de comprovantes, atendendo às necessidades de negócios que realizam vendas presenciais.
