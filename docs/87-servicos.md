# Análise do Módulo Serviços - ERP Revo

## Estrutura Geral

O módulo "Serviços" do ERP Revo apresenta uma interface organizada para gerenciamento de serviços oferecidos, com uma estrutura que facilita o cadastro, visualização e manipulação dos itens. A tela é composta por um cabeçalho com ações principais, filtros de pesquisa e uma área de listagem de serviços, que no estado atual mostra uma mensagem de ausência de itens cadastrados.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Serviços"
- Botão de impressão
- Botão de inclusão de novo serviço

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Serviços</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <a href="#/novo" class="botao botao-primario" id="btn-incluir">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir serviço</span>
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

A barra de pesquisa permite filtrar os serviços por diferentes critérios:

- Campo de texto para pesquisa por nome ou código
- Botão de busca
- Filtro por situação

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
  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="situacao">
      <span class="icone icone-status"></span>
      <span class="texto">por situação</span>
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

### Área de Conteúdo Vazio

Quando não há serviços cadastrados, a interface exibe uma mensagem informativa:

**Estrutura HTML:**

```html
<div class="conteudo-vazio">
  <div class="conteudo-vazio-container">
    <h2 class="conteudo-vazio-titulo">
      Você não possui nenhum item cadastrado.
    </h2>
    <p class="conteudo-vazio-descricao">
      Para inserir novos registros você pode clicar em incluir serviço.
    </p>
    <div class="conteudo-vazio-acoes">
      <button class="botao botao-primario" id="btn-incluir-servico">
        <span class="texto">incluir serviço</span>
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

### Tabela de Serviços

Quando há serviços cadastrados, a tabela exibe os itens com suas informações principais:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-servicos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-codigo">Código</th>
        <th class="coluna-nome">Nome</th>
        <th class="coluna-valor">Valor</th>
        <th class="coluna-status">Status</th>
        <th class="coluna-acoes"></th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-servico">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-codigo">001</td>
        <td class="coluna-nome">Instalação de Software</td>
        <td class="coluna-valor">R$ 150,00</td>
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
      <!-- Outras linhas de serviços -->
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

.tabela-servicos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-servicos th,
.tabela-servicos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-servicos th {
  font-weight: 500;
  color: #666666;
  background-color: #fafafa;
}

.coluna-selecao {
  width: 40px;
}

.coluna-codigo {
  width: 100px;
}

.coluna-nome {
  min-width: 250px;
}

.coluna-valor {
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

O módulo permite pesquisar e filtrar serviços:

```javascript
// Código para pesquisa de serviços
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
  // Lógica para filtrar serviços pelo termo de pesquisa
  fetch(`/api/servicos/pesquisa?termo=${encodeURIComponent(termo)}`)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaServicos(data);
    });
}

// Código para filtro por situação
document
  .querySelector('.filtro-item[data-filtro="situacao"]')
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre dropdown de situações
    const dropdown = document.createElement("div");
    dropdown.classList.add("dropdown-menu");
    dropdown.innerHTML = `
    <a href="#" class="dropdown-item" data-situacao="todos">Todos</a>
    <a href="#" class="dropdown-item" data-situacao="ativos">Ativos</a>
    <a href="#" class="dropdown-item" data-situacao="inativos">Inativos</a>
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

        const situacao = this.getAttribute("data-situacao");
        filtrarPorSituacao(situacao);

        // Remove o dropdown
        document.body.removeChild(dropdown);
      });
    });

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (
        !dropdown.contains(e.target) &&
        e.target !==
          document.querySelector('.filtro-item[data-filtro="situacao"]')
      ) {
        document.body.removeChild(dropdown);
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });

function filtrarPorSituacao(situacao) {
  // Lógica para filtrar serviços por situação
  let url = "/api/servicos";

  if (situacao !== "todos") {
    url += `?situacao=${situacao}`;
  }

  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      atualizarListaServicos(data);
    });
}
```

### Inclusão de Novo Serviço

Os botões de inclusão redirecionam para o formulário de cadastro:

```javascript
// Código para inclusão de novo serviço
document.querySelector("#btn-incluir").addEventListener("click", function (e) {
  // Redireciona para a página de cadastro
  window.location.href = "/servicos/novo";
});

document
  .querySelector("#btn-incluir-servico")
  .addEventListener("click", function (e) {
    // Redireciona para a página de cadastro
    window.location.href = "/servicos/novo";
  });
```

### Impressão de Relatório

O botão de impressão gera um relatório dos serviços:

```javascript
// Código para impressão de relatório
document.querySelector("#btn-imprimir").addEventListener("click", function () {
  // Abre modal de opções de impressão
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Imprimir Relatório</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="form-grupo">
          <label>Selecione o formato:</label>
          <div class="opcoes-radio">
            <label class="opcao-radio">
              <input type="radio" name="formato" value="pdf" checked>
              <span class="texto">PDF</span>
            </label>
            <label class="opcao-radio">
              <input type="radio" name="formato" value="excel">
              <span class="texto">Excel</span>
            </label>
          </div>
        </div>
        <div class="form-grupo">
          <label>Incluir no relatório:</label>
          <div class="opcoes-checkbox">
            <label class="opcao-checkbox">
              <input type="checkbox" name="incluir_valor" checked>
              <span class="texto">Valores</span>
            </label>
            <label class="opcao-checkbox">
              <input type="checkbox" name="incluir_status" checked>
              <span class="texto">Status</span>
            </label>
          </div>
        </div>
      </div>
      <div class="modal-rodape">
        <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
        <button class="botao botao-primario" id="btn-gerar">Gerar Relatório</button>
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

  modal.querySelector("#btn-gerar").addEventListener("click", () => {
    const formato = modal.querySelector('input[name="formato"]:checked').value;
    const incluirValor = modal.querySelector(
      'input[name="incluir_valor"]'
    ).checked;
    const incluirStatus = modal.querySelector(
      'input[name="incluir_status"]'
    ).checked;

    // Gera o relatório com as opções selecionadas
    gerarRelatorio(formato, incluirValor, incluirStatus);

    // Fecha o modal
    document.body.removeChild(modal);
  });
});

function gerarRelatorio(formato, incluirValor, incluirStatus) {
  // Constrói a URL com os parâmetros
  const params = new URLSearchParams();
  params.append("formato", formato);
  params.append("incluir_valor", incluirValor);
  params.append("incluir_status", incluirStatus);

  // Abre a URL em uma nova janela/aba
  window.open(`/servicos/relatorio?${params.toString()}`, "_blank");
}
```

## Formulário de Cadastro de Serviço

Quando o usuário clica em "Incluir serviço", é direcionado para um formulário de cadastro:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h1 class="formulario-titulo">Novo Serviço</h1>
    <div class="formulario-acoes">
      <button class="botao botao-secundario" id="btn-cancelar">Cancelar</button>
      <button class="botao botao-primario" id="btn-salvar">Salvar</button>
    </div>
  </div>
  <div class="formulario-corpo">
    <form id="form-servico">
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Básicas</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="codigo">Código</label>
            <input
              type="text"
              id="codigo"
              name="codigo"
              placeholder="Código do serviço"
            />
          </div>
          <div class="form-grupo form-grupo-grande">
            <label for="nome">Nome do Serviço *</label>
            <input
              type="text"
              id="nome"
              name="nome"
              placeholder="Nome do serviço"
              required
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="valor">Valor (R$) *</label>
            <input
              type="text"
              id="valor"
              name="valor"
              placeholder="0,00"
              required
            />
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="status">Status</label>
            <select id="status" name="status">
              <option value="ativo">Ativo</option>
              <option value="inativo">Inativo</option>
            </select>
          </div>
        </div>
      </div>
      <div class="form-secao">
        <h2 class="form-secao-titulo">Informações Fiscais</h2>
        <div class="form-linha">
          <div class="form-grupo form-grupo-medio">
            <label for="ncm">NCM</label>
            <input
              type="text"
              id="ncm"
              name="ncm"
              placeholder="NCM do serviço"
            />
          </div>
          <div class="form-grupo form-grupo-medio">
            <label for="codigo_servico">Código de Serviço</label>
            <input
              type="text"
              id="codigo_servico"
              name="codigo_servico"
              placeholder="Código de serviço municipal"
            />
          </div>
        </div>
        <div class="form-linha">
          <div class="form-grupo">
            <label for="descricao">Descrição para Nota Fiscal</label>
            <textarea
              id="descricao"
              name="descricao"
              rows="3"
              placeholder="Descrição detalhada para nota fiscal"
            ></textarea>
          </div>
        </div>
      </div>
    </form>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  background-color: #ffffff;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #e0e0e0;
}

.formulario-titulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.formulario-acoes {
  display: flex;
  gap: 8px;
}

.formulario-corpo {
  padding: 24px;
}

.form-secao {
  margin-bottom: 32px;
  padding-bottom: 24px;
  border-bottom: 1px solid #f0f0f0;
}

.form-secao:last-child {
  border-bottom: none;
  margin-bottom: 0;
  padding-bottom: 0;
}

.form-secao-titulo {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 16px 0;
}

.form-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 16px;
}

.form-grupo {
  flex: 1;
  min-width: 200px;
}

.form-grupo-pequeno {
  flex: 0 0 120px;
}

.form-grupo-medio {
  flex: 0 0 200px;
}

.form-grupo-grande {
  flex: 0 0 300px;
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

.opcoes-radio,
.opcoes-checkbox {
  display: flex;
  gap: 16px;
}

.opcao-radio,
.opcao-checkbox {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.opcao-radio input,
.opcao-checkbox input {
  margin-right: 6px;
}
```

## Interações JavaScript do Formulário

```javascript
// Código para manipulação do formulário
document.addEventListener("DOMContentLoaded", function () {
  // Máscara para campo de valor
  const campoValor = document.querySelector("#valor");
  if (campoValor) {
    campoValor.addEventListener("input", function (e) {
      let valor = e.target.value.replace(/\D/g, "");
      valor = (parseInt(valor) / 100).toFixed(2);
      e.target.value = valor.replace(".", ",");
    });
  }

  // Botão cancelar
  const btnCancelar = document.querySelector("#btn-cancelar");
  if (btnCancelar) {
    btnCancelar.addEventListener("click", function () {
      // Confirma se há alterações não salvas
      if (formularioAlterado()) {
        if (confirm("Há alterações não salvas. Deseja realmente sair?")) {
          window.location.href = "/servicos";
        }
      } else {
        window.location.href = "/servicos";
      }
    });
  }

  // Botão salvar
  const btnSalvar = document.querySelector("#btn-salvar");
  if (btnSalvar) {
    btnSalvar.addEventListener("click", function () {
      const form = document.querySelector("#form-servico");
      if (form.checkValidity()) {
        salvarServico();
      } else {
        form.reportValidity();
      }
    });
  }
});

function formularioAlterado() {
  // Verifica se houve alterações no formulário
  const form = document.querySelector("#form-servico");
  const formData = new FormData(form);

  // Compara com os valores originais
  // Implementação depende da lógica de negócio

  return false; // Placeholder
}

function salvarServico() {
  const form = document.querySelector("#form-servico");
  const formData = new FormData(form);

  // Converte para objeto
  const servico = {};
  formData.forEach((value, key) => {
    servico[key] = value;
  });

  // Ajusta o formato do valor
  if (servico.valor) {
    servico.valor = servico.valor.replace(",", ".");
  }

  // Envia para a API
  fetch("/api/servicos", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(servico),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar serviço");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      alert("Serviço salvo com sucesso!");

      // Redireciona para a listagem
      window.location.href = "/servicos";
    })
    .catch((error) => {
      // Exibe mensagem de erro
      alert(`Erro ao salvar serviço: ${error.message}`);
    });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1200px) {
  .form-linha {
    flex-direction: column;
    gap: 16px;
  }

  .form-grupo,
  .form-grupo-pequeno,
  .form-grupo-medio,
  .form-grupo-grande {
    flex: 1;
    width: 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 12px;
    width: 100%;
  }

  .formulario-corpo {
    padding: 16px;
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
  - Subtítulos: 18px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Badges de Status

```css
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

1. **Listagem de Serviços**:

   - A tela inicial exibe todos os serviços cadastrados ou uma mensagem quando não há itens
   - Filtros permitem refinar a visualização por situação ou outros critérios
   - Pesquisa permite localizar serviços específicos por nome ou código

2. **Cadastro de Novo Serviço**:

   - Clique no botão "Incluir serviço" redireciona para o formulário de cadastro
   - Preenchimento do formulário com dados do serviço
   - Salvamento adiciona o serviço à listagem

3. **Edição de Serviço**:

   - Clique no ícone de edição na linha do serviço abre o formulário preenchido
   - Alterações são salvas e refletidas na listagem

4. **Impressão de Relatório**:
   - Botão de impressão abre modal com opções de formato e conteúdo
   - Geração do relatório conforme as opções selecionadas

## Conclusão

O módulo "Serviços" do ERP Revo apresenta uma interface bem estruturada e funcional, com foco na gestão eficiente dos serviços oferecidos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a navegação e o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtragem, pesquisa, cadastro e manipulação de dados de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e tons de cinza para criar contraste e hierarquia visual. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

Mesmo quando não há serviços cadastrados, a interface oferece uma experiência amigável, com mensagens claras e ações diretas para o usuário iniciar o cadastro de novos itens.
