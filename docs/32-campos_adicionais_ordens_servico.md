# Análise do Módulo Configurações de Campos Adicionais para Ordens de Serviço - ERP Revo

## Estrutura Geral

O módulo "Configurações de Campos Adicionais para Ordens de Serviço" do ERP Revo apresenta uma interface para gerenciar campos personalizados que podem ser adicionados às ordens de serviço. A página exibe uma lista de campos adicionais cadastrados (ou uma mensagem indicando que não há itens cadastrados) e permite a inclusão de novos campos.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Navegação

A seção superior contém o título da página e links de navegação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/configuracoes" class="breadcrumb-item">Configurações</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual"
      >Campos Adicionais para Ordens de Serviço</span
    >
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Campos adicionais para ordens de serviços</h1>
  </div>

  <div class="cabecalho-acoes">
    <a
      href="/configuracoes"
      class="botao-acao botao-secundario"
      id="btn-voltar"
    >
      <span class="icone icone-voltar"></span>
      <span class="texto">Voltar</span>
    </a>
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
  align-items: center;
  gap: 8px;
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
}

.botao-secundario {
  background-color: #ffffff;
  color: #666666;
  border: 1px solid #d9d9d9;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
}
```

### Barra de Ferramentas

A barra de ferramentas contém um campo de pesquisa e um botão para incluir novo campo adicional:

**Estrutura HTML:**

```html
<div class="barra-ferramentas">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquisa..."
      id="campo-pesquisa"
    />
    <button type="button" class="botao-pesquisa" id="btn-pesquisa">
      <span class="icone icone-pesquisa"></span>
    </button>
  </div>

  <div class="acoes-container">
    <button
      type="button"
      class="botao-acao botao-primario"
      id="btn-incluir-campo"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir campo adicional</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.barra-ferramentas {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  position: relative;
  width: 300px;
}

.campo-pesquisa {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 40px;
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999999;
}

.botao-pesquisa:hover {
  color: #666666;
}

.acoes-container {
  display: flex;
  gap: 8px;
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

.icone-adicionar::before {
  content: "+";
}

.icone-pesquisa::before {
  content: "🔍";
}
```

### Área de Conteúdo (Estado Vazio)

Quando não há campos adicionais cadastrados, a página exibe uma mensagem indicando que não há itens e instruções para adicionar novos:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="estado-vazio">
    <div class="estado-vazio-ilustracao">
      <img
        src="/assets/images/ilustracao-vazio.svg"
        alt="Nenhum item cadastrado"
        class="ilustracao-vazio"
      />
    </div>

    <div class="estado-vazio-mensagem">
      <h3 class="estado-vazio-titulo">
        Você não possui nenhum item cadastrado.
      </h3>
      <p class="estado-vazio-descricao">
        Para inserir novos registros você pode clicar em incluir campo
        adicional.
      </p>

      <div class="estado-vazio-acoes">
        <button
          type="button"
          class="botao-acao botao-primario"
          id="btn-incluir-campo-vazio"
        >
          <span class="texto">incluir campo adicional</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  background-color: #ffffff;
  min-height: 400px;
  display: flex;
  flex-direction: column;
}

.estado-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 48px 24px;
  background-color: #fafafa;
  border-radius: 4px;
  border: 1px solid #f0f0f0;
}

.estado-vazio-ilustracao {
  margin-bottom: 24px;
}

.ilustracao-vazio {
  width: 120px;
  height: auto;
}

.estado-vazio-mensagem {
  max-width: 400px;
}

.estado-vazio-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
  margin-bottom: 8px;
}

.estado-vazio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
  margin-bottom: 16px;
}

.estado-vazio-acoes {
  display: flex;
  justify-content: center;
  margin-top: 16px;
}
```

### Área de Conteúdo (Com Campos Adicionais)

Quando há campos adicionais cadastrados, a página exibe uma tabela com a lista de campos:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela-campos">
      <thead>
        <tr>
          <th class="coluna-nome">Nome</th>
          <th class="coluna-tipo">Tipo</th>
          <th class="coluna-obrigatorio">Obrigatório</th>
          <th class="coluna-acoes">Ações</th>
        </tr>
      </thead>
      <tbody>
        <!-- Exemplo de linha de campo adicional -->
        <tr>
          <td class="coluna-nome">Número do Patrimônio</td>
          <td class="coluna-tipo">Texto</td>
          <td class="coluna-obrigatorio">
            <span class="badge badge-sim">Sim</span>
          </td>
          <td class="coluna-acoes">
            <button
              type="button"
              class="botao-acao-tabela botao-editar"
              title="Editar"
            >
              <span class="icone icone-editar"></span>
            </button>
            <button
              type="button"
              class="botao-acao-tabela botao-excluir"
              title="Excluir"
            >
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <!-- Fim do exemplo -->
      </tbody>
    </table>
  </div>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  width: 100%;
  overflow-x: auto;
}

.tabela-campos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-campos th,
.tabela-campos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-campos th {
  font-weight: 600;
  background-color: #fafafa;
  color: #333333;
}

.tabela-campos tr:hover {
  background-color: #f5f5f5;
}

.coluna-nome {
  width: 40%;
}

.coluna-tipo {
  width: 20%;
}

.coluna-obrigatorio {
  width: 20%;
}

.coluna-acoes {
  width: 20%;
  text-align: right;
}

.badge {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.badge-sim {
  background-color: #f6ffed;
  color: #52c41a;
  border: 1px solid #b7eb8f;
}

.badge-nao {
  background-color: #fff7e6;
  color: #fa8c16;
  border: 1px solid #ffd591;
}

.botao-acao-tabela {
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
  margin-left: 8px;
  color: #666666;
  border-radius: 4px;
}

.botao-acao-tabela:hover {
  background-color: #f0f0f0;
}

.botao-editar:hover {
  color: #1890ff;
}

.botao-excluir:hover {
  color: #f5222d;
}

.icone-editar::before {
  content: "✏️";
}

.icone-excluir::before {
  content: "🗑️";
}
```

### Rodapé

O rodapé contém um link para a ajuda do Revo:

**Estrutura HTML:**

```html
<div class="rodape-container">
  <div class="rodape-ajuda">
    <p class="rodape-texto">Ficou com alguma dúvida?</p>
    <a href="#" class="rodape-link">Acesse a ajuda do Revo.</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.rodape-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #f0f0f0;
  margin-top: auto;
}

.rodape-ajuda {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.rodape-texto {
  font-size: 14px;
  color: #666666;
  margin: 0;
  margin-bottom: 4px;
}

.rodape-link {
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.rodape-link:hover {
  text-decoration: underline;
}
```

## Modal de Inclusão/Edição de Campo Adicional

Quando o usuário clica em "Incluir campo adicional" ou no botão de editar um campo existente, é exibido um modal para preencher as informações:

**Estrutura HTML:**

```html
<div class="modal" id="modal-campo">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h3 class="modal-titulo">Incluir campo adicional</h3>
      <button type="button" class="modal-fechar" id="btn-fechar-modal">
        ×
      </button>
    </div>

    <div class="modal-corpo">
      <div class="campo-grupo">
        <label for="nome-campo" class="campo-label">Nome do campo</label>
        <input
          type="text"
          id="nome-campo"
          name="nome_campo"
          class="campo-texto"
        />
      </div>

      <div class="campo-grupo">
        <label for="tipo-campo" class="campo-label">Tipo do campo</label>
        <select id="tipo-campo" name="tipo_campo" class="campo-select">
          <option value="texto">Texto</option>
          <option value="numero">Número</option>
          <option value="data">Data</option>
          <option value="hora">Hora</option>
          <option value="selecao">Seleção</option>
          <option value="checkbox">Checkbox</option>
        </select>
      </div>

      <div class="campo-grupo" id="opcoes-container" style="display: none;">
        <label class="campo-label">Opções de seleção</label>
        <div class="opcoes-lista" id="opcoes-lista">
          <div class="opcao-item">
            <input
              type="text"
              class="campo-texto campo-opcao"
              placeholder="Digite uma opção"
            />
            <button type="button" class="botao-remover-opcao">
              <span class="icone icone-remover"></span>
            </button>
          </div>
        </div>
        <button
          type="button"
          class="botao-acao botao-secundario botao-adicionar-opcao"
          id="btn-adicionar-opcao"
        >
          <span class="icone icone-adicionar"></span>
          <span class="texto">Adicionar opção</span>
        </button>
      </div>

      <div class="campo-grupo">
        <label for="descricao-campo" class="campo-label"
          >Descrição (opcional)</label
        >
        <textarea
          id="descricao-campo"
          name="descricao_campo"
          class="campo-texto campo-textarea"
          placeholder="Descrição ou instruções para preenchimento"
        ></textarea>
      </div>

      <div class="campo-grupo campo-checkbox">
        <input
          type="checkbox"
          id="campo-obrigatorio"
          name="campo_obrigatorio"
          class="campo-checkbox-input"
        />
        <label for="campo-obrigatorio" class="campo-checkbox-label"
          >Campo obrigatório</label
        >
      </div>
    </div>

    <div class="modal-rodape">
      <button
        type="button"
        class="botao-acao botao-secundario"
        id="btn-cancelar-modal"
      >
        <span class="texto">Cancelar</span>
      </button>

      <button
        type="button"
        class="botao-acao botao-primario"
        id="btn-salvar-campo"
      >
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-conteudo {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 500px;
  max-width: 90%;
  display: flex;
  flex-direction: column;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-cabecalho {
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: sticky;
  top: 0;
  background-color: #ffffff;
  z-index: 1;
}

.modal-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.modal-fechar {
  background: none;
  border: none;
  font-size: 24px;
  color: #999999;
  cursor: pointer;
  padding: 0;
  line-height: 1;
}

.modal-fechar:hover {
  color: #666666;
}

.modal-corpo {
  padding: 16px;
  overflow-y: auto;
}

.modal-rodape {
  padding: 16px;
  border-top: 1px solid #f0f0f0;
  display: flex;
  justify-content: flex-end;
  gap: 8px;
  position: sticky;
  bottom: 0;
  background-color: #ffffff;
  z-index: 1;
}

.campo-grupo {
  margin-bottom: 16px;
}

.campo-label {
  display: block;
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.campo-texto {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-texto:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-select {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  background-color: #ffffff;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.825L1.175 4 2.05 3.125 6 7.075 9.95 3.125 10.825 4z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.campo-select:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-textarea {
  min-height: 80px;
  resize: vertical;
}

.campo-checkbox {
  display: flex;
  align-items: center;
}

.campo-checkbox-input {
  margin: 0;
  margin-right: 8px;
}

.campo-checkbox-label {
  font-size: 14px;
  color: #333333;
  cursor: pointer;
}

.opcoes-lista {
  margin-bottom: 8px;
}

.opcao-item {
  display: flex;
  align-items: center;
  margin-bottom: 8px;
}

.campo-opcao {
  flex: 1;
}

.botao-remover-opcao {
  background: none;
  border: none;
  color: #f5222d;
  cursor: pointer;
  padding: 4px 8px;
  margin-left: 8px;
  border-radius: 4px;
}

.botao-remover-opcao:hover {
  background-color: #fff1f0;
}

.botao-adicionar-opcao {
  margin-top: 8px;
}

.icone-remover::before {
  content: "×";
}
```

## Interações JavaScript

### Pesquisa de Campos Adicionais

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Pesquisa de campos adicionais
  const campoPesquisa = document.getElementById("campo-pesquisa");
  const btnPesquisa = document.getElementById("btn-pesquisa");

  if (campoPesquisa && btnPesquisa) {
    btnPesquisa.addEventListener("click", function () {
      pesquisarCampos(campoPesquisa.value);
    });

    campoPesquisa.addEventListener("keypress", function (e) {
      if (e.key === "Enter") {
        pesquisarCampos(campoPesquisa.value);
      }
    });

    function pesquisarCampos(termo) {
      console.log("Pesquisando campos:", termo);

      // Aqui seria implementada a lógica para filtrar os campos
      // Por exemplo, usando uma requisição AJAX ou filtrando os elementos da tabela
    }
  }
});
```

### Abertura e Fechamento do Modal

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const btnIncluirCampo = document.getElementById("btn-incluir-campo");
  const btnIncluirCampoVazio = document.getElementById(
    "btn-incluir-campo-vazio"
  );
  const modal = document.getElementById("modal-campo");
  const btnFecharModal = document.getElementById("btn-fechar-modal");
  const btnCancelarModal = document.getElementById("btn-cancelar-modal");

  // Função para abrir o modal
  function abrirModal() {
    if (modal) {
      modal.style.display = "flex";
      document.getElementById("nome-campo").focus();
    }
  }

  // Função para fechar o modal
  function fecharModal() {
    if (modal) {
      modal.style.display = "none";
      // Limpar os campos do formulário
      document.getElementById("nome-campo").value = "";
      document.getElementById("tipo-campo").value = "texto";
      document.getElementById("descricao-campo").value = "";
      document.getElementById("campo-obrigatorio").checked = false;

      // Limpar as opções de seleção
      const opcoesLista = document.getElementById("opcoes-lista");
      if (opcoesLista) {
        opcoesLista.innerHTML = `
          <div class="opcao-item">
            <input type="text" class="campo-texto campo-opcao" placeholder="Digite uma opção">
            <button type="button" class="botao-remover-opcao">
              <span class="icone icone-remover"></span>
            </button>
          </div>
        `;
      }

      // Esconder o container de opções
      document.getElementById("opcoes-container").style.display = "none";

      // Alterar o título do modal para "Incluir campo adicional"
      document.querySelector(".modal-titulo").textContent =
        "Incluir campo adicional";
    }
  }

  // Adicionar event listeners
  if (btnIncluirCampo) {
    btnIncluirCampo.addEventListener("click", abrirModal);
  }

  if (btnIncluirCampoVazio) {
    btnIncluirCampoVazio.addEventListener("click", abrirModal);
  }

  if (btnFecharModal) {
    btnFecharModal.addEventListener("click", fecharModal);
  }

  if (btnCancelarModal) {
    btnCancelarModal.addEventListener("click", fecharModal);
  }

  // Fechar o modal ao clicar fora dele
  if (modal) {
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        fecharModal();
      }
    });
  }
});
```

### Gerenciamento de Tipo de Campo

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Gerenciamento de tipo de campo
  const tipoCampo = document.getElementById("tipo-campo");
  const opcoesContainer = document.getElementById("opcoes-container");

  if (tipoCampo && opcoesContainer) {
    tipoCampo.addEventListener("change", function () {
      // Mostrar o container de opções apenas se o tipo for "selecao"
      if (this.value === "selecao") {
        opcoesContainer.style.display = "block";
      } else {
        opcoesContainer.style.display = "none";
      }
    });
  }
});
```

### Gerenciamento de Opções de Seleção

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Gerenciamento de opções de seleção
  const btnAdicionarOpcao = document.getElementById("btn-adicionar-opcao");
  const opcoesLista = document.getElementById("opcoes-lista");

  if (btnAdicionarOpcao && opcoesLista) {
    // Adicionar nova opção
    btnAdicionarOpcao.addEventListener("click", function () {
      const novaOpcao = document.createElement("div");
      novaOpcao.className = "opcao-item";
      novaOpcao.innerHTML = `
        <input type="text" class="campo-texto campo-opcao" placeholder="Digite uma opção">
        <button type="button" class="botao-remover-opcao">
          <span class="icone icone-remover"></span>
        </button>
      `;

      opcoesLista.appendChild(novaOpcao);

      // Focar no novo campo
      const novoCampo = novaOpcao.querySelector(".campo-opcao");
      if (novoCampo) {
        novoCampo.focus();
      }
    });

    // Remover opção (delegação de eventos)
    opcoesLista.addEventListener("click", function (e) {
      const botaoRemover = e.target.closest(".botao-remover-opcao");

      if (botaoRemover) {
        const opcaoItem = botaoRemover.closest(".opcao-item");

        // Não remover se for a única opção
        const opcoes = opcoesLista.querySelectorAll(".opcao-item");
        if (opcoes.length > 1) {
          opcaoItem.remove();
        } else {
          // Limpar o valor do campo
          const campo = opcaoItem.querySelector(".campo-opcao");
          if (campo) {
            campo.value = "";
            campo.focus();
          }
        }
      }
    });
  }
});
```

### Salvar Campo Adicional

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Salvar campo adicional
  const btnSalvarCampo = document.getElementById("btn-salvar-campo");

  if (btnSalvarCampo) {
    btnSalvarCampo.addEventListener("click", function () {
      const nomeCampo = document.getElementById("nome-campo").value;
      const tipoCampo = document.getElementById("tipo-campo").value;
      const descricaoCampo = document.getElementById("descricao-campo").value;
      const campoObrigatorio =
        document.getElementById("campo-obrigatorio").checked;

      // Validação básica
      if (!nomeCampo) {
        alert("O nome do campo é obrigatório.");
        return;
      }

      // Obter as opções de seleção, se aplicável
      let opcoes = [];
      if (tipoCampo === "selecao") {
        const camposOpcao = document.querySelectorAll(".campo-opcao");

        camposOpcao.forEach(function (campo) {
          if (campo.value.trim()) {
            opcoes.push(campo.value.trim());
          }
        });

        if (opcoes.length === 0) {
          alert("É necessário adicionar pelo menos uma opção de seleção.");
          return;
        }
      }

      // Criar o objeto com os dados
      const campo = {
        nome: nomeCampo,
        tipo: tipoCampo,
        descricao: descricaoCampo,
        obrigatorio: campoObrigatorio,
        opcoes: opcoes,
      };

      // Salvar o campo
      salvarCampo(campo);
    });

    function salvarCampo(campo) {
      console.log("Salvando campo:", campo);

      // Aqui seria implementada a lógica para salvar o campo no servidor
      // Por exemplo, usando uma requisição AJAX

      // Simula o salvamento bem-sucedido
      setTimeout(() => {
        alert("Campo adicional salvo com sucesso!");

        // Fechar o modal
        document.getElementById("btn-fechar-modal").click();

        // Recarregar a lista de campos
        // Esta parte seria implementada de acordo com a lógica da aplicação
      }, 1000);
    }
  }
});
```

### Editar e Excluir Campo Adicional

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Editar campo adicional
  const botoesEditar = document.querySelectorAll(".botao-editar");

  botoesEditar.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter os dados do campo a partir da linha da tabela
      const linha = this.closest("tr");
      const nome = linha.querySelector(".coluna-nome").textContent;
      const tipo = linha
        .querySelector(".coluna-tipo")
        .textContent.toLowerCase();
      const obrigatorio = linha.querySelector(".badge-sim") !== null;

      // Preencher o formulário
      document.getElementById("nome-campo").value = nome;
      document.getElementById("tipo-campo").value = tipo;
      document.getElementById("campo-obrigatorio").checked = obrigatorio;

      // Alterar o título do modal
      document.querySelector(".modal-titulo").textContent =
        "Editar campo adicional";

      // Mostrar o container de opções se o tipo for "seleção"
      if (tipo === "seleção") {
        document.getElementById("opcoes-container").style.display = "block";

        // Aqui seria necessário carregar as opções existentes
        // Esta parte seria implementada de acordo com a lógica da aplicação
      } else {
        document.getElementById("opcoes-container").style.display = "none";
      }

      // Abrir o modal
      document.getElementById("modal-campo").style.display = "flex";
    });
  });

  // Excluir campo adicional
  const botoesExcluir = document.querySelectorAll(".botao-excluir");

  botoesExcluir.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter o nome do campo a partir da linha da tabela
      const linha = this.closest("tr");
      const nome = linha.querySelector(".coluna-nome").textContent;

      // Confirmar a exclusão
      if (confirm(`Deseja realmente excluir o campo "${nome}"?`)) {
        // Excluir o campo
        excluirCampo(nome);
      }
    });
  });

  function excluirCampo(nome) {
    console.log("Excluindo campo:", nome);

    // Aqui seria implementada a lógica para excluir o campo no servidor
    // Por exemplo, usando uma requisição AJAX

    // Simula a exclusão bem-sucedida
    setTimeout(() => {
      alert("Campo adicional excluído com sucesso!");

      // Recarregar a lista de campos
      // Esta parte seria implementada de acordo com a lógica da aplicação
    }, 1000);
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .barra-ferramentas {
    flex-direction: column;
    align-items: stretch;
    gap: 16px;
  }

  .pesquisa-container {
    width: 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .cabecalho-acoes {
    flex-direction: column;
    align-items: flex-start;
  }

  .cabecalho-acoes .botao-acao {
    width: 100%;
    justify-content: center;
    margin-bottom: 8px;
  }

  .tabela-campos th,
  .tabela-campos td {
    padding: 8px;
  }

  .coluna-nome {
    width: 30%;
  }

  .coluna-tipo {
    width: 20%;
  }

  .coluna-obrigatorio {
    width: 20%;
  }

  .coluna-acoes {
    width: 30%;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .titulo-pagina {
    font-size: 20px;
  }

  .estado-vazio {
    padding: 24px 16px;
  }

  .ilustracao-vazio {
    width: 80px;
  }

  .estado-vazio-titulo {
    font-size: 14px;
  }

  .estado-vazio-descricao {
    font-size: 12px;
  }

  .coluna-obrigatorio {
    display: none;
  }

  .coluna-nome {
    width: 40%;
  }

  .coluna-tipo {
    width: 30%;
  }

  .coluna-acoes {
    width: 30%;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Verde (sucesso): #52c41a
- Verde claro (background): #f6ffed
- Laranja (alerta): #fa8c16
- Laranja claro (background): #fff7e6
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
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
  - Títulos grandes: 24px
  - Títulos médios: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

## Fluxos de Navegação

1. **Acesso às Configurações de Campos Adicionais**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configurações de campos adicionais para ordens de serviço"
   - O sistema exibe a tela de configurações de campos adicionais

2. **Inclusão de Novo Campo Adicional**:

   - O usuário clica no botão "Incluir campo adicional"
   - O sistema exibe um modal para preenchimento dos dados
   - O usuário preenche o nome, seleciona o tipo, adiciona uma descrição opcional e marca se o campo é obrigatório
   - Se o tipo for "Seleção", o usuário adiciona as opções de seleção
   - Clica em "Salvar" para confirmar
   - O sistema salva o campo adicional e atualiza a lista

3. **Edição de Campo Adicional Existente**:

   - O usuário clica no botão de edição de um campo na lista
   - O sistema exibe um modal com os dados preenchidos
   - O usuário altera os dados conforme necessário
   - Clica em "Salvar" para confirmar
   - O sistema atualiza o campo e a lista

4. **Exclusão de Campo Adicional**:

   - O usuário clica no botão de exclusão de um campo na lista
   - O sistema exibe uma confirmação
   - O usuário confirma a exclusão
   - O sistema remove o campo e atualiza a lista

5. **Pesquisa de Campos Adicionais**:

   - O usuário digita um termo no campo de pesquisa
   - Pressiona Enter ou clica no botão de pesquisa
   - O sistema filtra a lista de campos de acordo com o termo

6. **Retorno à Lista de Configurações**:
   - O usuário clica em "Voltar" para retornar à lista de configurações
   - O sistema redireciona para a página de configurações

## Conclusão

O módulo "Configurações de Campos Adicionais para Ordens de Serviço" do ERP Revo apresenta uma interface para gerenciar campos personalizados que podem ser adicionados às ordens de serviço. A página permite a inclusão, edição, exclusão e pesquisa de campos adicionais, com uma interface intuitiva e responsiva.

A interface é bem estruturada, com uma barra de ferramentas contendo um campo de pesquisa e um botão para incluir novos campos, e uma área de conteúdo que exibe a lista de campos ou uma mensagem indicando que não há itens cadastrados.

O módulo utiliza modais para a inclusão e edição de campos, com opções para diferentes tipos de campos (texto, número, data, hora, seleção, checkbox). A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações.

Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma. A responsividade é bem implementada, garantindo uma boa experiência em dispositivos móveis e desktop.
