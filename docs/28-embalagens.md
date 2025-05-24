# Análise do Módulo Embalagens - ERP Revo

## Estrutura Geral

O módulo "Embalagens" do ERP Revo apresenta uma interface organizada para gerenciamento de embalagens utilizadas para envio de produtos, com uma estrutura que facilita a visualização, cadastro e manipulação dos itens. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma tabela de dados com informações das embalagens cadastradas.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Embalagens de produtos"
- Botão para criar embalagens dos Correios
- Botão de inclusão de nova embalagem

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Embalagens de produtos</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-criar-correios">
      <span class="icone icone-correios"></span>
      <span class="texto">Criar embalagens Correios</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir embalagem</span>
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
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar as embalagens:

- Campo de texto para pesquisa
- Botão de busca
- Filtro por embalagem

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input type="text" placeholder="Pesquisa..." class="input-pesquisa" />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="embalagem">
      <span class="icone icone-filtro"></span>
      <span class="texto">por embalagem</span>
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

### Tabela de Embalagens

A tabela exibe as embalagens cadastradas com suas informações principais:

- Checkbox para seleção
- Código/ID da embalagem
- Descrição
- Tipo
- Dimensões
- Peso

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-embalagens">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-id">ID</th>
        <th class="coluna-descricao">Descrição</th>
        <th class="coluna-tipo">Tipo</th>
        <th class="coluna-dimensoes">Dimensões</th>
        <th class="coluna-peso">Peso</th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-embalagem">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-id">
          <div class="embalagem-tag">19</div>
        </td>
        <td class="coluna-descricao">Caixa de Encomenda Flex</td>
        <td class="coluna-tipo">Pacote / Caixa</td>
        <td class="coluna-dimensoes">26,00cm x 21,00cm x 1,00cm</td>
        <td class="coluna-peso">0,09 Kg</td>
      </tr>
      <tr class="linha-embalagem">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-id">
          <div class="embalagem-tag">20</div>
        </td>
        <td class="coluna-descricao">Caixa de Encomenda Flex</td>
        <td class="coluna-tipo">Pacote / Caixa</td>
        <td class="coluna-dimensoes">26,00cm x 21,00cm x 2,00cm</td>
        <td class="coluna-peso">0,18 Kg</td>
      </tr>
      <!-- Outras linhas de embalagens -->
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

.tabela-embalagens {
  width: 100%;
  border-collapse: collapse;
}

.tabela-embalagens th,
.tabela-embalagens td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-embalagens th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-id {
  width: 60px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-tipo {
  width: 150px;
}

.coluna-dimensoes {
  width: 200px;
}

.coluna-peso {
  width: 100px;
}

.embalagem-tag {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #722ed1;
  color: white;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}
```

### Paginação

A paginação permite navegar entre as páginas de resultados:

**Estrutura HTML:**

```html
<div class="paginacao">
  <div class="paginacao-info">
    <span class="paginacao-total">74 embalagens</span>
  </div>
  <div class="paginacao-controles">
    <a href="#" class="paginacao-pagina ativo">01</a>
    <a href="#" class="paginacao-pagina">02</a>
    <a href="#" class="paginacao-proxima">
      <span class="icone icone-seta-direita"></span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #e0e0e0;
}

.paginacao-total {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  gap: 4px;
}

.paginacao-pagina {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.paginacao-pagina.ativo {
  background-color: #1890ff;
  color: white;
}

.paginacao-pagina:hover:not(.ativo) {
  background-color: #f5f5f5;
}

.paginacao-proxima {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.paginacao-proxima:hover {
  background-color: #f5f5f5;
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

O módulo permite pesquisar e filtrar embalagens:

```javascript
// Código para pesquisa de embalagens
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
  // Lógica para filtrar embalagens pelo termo de pesquisa
  fetch(`/api/embalagens/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaEmbalagens(data);
    });
}

// Código para filtro por embalagem
document
  .querySelector('.filtro-item[data-filtro="embalagem"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre dropdown de tipos de embalagem
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-tipo="todos">Todos os tipos</a>
    <a href="#" class="dropdown-item" data-tipo="caixa">Caixas</a>
    <a href="#" class="dropdown-item" data-tipo="envelope">Envelopes</a>
    <a href="#" class="dropdown-item" data-tipo="pacote">Pacotes</a>
  `;

    // Posiciona o dropdown
    const rect = this.getBoundingClientRect();
    dropdown.style.top = `${rect.bottom}px`;
    dropdown.style.left = `${rect.left}px`;

    // Adiciona ao DOM
    document.body.appendChild(dropdown);

    // Adiciona eventos aos itens do dropdown
    dropdown.querySelectorAll(".dropdown-item").forEach((item) => {
      item.addEventListener("click", function (e) {
        e.preventDefault();

        const tipo = this.getAttribute("data-tipo");
        filtrarPorTipo(tipo);

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !==
          document.querySelector('.filtro-item[data-filtro="embalagem"]')
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function filtrarPorTipo(tipo) {
  // Lógica para filtrar embalagens por tipo
  let url = "/api/embalagens";

  if (tipo !== "todos") {
    url += `?tipo=${tipo}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaEmbalagens(data);
    });
}
```

### Seleção de Embalagens

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de embalagens
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

### Inclusão de Nova Embalagem

O botão de inclusão redireciona para o formulário de cadastro:

```javascript
// Código para inclusão de nova embalagem
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/embalagens/novo";
});
```

### Criação de Embalagens dos Correios

O botão para criar embalagens dos Correios abre um modal com opções:

```javascript
// Código para criar embalagens dos Correios
document.querySelector('#btn-criar-correios').addEventListener('click', function() {
  // Abre modal de opções
  const modal = document.createElement('div');
  modal.classList.add('modal');
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Criar Embalagens dos Correios</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <p class="modal-descricao">
          Selecione os tipos de embalagens dos Correios que deseja criar automaticamente:
        </p>
        <div class="opcoes-checkbox">
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_caixa" name="tipos[]" value="caixa" checked>
            <label for="tipo_caixa">Caixas</label>
          </div>
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_envelope" name="tipos[]" value="envelope" checked>
            <label for="tipo_envelope">Envelopes</label>
          </div>
          <div class="opcao-checkbox">
            <input type="checkbox" id="tipo_pacote" name="tipos[]" value="pacote" checked>
            <label for="tipo_pacote">Pacotes</label>
          </div>
        </div>
        <p class="modal-aviso">
          As embalagens criadas terão as dimensões oficiais dos Correios.
        </p>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
        <button class="botao botao-primario" id="btn-confirmar">Criar Embalagens</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector('.botao-fechar').addEventListener('click', () => {
    document.body.removeChild(modal);
  });

  modal.querySelector('#btn-cancelar').addEventListener('click', () => {
    document.body.removeChild(modal);
  });

  modal.querySelector('#btn-confirmar').addEventListener('click', () => {
    // Coleta os tipos selecionados
    const tiposSelecionados = Array.from(
      modal.querySelectorAll('input[name="tipos[]"]:checked')
    ).map(input => input.value);

    // Cria as embalagens
    criarEmbalagensCorreios(tiposSelecionados);

    // Fecha o modal
    document.body.removeChild(modal);
  });
});

function criarEmbalagensCorreios(tipos) {
  // Envia a solicitação para criar as embalagens
  fetch('/api/embalagens/criar-correios', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({ tipos })
  })
  .then(response => response.json())
  .then(data => {
    // Exibe mensagem de sucesso
    alert(`${data.quantidade} embalagens dos Correios foram criadas com sucesso!`);

    // Atualiza a lista de embalagens
    window.location.reload();
  })
  .catch(error => {
    // Exibe mensagem de erro
    alert('Erro ao criar embalagens dos Correios
(Content truncated due to size limit. Use line ranges to read in chunks)
```
