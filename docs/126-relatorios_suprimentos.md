# Análise do Módulo Relatórios de Suprimentos - ERP Revo

## Estrutura Geral

O módulo "Relatórios de Suprimentos" do ERP Revo apresenta uma interface organizada para acesso aos diversos relatórios relacionados ao controle de estoque, notas de entrada e ordens de compra. A tela é composta por um cabeçalho com título e botões de ação, seguida por uma navegação por categorias e uma lista de relatórios disponíveis com suas respectivas descrições.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação:

- Título "Relatórios de Suprimentos"
- Botão para acessar outros relatórios

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Relatórios de Suprimentos</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-outros-relatorios">
      <span class="icone icone-relatorio"></span>
      <span class="texto">outros relatórios</span>
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

.botao-secundario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-secundario:hover {
  background-color: #40a9ff;
}

.botao .icone {
  margin-right: 8px;
}
```

### Navegação por Categorias

A navegação por categorias permite filtrar os relatórios por área:

- Controle de Estoques
- Notas de Entrada
- Ordens de Compra

**Estrutura HTML:**

```html
<div class="categorias-navegacao">
  <a href="#" class="categoria-item ativo" data-categoria="controle-estoques">
    <span class="texto">controle de estoques</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="notas-entrada">
    <span class="texto">notas de entrada</span>
  </a>
  <a href="#" class="categoria-item" data-categoria="ordens-compra">
    <span class="texto">ordens de compra</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.categorias-navegacao {
  display: flex;
  gap: 8px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.categoria-item {
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

.categoria-item.ativo {
  background-color: #f6ffed;
  border-color: #b7eb8f;
  color: #52c41a;
}

.categoria-item:hover:not(.ativo) {
  background-color: #f5f5f5;
}
```

### Lista de Relatórios

A lista de relatórios exibe os relatórios disponíveis com título e descrição:

**Estrutura HTML:**

```html
<div class="relatorios-container">
  <div class="relatorio-item">
    <a href="#/relatorio/entradas-saidas" class="relatorio-link">
      <h2 class="relatorio-titulo">Entradas e Saídas de Estoque</h2>
      <p class="relatorio-descricao">
        Este relatório mostra todas as entradas e saídas realizadas em um
        período. Demonstra o fluxo de movimentação do estoque e os saldos no
        período.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/saldos-estoque" class="relatorio-link">
      <h2 class="relatorio-titulo">Saldos em Estoque</h2>
      <p class="relatorio-descricao">
        Apresenta os saldos em estoque dos itens em uma data qualquer.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/produtos-maior-circulacao" class="relatorio-link">
      <h2 class="relatorio-titulo">Produtos com Maior Circulação</h2>
      <p class="relatorio-descricao">
        Relação dos itens que mais movimentaram em certo período e a sua
        participação percentual com totais por quantidade e valor.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/produtos-sem-movimentacao" class="relatorio-link">
      <h2 class="relatorio-titulo">Produtos sem Movimentação</h2>
      <p class="relatorio-descricao">
        Relaciona os produtos que não tiveram nenhuma movimentação de saída de
        estoque no período.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/produtos-abaixo-minimo" class="relatorio-link">
      <h2 class="relatorio-titulo">Produtos Abaixo do Estoque Mínimo</h2>
      <p class="relatorio-descricao">
        Relação dos produtos que estão abaixo do estoque mínimo.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/visao-financeira-estoque" class="relatorio-link">
      <h2 class="relatorio-titulo">Visão Financeira do Estoque</h2>
      <p class="relatorio-descricao">
        Valor total dos produtos em estoque pelo preço de última compra e preço
        de venda.
      </p>
    </a>
  </div>

  <div class="relatorio-item">
    <a href="#/relatorio/movimentacao-produto" class="relatorio-link">
      <h2 class="relatorio-titulo">Movimentação de um Produto</h2>
      <p class="relatorio-descricao">
        Relatório e gráfico de movimentação de estoque de um produto em
        determinado período.
      </p>
    </a>
  </div>

  <div class="relatorio-item relatorio-item-bloqueado">
    <div class="relatorio-link">
      <h2 class="relatorio-titulo">
        Relatório de lotes e validades de produtos
      </h2>
      <div class="relatorio-bloqueado-info">
        <span class="icone icone-bloqueado"></span>
        <span class="texto">Disponível apenas em planos superiores</span>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.relatorios-container {
  padding: 16px 24px;
  background-color: #ffffff;
}

.relatorio-item {
  margin-bottom: 16px;
  border-radius: 4px;
  overflow: hidden;
}

.relatorio-link {
  display: block;
  padding: 16px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  text-decoration: none;
  transition: background-color 0.2s ease, border-color 0.2s ease;
}

.relatorio-link:hover {
  background-color: #f5f5f5;
  border-color: #d9d9d9;
}

.relatorio-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.relatorio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
  line-height: 1.5;
}

.relatorio-item-bloqueado .relatorio-link {
  background-color: #f5f5f5;
  cursor: default;
}

.relatorio-bloqueado-info {
  display: flex;
  align-items: center;
  margin-top: 8px;
  color: #999999;
  font-size: 12px;
}

.relatorio-bloqueado-info .icone {
  margin-right: 4px;
}
```

## Interações JavaScript

### Navegação por Categorias

A navegação por categorias permite filtrar os relatórios exibidos:

```javascript
// Código para navegação por categorias
document.querySelectorAll(".categoria-item").forEach((categoria) => {
  categoria.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todas as categorias
    document.querySelectorAll(".categoria-item").forEach((cat) => {
      cat.classList.remove("ativo");
    });

    // Adiciona classe ativo à categoria clicada
    this.classList.add("ativo");

    // Filtra os relatórios pela categoria
    const categoriaId = this.getAttribute("data-categoria");
    filtrarRelatoriosPorCategoria(categoriaId);
  });
});

function filtrarRelatoriosPorCategoria(categoria) {
  // Oculta todos os relatórios
  document.querySelectorAll(".relatorio-item").forEach((item) => {
    item.style.display = "none";
  });

  // Exibe apenas os relatórios da categoria selecionada
  if (categoria === "controle-estoques") {
    document
      .querySelectorAll('.relatorio-item[data-categoria="controle-estoques"]')
      .forEach((item) => {
        item.style.display = "block";
      });
  } else if (categoria === "notas-entrada") {
    document
      .querySelectorAll('.relatorio-item[data-categoria="notas-entrada"]')
      .forEach((item) => {
        item.style.display = "block";
      });
  } else if (categoria === "ordens-compra") {
    document
      .querySelectorAll('.relatorio-item[data-categoria="ordens-compra"]')
      .forEach((item) => {
        item.style.display = "block";
      });
  }
}
```

### Acesso a Outros Relatórios

O botão "outros relatórios" permite acessar relatórios de outros módulos:

```javascript
// Código para acesso a outros relatórios
document
  .querySelector("#btn-outros-relatorios")
  .addEventListener("click", function () {
    // Abre modal de seleção de módulo
    const modal = document.createElement("div");
    modal.classList.add("modal");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecione o Módulo</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="lista-modulos">
          <a href="/relatorios_Revo?id=1&nome=Cadastros" class="modulo-item">
            <span class="icone icone-cadastros"></span>
            <span class="texto">Cadastros</span>
          </a>
          <a href="/relatorios_Revo?id=2&nome=Suprimentos" class="modulo-item ativo">
            <span class="icone icone-suprimentos"></span>
            <span class="texto">Suprimentos</span>
          </a>
          <a href="/relatorios_Revo?id=3&nome=Vendas" class="modulo-item">
            <span class="icone icone-vendas"></span>
            <span class="texto">Vendas</span>
          </a>
          <a href="/relatorios_Revo?id=4&nome=Financas" class="modulo-item">
            <span class="icone icone-financas"></span>
            <span class="texto">Finanças</span>
          </a>
          <a href="/relatorios_Revo?id=5&nome=Servicos" class="modulo-item">
            <span class="icone icone-servicos"></span>
            <span class="texto">Serviços</span>
          </a>
        </div>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos aos botões do modal
    modal.querySelector(".botao-fechar").addEventListener("click", () => {
      document.body.removeChild(modal);
    });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });
```

### Acesso aos Relatórios

Ao clicar em um relatório, o usuário é direcionado para a tela de configuração do relatório:

```javascript
// Código para acesso aos relatórios
document.querySelectorAll(".relatorio-link").forEach((link) => {
  link.addEventListener("click", function (e) {
    // Não executa para relatórios bloqueados
    if (this.closest(".relatorio-item-bloqueado")) {
      e.preventDefault();
      exibirModalPlanoSuperior();
      return;
    }

    // Para relatórios normais, segue o fluxo padrão
    // O link já possui o href para a página do relatório
  });
});

function exibirModalPlanoSuperior() {
  // Abre modal informando sobre planos superiores
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Recurso Disponível em Planos Superiores</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="modal-mensagem">
          <p>Este relatório está disponível apenas em planos superiores.</p>
          <p>Faça um upgrade do seu plano para acessar este e outros recursos exclusivos.</p>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-fechar-modal">Fechar</button>
        <a href="/planos" class="botao botao-primario">Ver Planos</a>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-fechar-modal").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}
```

## Tela de Configuração de Relatório

Quando o usuário clica em um relatório, é direcionado para uma tela de configuração:

**Estrutura HTML:**

```html
<div class="configuracao-relatorio">
  <div class="configuracao-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-relatorio">Entradas e Saídas de Estoque</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-voltar">
        <span class="icone icone-voltar"></span>
        <span class="texto">Voltar</span>
      </button>
    </div>
  </div>

  <div class="configuracao-corpo">
    <form id="form-configuracao">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Filtros</h2>

        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="periodo">Período</label>
            <select id="periodo" name="periodo">
              <option value="hoje">Hoje</option>
              <option value="ontem">Ontem</option>
              <option value="7dias">Últimos 7 dias</option>
              <option value="30dias" selected>Últimos 30 dias</option>
              <option value="mes_atual">Mês atual</option>
              <option value="mes_anterior">Mês anterior</option>
              <option value="personalizado">Personalizado</option>
            </select>
          </div>
        </div>

        <div class="form-linha periodo-personalizado" style="display: none;">
          <div class="form-grupo form-grupo-pequeno">
            <label for="data_inicial">Data Inicial</label>
            <input type="date" id="data_inicial" name="data_inicial">
          </div>
          <div class="form-grupo form-grupo-pequeno">
            <label for="data_final">Data Final</label>
            <input type="date" id="data_final" name="data_final">
          </div>
        </div>

        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="produto">Produto</label>
            <select id="produto" name="produto">
              <option value="">Todos os produtos</option>
              <!-- Opções de produtos serão carregadas dinamicamente -->
            </select>
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="categoria">Categoria</label>
            <select id="categoria" name="categoria">
              <option value="">Todas as categorias</option>
              <!-- Opções de categorias serão carregadas dinamicamente -->
            </select>
          </div>
        </div>

        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="tipo_movimento">Tipo de Movimento</label>
            <select id="tipo_movimento" name="tipo_movimento">
              <option value="todos">Todos</option>
              <option value="entrada">Apenas Entradas</option>
              <option value="saida">Apenas Saídas</option>
            </select>
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="local_estoque">Local de Estoque</label>
            <select id="local_estoque" name="local_estoque">
              <option value="">Todos os locais</option>
              <!-- Opções de locais serão carregadas dinamicamente -->
            </select>
          </div>
        </div>
      </div>

      <div class="fo
(Content truncated due to size limit. Use line ranges to read in chunks)
```
