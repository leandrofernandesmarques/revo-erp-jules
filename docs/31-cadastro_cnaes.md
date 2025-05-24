# Análise do Módulo Cadastro de CNAEs - ERP Revo

## Estrutura Geral

O módulo "Cadastro de CNAEs" do ERP Revo apresenta uma interface para gerenciar os códigos CNAE (Classificação Nacional de Atividades Econômicas) que podem ser utilizados nos documentos fiscais de serviços. A página exibe uma lista de CNAEs cadastrados (ou uma mensagem indicando que não há itens cadastrados) e permite a inclusão de novos códigos.

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
    <span class="breadcrumb-item-atual">Cadastro de CNAEs</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Meus CNAEs</h1>
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

A barra de ferramentas contém um campo de pesquisa e um botão para incluir novo CNAE:

**Estrutura HTML:**

```html
<div class="barra-ferramentas">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise pelo CNAE"
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
      id="btn-incluir-cnae"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir CNAE</span>
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

Quando não há CNAEs cadastrados, a página exibe uma mensagem indicando que não há itens e instruções para adicionar novos:

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
        Para inserir novos registros você pode clicar em incluir CNAE.
      </p>

      <div class="estado-vazio-acoes">
        <button
          type="button"
          class="botao-acao botao-primario"
          id="btn-incluir-cnae-vazio"
        >
          <span class="texto">incluir CNAE</span>
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

### Área de Conteúdo (Com CNAEs)

Quando há CNAEs cadastrados, a página exibe uma tabela com a lista de códigos:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela-cnaes">
      <thead>
        <tr>
          <th class="coluna-codigo">Código</th>
          <th class="coluna-descricao">Descrição</th>
          <th class="coluna-acoes">Ações</th>
        </tr>
      </thead>
      <tbody>
        <!-- Exemplo de linha de CNAE -->
        <tr>
          <td class="coluna-codigo">6201-5/01</td>
          <td class="coluna-descricao">
            Desenvolvimento de programas de computador sob encomenda
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

.tabela-cnaes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-cnaes th,
.tabela-cnaes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-cnaes th {
  font-weight: 600;
  background-color: #fafafa;
  color: #333333;
}

.tabela-cnaes tr:hover {
  background-color: #f5f5f5;
}

.coluna-codigo {
  width: 20%;
}

.coluna-descricao {
  width: 60%;
}

.coluna-acoes {
  width: 20%;
  text-align: right;
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

O rodapé contém um link para a ajuda do sistema:

**Estrutura HTML:**

```html
<div class="rodape-container">
  <div class="rodape-ajuda">
    <p class="rodape-texto">Ficou com alguma dúvida?</p>
    <a href="#" class="rodape-link">Ajuda do Sistema ERP</a>
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

## Modal de Inclusão/Edição de CNAE

Quando o usuário clica em "Incluir CNAE" ou no botão de editar um CNAE existente, é exibido um modal para preencher as informações:

**Estrutura HTML:**

```html
<div class="modal" id="modal-cnae">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h3 class="modal-titulo">Incluir CNAE</h3>
      <button type="button" class="modal-fechar" id="btn-fechar-modal">
        ×
      </button>
    </div>

    <div class="modal-corpo">
      <div class="campo-grupo">
        <label for="codigo-cnae" class="campo-label">Código CNAE</label>
        <input
          type="text"
          id="codigo-cnae"
          name="codigo_cnae"
          class="campo-texto"
          placeholder="Ex: 6201-5/01"
        />
        <p class="campo-ajuda">Formato: 0000-0/00</p>
      </div>

      <div class="campo-grupo">
        <label for="descricao-cnae" class="campo-label">Descrição</label>
        <textarea
          id="descricao-cnae"
          name="descricao_cnae"
          class="campo-texto campo-textarea"
          placeholder="Descrição da atividade econômica"
        ></textarea>
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
        id="btn-salvar-cnae"
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
}

.modal-cabecalho {
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
  display: flex;
  justify-content: space-between;
  align-items: center;
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
}

.modal-rodape {
  padding: 16px;
  border-top: 1px solid #f0f0f0;
  display: flex;
  justify-content: flex-end;
  gap: 8px;
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

.campo-textarea {
  min-height: 100px;
  resize: vertical;
}

.campo-ajuda {
  font-size: 12px;
  color: #999999;
  margin: 4px 0 0 0;
}
```

## Interações JavaScript

### Pesquisa de CNAEs

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Pesquisa de CNAEs
  const campoPesquisa = document.getElementById("campo-pesquisa");
  const btnPesquisa = document.getElementById("btn-pesquisa");

  if (campoPesquisa && btnPesquisa) {
    btnPesquisa.addEventListener("click", function () {
      pesquisarCNAEs(campoPesquisa.value);
    });

    campoPesquisa.addEventListener("keypress", function (e) {
      if (e.key === "Enter") {
        pesquisarCNAEs(campoPesquisa.value);
      }
    });

    function pesquisarCNAEs(termo) {
      console.log("Pesquisando CNAEs:", termo);

      // Aqui seria implementada a lógica para filtrar os CNAEs
      // Por exemplo, usando uma requisição AJAX ou filtrando os elementos da tabela
    }
  }
});
```

### Abertura e Fechamento do Modal

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const btnIncluirCNAE = document.getElementById("btn-incluir-cnae");
  const btnIncluirCNAEVazio = document.getElementById("btn-incluir-cnae-vazio");
  const modal = document.getElementById("modal-cnae");
  const btnFecharModal = document.getElementById("btn-fechar-modal");
  const btnCancelarModal = document.getElementById("btn-cancelar-modal");

  // Função para abrir o modal
  function abrirModal() {
    if (modal) {
      modal.style.display = "flex";
      document.getElementById("codigo-cnae").focus();
    }
  }

  // Função para fechar o modal
  function fecharModal() {
    if (modal) {
      modal.style.display = "none";
      // Limpar os campos do formulário
      document.getElementById("codigo-cnae").value = "";
      document.getElementById("descricao-cnae").value = "";
    }
  }

  // Adicionar event listeners
  if (btnIncluirCNAE) {
    btnIncluirCNAE.addEventListener("click", abrirModal);
  }

  if (btnIncluirCNAEVazio) {
    btnIncluirCNAEVazio.addEventListener("click", abrirModal);
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

### Validação e Formatação do Código CNAE

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Validação e formatação do código CNAE
  const codigoCNAE = document.getElementById("codigo-cnae");

  if (codigoCNAE) {
    codigoCNAE.addEventListener("input", function () {
      // Remove caracteres não numéricos, exceto hífen e barra
      let valor = this.value.replace(/[^\d\-\/]/g, "");

      // Aplica a máscara 0000-0/00
      if (valor.length > 0) {
        // Adiciona o hífen após os primeiros 4 dígitos
        if (valor.length >= 4 && !valor.includes("-")) {
          valor = valor.substring(0, 4) + "-" + valor.substring(4);
        }

        // Adiciona a barra após o próximo dígito
        if (valor.length >= 6 && !valor.includes("/")) {
          valor = valor.substring(0, 6) + "/" + valor.substring(6);
        }

        // Limita o tamanho total
        if (valor.length > 9) {
          valor = valor.substring(0, 9);
        }
      }

      this.value = valor;
    });
  }
});
```

### Salvar CNAE

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Salvar CNAE
  const btnSalvarCNAE = document.getElementById("btn-salvar-cnae");

  if (btnSalvarCNAE) {
    btnSalvarCNAE.addEventListener("click", function () {
      const codigoCNAE = document.getElementById("codigo-cnae").value;
      const descricaoCNAE = document.getElementById("descricao-cnae").value;

      // Validação básica
      if (!codigoCNAE) {
        alert("O código CNAE é obrigatório.");
        return;
      }

      if (!descricaoCNAE) {
        alert("A descrição do CNAE é obrigatória.");
        return;
      }

      // Validar o formato do código CNAE
      const regexCNAE = /^\d{4}-\d\/\d{2}$/;
      if (!regexCNAE.test(codigoCNAE)) {
        alert("O código CNAE deve estar no formato 0000-0/00.");
        return;
      }

      // Criar o objeto com os dados
      const cnae = {
        codigo: codigoCNAE,
        descricao: descricaoCNAE,
      };

      // Salvar o CNAE
      salvarCNAE(cnae);
    });

    function salvarCNAE(cnae) {
      console.log("Salvando CNAE:", cnae);

      // Aqui seria implementada a lógica para salvar o CNAE no servidor
      // Por exemplo, usando uma requisição AJAX

      // Simula o salvamento bem-sucedido
      setTimeout(() => {
        alert("CNAE salvo com sucesso!");

        // Fechar o modal
        document.getElementById("btn-fechar-modal").click();

        // Recarregar a lista de CNAEs
        // Esta parte seria implementada de acordo com a lógica da aplicação
      }, 1000);
    }
  }
});
```

### Editar e Excluir CNAE

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Editar CNAE
  const botoesEditar = document.querySelectorAll(".botao-editar");

  botoesEditar.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter os dados do CNAE a partir da linha da tabela
      const linha = this.closest("tr");
      const codigo = linha.querySelector(".coluna-codigo").textContent;
      const descricao = linha.querySelector(".coluna-descricao").textContent;

      // Preencher o formulário
      document.getElementById("codigo-cnae").value = codigo;
      document.getElementById("descricao-cnae").value = descricao;

      // Alterar o título do modal
      document.querySelector(".modal-titulo").textContent = "Editar CNAE";

      // Abrir o modal
      document.getElementById("modal-cnae").style.display = "flex";
    });
  });

  // Excluir CNAE
  const botoesExcluir = document.querySelectorAll(".botao-excluir");

  botoesExcluir.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter o código do CNAE a partir da linha da tabela
      const linha = this.closest("tr");
      const codigo = linha.querySelector(".coluna-codigo").textContent;

      // Confirmar a exclusão
      if (confirm(`Deseja realmente excluir o CNAE "${codigo}"?`)) {
        // Excluir o CNAE
        excluirCNAE(codigo);
      }
    });
  });

  function excluirCNAE(codigo) {
    console.log("Excluindo CNAE:", codigo);

    // Aqui seria implementada a lógica para excluir o CNAE no servidor
    // Por exemplo, usando uma requisição AJAX

    // Simula a exclusão bem-sucedida
    setTimeout(() => {
      alert("CNAE excluído com sucesso!");

      // Recarregar a lista de CNAEs
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

  .tabela-cnaes th,
  .tabela-cnaes td {
    padding: 8px;
  }

  .coluna-codigo {
    width: 30%;
  }

  .coluna-descricao {
    width: 50%;
  }

  .coluna-acoes {
    width: 20%;
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

  .coluna-codigo {
    width: 40%;
  }

  .coluna-descricao {
    width: 40%;
  }

  .coluna-acoes {
    width: 20%;
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

1. **Acesso ao Cadastro de CNAEs**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Cadastro de CNAEs"
   - O sistema exibe a tela de cadastro de CNAEs

2. **Inclusão de Novo CNAE**:

   - O usuário clica no botão "Incluir CNAE"
   - O sistema exibe um modal para preenchimento dos dados
   - O usuário preenche o código e a descrição do CNAE
   - Clica em "Salvar" para confirmar
   - O sistema salva o CNAE e atualiza a lista

3. **Edição de CNAE Existente**:

   - O usuário clica no botão de edição de um CNAE na lista
   - O sistema exibe um modal com os dados preenchidos
   - O usuário altera os dados conforme necessário
   - Clica em "Salvar" para confirmar
   - O sistema atualiza o CNAE e a lista

4. **Exclusão de CNAE**:

   - O usuário clica no botão de exclusão de um CNAE na lista
   - O sistema exibe uma confirmação
   - O usuário confirma a exclusão
   - O sistema remove o CNAE e atualiza a lista

5. **Pesquisa de CNAEs**:

   - O usuário digita um termo no campo de pesquisa
   - Pressiona Enter ou clica no botão de pesquisa
   - O sistema filtra a lista de CNAEs de acordo com o termo

6. **Retorno à Lista de Configurações**:
   - O usuário clica em "Voltar" para retornar à lista de configurações
   - O sistema redireciona para a página de configurações

## Conclusão

O módulo "Cadastro de CNAEs" do ERP Revo apresenta uma interface para gerenciar os códigos CNAE que podem ser utilizados nos documentos fiscais de serviços. A página permite a inclusão, edição, exclusão e pesquisa de CNAEs, com uma interface intuitiva e responsiva.

A interface é bem estruturada, com uma barra de ferramentas contendo um campo de pesquisa e um botão para incluir novos CNAEs, e uma área de conteúdo que exibe a lista de CNAEs ou uma mensagem indicando que não há itens cadastrados.

O módulo utiliza modais para a inclusão e edição de CNAEs, com campos para o código e a descrição do CNAE. A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações.

Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma. A responsividade é bem implementada, garantindo uma boa experiência em dispositivos móveis e desktop.
