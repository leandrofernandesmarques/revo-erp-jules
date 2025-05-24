# Análise do Módulo Vendedores - ERP Revo

## Estrutura Geral

O módulo "Vendedores" do ERP Revo apresenta uma interface organizada para gerenciamento de vendedores e representantes comerciais, com uma estrutura que facilita o cadastro, visualização e manipulação dos registros. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma área de listagem de vendedores, que no estado atual mostra uma mensagem de ausência de itens cadastrados.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Vendedores"
- Botão de inclusão de novo vendedor

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Vendedores</h1>
  </div>
  <div class="acoes-container">
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir vendedor</span>
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

.botao .icone {
  margin-right: 8px;
}
```

### Barra de Pesquisa

A barra de pesquisa permite filtrar os vendedores por diferentes critérios:

- Campo de texto para pesquisa por nome ou código
- Botão de busca

**Estrutura HTML:**

```html
<div class="barra-pesquisa">
  <div class="campo-pesquisa">
    <input
      type="text"
      placeholder="Pesquise por nome ou código"
      class="input-pesquisa"
    />
    <button class="botao-busca">
      <span class="icone icone-busca"></span>
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
```

### Filtros de Status

Os filtros permitem refinar a visualização dos vendedores por status:

- Ativos com acesso ao sistema
- Todos
- Ativos
- Inativos
- Excluídos

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtros-status">
    <a href="#" class="filtro-status ativo" data-status="acesso">
      <span class="texto">Ativos com acesso ao sistema</span>
    </a>
    <a href="#" class="filtro-status" data-status="todos">
      <span class="texto">Todos</span>
    </a>
    <a href="#" class="filtro-status" data-status="ativos">
      <span class="texto">Ativos</span>
    </a>
    <a href="#" class="filtro-status" data-status="inativos">
      <span class="texto">Inativos</span>
    </a>
    <a href="#" class="filtro-status" data-status="excluidos">
      <span class="texto">Excluídos</span>
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

.filtros-status {
  display: flex;
  gap: 8px;
}

.filtro-status {
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

.filtro-status.ativo {
  background-color: #f5f5f5;
  border-color: #1890ff;
  color: #1890ff;
}

.filtro-status:hover {
  background-color: #e6f7ff;
}
```

### Área de Conteúdo Vazio

Quando não há vendedores cadastrados, a interface exibe uma mensagem informativa:

**Estrutura HTML:**

```html
<div class="conteudo-vazio">
  <div class="conteudo-vazio-container">
    <h2 class="conteudo-vazio-titulo">
      Você não possui nenhum item cadastrado.
    </h2>
    <p class="conteudo-vazio-descricao">
      Para inserir novos registros você pode clicar em incluir vendedor.
    </p>
    <div class="conteudo-vazio-acoes">
      <button class="botao botao-primario" id="btn-incluir-vendedor">
        <span class="texto">incluir vendedor</span>
      </button>
    </div>
    <div class="conteudo-vazio-ilustracao">
      <!-- Ilustração -->
    </div>
    <div class="conteudo-vazio-ajuda">
      <p>Ficou com alguma dúvida?</p>
      <a href="#" class="link-ajuda">Acesse a ajuda do Revo.</a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-vazio {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 400px;
  background-color: #ffffff;
  padding: 24px;
}

.conteudo-vazio-container {
  max-width: 600px;
  text-align: center;
  padding: 24px;
  border: 1px solid #f0f0f0;
  border-radius: 8px;
  background-color: #ffffff;
}

.conteudo-vazio-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.conteudo-vazio-descricao {
  font-size: 14px;
  color: #666666;
  margin-bottom: 24px;
}

.conteudo-vazio-acoes {
  margin-bottom: 24px;
}

.conteudo-vazio-ilustracao {
  margin: 24px 0;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.conteudo-vazio-ajuda {
  margin-top: 24px;
  font-size: 14px;
  color: #666666;
}

.link-ajuda {
  color: #1890ff;
  text-decoration: none;
}

.link-ajuda:hover {
  text-decoration: underline;
}
```

### Tabela de Vendedores

Quando há vendedores cadastrados, a tabela exibe os itens com suas informações principais:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-vendedores">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-codigo">Código</th>
        <th class="coluna-nome">Nome</th>
        <th class="coluna-email">E-mail</th>
        <th class="coluna-comissao">Comissão (%)</th>
        <th class="coluna-status">Status</th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-vendedor">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-codigo">001</td>
        <td class="coluna-nome">João Silva</td>
        <td class="coluna-email">joao.silva@exemplo.com</td>
        <td class="coluna-comissao">5,00</td>
        <td class="coluna-status">
          <span class="badge badge-ativo">Ativo</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao">
            <span class="icone icone-editar"></span>
          </button>
          <button class="botao-acao">
            <span class="icone icone-mais"></span>
          </button>
        </td>
      </tr>
      <!-- Outras linhas de vendedores -->
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

.tabela-vendedores {
  width: 100%;
  border-collapse: collapse;
}

.tabela-vendedores th,
.tabela-vendedores td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-vendedores th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-codigo {
  width: 80px;
}

.coluna-nome {
  min-width: 200px;
}

.coluna-email {
  min-width: 200px;
}

.coluna-comissao {
  width: 120px;
}

.coluna-status {
  width: 100px;
}

.coluna-acoes {
  width: 80px;
  text-align: right;
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

.badge-ativo {
  background-color: #e6f7ff;
  color: #1890ff;
}

.badge-inativo {
  background-color: #f5f5f5;
  color: #999999;
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
  margin-left: 4px;
}

.botao-acao:hover {
  background-color: #f5f5f5;
}
```

## Interações JavaScript

### Pesquisa e Filtros

O módulo permite pesquisar e filtrar vendedores:

```javascript
// Código para pesquisa de vendedores
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
  // Lógica para filtrar vendedores pelo termo de pesquisa
  fetch(`/api/vendedores/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaVendedores(data);
    });
}

// Código para filtros de status
document.querySelectorAll(".filtro-status").forEach((filtro) => {
  filtro.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove classe ativo de todos os filtros
    document.querySelectorAll(".filtro-status").forEach((f) => {
      f.classList.remove("ativo");
    });

    // Adiciona classe ativo ao filtro clicado
    this.classList.add("ativo");

    // Aplica o filtro por status
    const status = this.getAttribute("data-status");
    filtrarPorStatus(status);
  });
});

function filtrarPorStatus(status) {
  // Lógica para filtrar vendedores por status
  let url = "/api/vendedores";

  if (status !== "todos") {
    url += `?status=${status}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaVendedores(data);
    });
}
```

### Inclusão de Novo Vendedor

Os botões de inclusão redirecionam para o formulário de cadastro:

```javascript
// Código para inclusão de novo vendedor
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/vendedores/novo";
});

document
  .querySelector("#btn-incluir-vendedor")
  .addEventListener("click", function (e) {
    // Redireciona para a página de cadastro
    window.location.href = "/vendedores/novo";
  });
```

## Formulário de Cadastro de Vendedor

Quando o usuário clica em "Incluir vendedor", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Novo Vendedor</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-vendedor">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Básicas</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="codigo">Código</label>
            <input type="text" id="codigo" name="codigo" placeholder="Código do vendedor">
          </div>
          <div class="form-grupo form-grupo-grande">
            <label for="nome">Nome *</label>
            <input type="text" id="nome" name="nome" placeholder="Nome do vendedor" required>
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="email">E-mail</label>
            <input type="email" id="email" name="email" placeholder="E-mail do vendedor">
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="telefone">Telefone</label>
            <input type="tel" id="telefone" name="telefone" placeholder="Telefone do vendedor">
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="celular">Celular</label>
            <input type="tel" id="celular" name="celular" placeholder="Celular do vendedor">
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Comissão</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-pequeno">
            <label for="comissao">Comissão (%)</label>
            <input type="text" id="comissao" name="comissao" placeholder="0,00">
          </div>
          <div class="form-grupo">
            <label for="tipo_comissao">Tipo de Comissão</label>
            <select id="tipo_comissao" name="tipo_comissao">
              <option value="padrao">Padrão</option>
              <option value="por_produto">Por Produto</option>
              <option value="por_cliente">Por Cliente</option>
            </select>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Acesso ao Sistema</h2>
        <div class="form-linha">
          <div class="form-grupo">
            <div class="opcao-checkbox">
              <input type="checkbox" id="acesso_sistema" name="acesso_sistema">
              <label for="acesso_sistema">Permitir acesso ao sistema</label>
            </div>
          </div>
        </div>
        <div class="form-linha acesso-sistema-campos" style="display: none;">
          <div class="form-grupo form-grupo-medio">
            <label for="usuario">Usuário *</label>
            <input type="text" id="usuario" name="usuario" placeholder="Nome de usuário">
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="senha">Senha *</label>
            <input type="password" id="senha" name="senha" placeholder="Senha de acesso">
          </div>
        </div>
        <div class="form-linha acesso-sistema-campos" style="display: none;">
          <div class="form-grupo">
            <label>Permissões</label>
            <div class="opcoes-checkbox">
              <div class="opcao-checkbox">
                <input type="checkbox" id="perm_vendas" name="permissoes[]" value="vendas">
                <label for="perm_vendas">Vendas</label>
              </div>
              <div class="opcao-checkbox">
                <input type="checkbox" id="perm_clientes" name="permissoes[]" value="clientes">
                <label for="perm_clientes">Clientes</label>
              </div>
              <div class="opcao-checkbox">
                <input type="checkbox" id="perm_produtos" name="permissoes[]" value="produtos">
                <label for="perm_produtos">Produtos</label>
              </div>
              <div class="opcao-checkbox">
                <input type="checkbox" id="perm_financeiro" name="permissoes[]" value="financeiro">
                <label for="perm_financeiro">Financeiro</label>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Status</h2>
        <div class="form-linha">
          <div class="form-grupo">
            <div class="opcoes-radio">
              <label class="opcao-ra
(Content truncated due to size limit. Use line ranges to read in chunks)
```
