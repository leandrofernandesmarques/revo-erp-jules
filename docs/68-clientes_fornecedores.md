# Análise do Módulo Clientes e Fornecedores - ERP Revo

## Estrutura Geral

O módulo "Clientes e Fornecedores" do ERP Revo apresenta uma interface organizada para gerenciamento de contatos, com uma estrutura que prioriza a visualização e manipulação de dados de forma eficiente. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma tabela de dados com informações dos contatos cadastrados.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Clientes e Fornecedores"
- Botão de impressão
- Botão de inclusão de novo cadastro
- Menu de ações adicionais

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Clientes e Fornecedores</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">imprimir</span>
    </button>
    <button class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">incluir cadastro</span>
    </button>
    <button class="botao botao-secundario dropdown-toggle" id="btn-mais-acoes">
      <span class="texto">mais ações</span>
      <span class="icone icone-seta-baixo"></span>
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

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao .icone {
  margin-right: 8px;
}

.dropdown-toggle {
  position: relative;
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar os contatos por diferentes critérios:

- Campo de texto para pesquisa por nome, código, fantasia, email ou CPF/CNPJ
- Botão de busca
- Opções de visualização (lista/grade)

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por nome, cód., fantasia, email ou CPF/CNPJ..."
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
    </button>
  </div>
  <div class="opcoes-visualizacao">
    <button class="botao-visualizacao ativo" data-view="lista">
      <span class="icone icone-lista"></span>
    </button>
    <button class="botao-visualizacao" data-view="grade">
      <span class="icone icone-grade"></span>
    </button>
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
  gap: 4px;
}

.botao-visualizacao {
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: white;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  cursor: pointer;
}

.botao-visualizacao.ativo {
  background-color: #1890ff;
  color: white;
  border-color: #1890ff;
}
```

### Filtros de Dados

Os filtros permitem refinar a visualização dos contatos por diferentes critérios:

- Filtro por data de cadastro
- Filtro por nome (ordem alfabética)
- Filtro por situação
- Filtros avançados
- Filtro por tipo de contato (Todos, Cliente, Fornecedor, Transportador, Outro)

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtros-principais">
    <a href="#" class="filtro-item" data-filtro="data">
      <span class="icone icone-calendario"></span>
      <span class="texto">por data do cadastro</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="nome">
      <span class="icone icone-ordenar"></span>
      <span class="texto">nome</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="situacao">
      <span class="icone icone-status"></span>
      <span class="texto">por situação</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="avancado">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
  </div>
  <div class="filtros-tipo">
    <a href="#" class="filtro-tipo ativo" data-tipo="todos">
      <span class="texto">todos</span>
      <span class="contador">111</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="cliente">
      <span class="texto">cliente</span>
      <span class="contador">08</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="fornecedor">
      <span class="texto">fornecedor</span>
      <span class="contador">01</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="transportador">
      <span class="texto">transportador</span>
    </a>
    <a href="#" class="filtro-tipo" data-tipo="outro">
      <span class="texto">outro</span>
      <span class="contador">100</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.filtros-container {
  display: flex;
  flex-direction: column;
  padding: 8px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.filtros-principais {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
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

.filtros-tipo {
  display: flex;
  gap: 4px;
}

.filtro-tipo {
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

.filtro-tipo.ativo {
  background-color: #f5f5f5;
  border-color: #1890ff;
  color: #1890ff;
}

.filtro-tipo .contador {
  margin-left: 6px;
  font-size: 12px;
  color: #666666;
}

.filtro-tipo.ativo .contador {
  color: #1890ff;
}
```

### Tabela de Contatos

A tabela exibe os contatos cadastrados com suas informações principais:

- Checkbox para seleção
- Nome do contato
- CPF/CNPJ
- Cidade
- Contato (telefone/email)
- Ações por linha

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-contatos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-nome">Nome</th>
        <th class="coluna-documento">CPF/CNPJ</th>
        <th class="coluna-cidade">Cidade</th>
        <th class="coluna-contato">Contato</th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-contato">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-nome">
          <div class="contato-info">
            <div class="contato-tag">29</div>
            <div class="contato-detalhes">
              <div class="contato-nome">ABSOLUTTA ELETRÔNICA LTDA</div>
              <div class="contato-nome-fantasia">ABSOLUTTA ELETRÔNICA LTDA</div>
            </div>
          </div>
        </td>
        <td class="coluna-documento">55.099.891/0001-77</td>
        <td class="coluna-cidade">Osasco</td>
        <td class="coluna-contato"></td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-editar"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de contato -->
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

.tabela-contatos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-contatos th,
.tabela-contatos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-contatos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-nome {
  min-width: 250px;
}

.coluna-documento {
  width: 180px;
}

.coluna-cidade {
  width: 150px;
}

.coluna-contato {
  width: 180px;
}

.coluna-acoes {
  width: 80px;
  text-align: right;
}

.contato-info {
  display: flex;
  align-items: center;
}

.contato-tag {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #1890ff;
  color: white;
  border-radius: 4px;
  font-size: 12px;
  margin-right: 12px;
}

.contato-detalhes {
  display: flex;
  flex-direction: column;
}

.contato-nome {
  font-weight: 500;
  color: #333333;
}

.contato-nome-fantasia {
  font-size: 12px;
  color: #999999;
  margin-top: 2px;
}

.botao-acao {
  width: 32px;
  height: 32px;
  display: flex;
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

### Filtros e Pesquisa

O módulo permite filtrar e pesquisar contatos com diversas opções:

```javascript
// Código para pesquisa de contatos
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
  // Lógica para filtrar contatos pelo termo de pesquisa
  fetch(`/api/contatos/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarTabelaContatos(data);
    });
}

// Código para alternar entre visualizações (lista/grade)
document.querySelectorAll(".botao-visualizacao").forEach((botao) => {
  botao.addEventListener("click", function () {
    // Remove classe ativo de todos os botões
    document.querySelectorAll(".botao-visualizacao").forEach((b) => {
      b.classList.remove("ativo");
    });

    // Adiciona classe ativo ao botão clicado
    this.classList.add("ativo");

    // Altera o modo de visualização
    const modo = this.getAttribute("data-view");
    alterarModoVisualizacao(modo);
  });
});

function alterarModoVisualizacao(modo) {
  const container = document.querySelector(".tabela-container");

  if (modo === "grade") {
    container.classList.add("modo-grade");
    container.classList.remove("modo-lista");
  } else {
    container.classList.add("modo-lista");
    container.classList.remove("modo-grade");
  }
}
```

### Filtros por Tipo de Contato

Os filtros por tipo permitem visualizar apenas contatos específicos:

```javascript
// Código para filtrar por tipo de contato
document.querySelectorAll(".filtro-tipo").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-tipo").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por tipo
    const tipo = this.getAttribute("data-tipo");
    filtrarPorTipo(tipo);
  });
});

function filtrarPorTipo(tipo) {
  // Lógica para filtrar contatos por tipo
  let url = "/api/contatos";

  if (tipo !== "todos") {
    url += `?tipo=${tipo}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarTabelaContatos(data);
    });
}
```

### Seleção de Contatos

A funcionalidade de seleção permite operações em lote:

```javascript
// Código para seleção de contatos
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

### Inclusão de Novo Contato

O botão de inclusão abre um formulário para cadastro:

```javascript
// Código para inclusão de novo contato
document.querySelector("#btn-incluir").addEventListener("click", function () {
  // Abre o modal de cadastro
  abrirModalCadastro();
});

function abrirModalCadastro() {
  // Cria e exibe o modal de cadastro
  const modal = document.createElement("div");
  modal.classList.add("modal-cadastro");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Novo Cadastro</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <form id="form-cadastro">
          <!-- Campos do formulário -->
          <div class="form-grupo">
            <label for="tipo">Tipo de Cadastro</label>
            <select id="tipo" name="tipo" required>
              <option value="cliente">Cliente</option>
              <option value="fornecedor">Fornecedor</option>
              <option value="transportador">Transportador</option>
              <option value="outro">Outro</option>
            </select>
          </div>
          <div class="form-grupo">
            <label for="nome">Nome/Razão Social</label>
            <input type="text" id="nome" name="nome" required>
          </div>
          <div class="form-grupo">
            <label for="documento">CPF/CNPJ</label>
            <input type="text" id="documento" name="documento" required>
          </div>
          <!-- Outros campos -->
        </form>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
        <button class="botao botao-primario" id="btn-salvar">Salvar</button>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos aos botões do modal
  modal.querySelector(".botao-fechar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-cancelar").addEventListener("click", () => {
    document.body.removeChild(modal);
  });

  modal.querySelector("#btn-salvar").addEventListener("click", () => {
    const form = document.querySelector("#form-cadastro");
    if (form.checkValidity()) {
      // Coleta os dados do formulário
      const formData = new FormData(form);

      // Envia os dados para a API
      fetch("/api/contatos", {
        method: "POST",
        body: formData,
      })
        .then((response) => response.json())
        .then((data) => {
          // Atualiza a tabela com o novo contato
          adicionarContatoTabela(data);

          // Fecha o modal
          document.body.removeChild(modal);
        });
    } else {
      form.reportValidity();
    }
  });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .filtros-tipo {
    flex-wrap: wrap;
  }

  .filtro-tipo {
    flex: 1;
    min-width: 100px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .modulo-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 12px;
    width: 100%;
  }

  .filtros-principais {
    flex-wrap: wrap;
  }

  .filtro-item {
    flex: 1;
    min-width: 120px;
  }

  .coluna-cidade,
  .coluna-contato {
    display: none;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .filtro-item {
    min-width: 100%;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 24px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Tags de Identificação

```css
.tag {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
  color: white;
}

.tag-cliente {
  background-color: #52c41a;
}

.tag-fornecedor {
  background-color: #722ed1;
}

.tag-transportador {
  background-color: #fa8c16;
}

.tag-outro {
  background-color: #8c8c8c;
}
```

### Formulários

```css
.form-grupo {
  margin-bottom: 16px;
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

.form-grupo-inline {
  display: flex;
  gap: 12px;
}

.form-grupo-inline > * {
  flex: 1;
}
```

### Modais

```css
.modal-cadastro {
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

## Fluxos de Navegação

1. **Listagem de Contatos**:

   - A tela inicial exibe todos os contatos cadastrados
   - Filtros permitem refinar a visualização por tipo, data, nome ou situação
   - Pesquisa permite localizar contatos específicos por nome, código, email ou documento

2. **Cadastro de Novo Contato**:

   - Clique no botão "incluir cadastro" abre o modal de cadastro
   - Preenchimento do formulário com dados do contato
   - Salvamento adiciona o contato à listagem

3. **Edição de Contato**:

   - Clique no ícone de edição na linha do contato abre o formulário preenchido
   - Alterações são salvas e refletidas na listagem

4. **Ações em Lote**:

   - Seleção de múltiplos contatos via checkbox
   - Barra de ações em lote é exibida com opções relevantes
   - Ações aplicadas a todos os contatos selecionados

5. **Impressão e Exportação**:
   - Botão de impressão permite gerar relatórios dos contatos
   - Menu "mais ações" oferece opções de exportação em diferentes formatos

## Conclusão

O módulo "Clientes e Fornecedores" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente de contatos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, seleção e manipulação de dados de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e tons de cinza para criar contraste e hierarquia visual. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.
