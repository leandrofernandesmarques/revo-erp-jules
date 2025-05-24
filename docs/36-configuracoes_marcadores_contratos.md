# Análise do Módulo Configurações dos Marcadores nos Contratos - ERP Revo

## Estrutura Geral

O módulo "Configurações dos Marcadores nos Contratos" do ERP Revo apresenta uma interface para gerenciar os marcadores que podem ser utilizados nos contratos. A página exibe uma lista de marcadores cadastrados (ou uma mensagem indicando que não há itens cadastrados) e permite a inclusão de novos marcadores.

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
      >Configurações dos Marcadores nos Contratos</span
    >
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Configuração de marcadores</h1>
    <h2 class="subtitulo-pagina">Contratos</h2>
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
  margin-bottom: 4px;
}

.subtitulo-pagina {
  font-size: 16px;
  font-weight: 400;
  color: #666666;
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

A barra de ferramentas contém um campo de pesquisa e um botão para incluir novo marcador:

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
      id="btn-incluir-marcador"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir marcador</span>
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

Quando não há marcadores cadastrados, a página exibe uma mensagem indicando que não há itens e instruções para adicionar novos:

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
        Para inserir novos registros você pode clicar em incluir marcador.
      </p>

      <div class="estado-vazio-acoes">
        <button
          type="button"
          class="botao-acao botao-primario"
          id="btn-incluir-marcador-vazio"
        >
          <span class="texto">incluir marcador</span>
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

### Área de Conteúdo (Com Marcadores)

Quando há marcadores cadastrados, a página exibe uma tabela com a lista de marcadores:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela-marcadores">
      <thead>
        <tr>
          <th class="coluna-nome">Nome</th>
          <th class="coluna-cor">Cor</th>
          <th class="coluna-acoes">Ações</th>
        </tr>
      </thead>
      <tbody>
        <!-- Exemplo de linha de marcador -->
        <tr>
          <td class="coluna-nome">Urgente</td>
          <td class="coluna-cor">
            <div class="amostra-cor" style="background-color: #f5222d;"></div>
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

.tabela-marcadores {
  width: 100%;
  border-collapse: collapse;
}

.tabela-marcadores th,
.tabela-marcadores td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-marcadores th {
  font-weight: 600;
  background-color: #fafafa;
  color: #333333;
}

.tabela-marcadores tr:hover {
  background-color: #f5f5f5;
}

.coluna-nome {
  width: 60%;
}

.coluna-cor {
  width: 20%;
}

.coluna-acoes {
  width: 20%;
  text-align: right;
}

.amostra-cor {
  width: 24px;
  height: 24px;
  border-radius: 4px;
  display: inline-block;
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

## Modal de Inclusão/Edição de Marcador

Quando o usuário clica em "Incluir marcador" ou no botão de editar um marcador existente, é exibido um modal para preencher as informações:

**Estrutura HTML:**

```html
<div class="modal" id="modal-marcador">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h3 class="modal-titulo">Incluir marcador</h3>
      <button type="button" class="modal-fechar" id="btn-fechar-modal">
        ×
      </button>
    </div>

    <div class="modal-corpo">
      <div class="campo-grupo">
        <label for="nome-marcador" class="campo-label">Nome do marcador</label>
        <input
          type="text"
          id="nome-marcador"
          name="nome_marcador"
          class="campo-texto"
        />
      </div>

      <div class="campo-grupo">
        <label for="cor-marcador" class="campo-label">Cor do marcador</label>
        <div class="seletor-cor">
          <input
            type="color"
            id="cor-marcador"
            name="cor_marcador"
            class="campo-cor"
            value="#1890ff"
          />
          <span
            class="cor-preview"
            id="cor-preview"
            style="background-color: #1890ff;"
          ></span>
        </div>
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
        id="btn-salvar-marcador"
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
  width: 400px;
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

.seletor-cor {
  display: flex;
  align-items: center;
  gap: 8px;
}

.campo-cor {
  width: 40px;
  height: 40px;
  padding: 0;
  border: none;
  cursor: pointer;
}

.cor-preview {
  width: 24px;
  height: 24px;
  border-radius: 4px;
  display: inline-block;
}
```

## Interações JavaScript

### Pesquisa de Marcadores

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Pesquisa de marcadores
  const campoPesquisa = document.getElementById("campo-pesquisa");
  const btnPesquisa = document.getElementById("btn-pesquisa");

  if (campoPesquisa && btnPesquisa) {
    btnPesquisa.addEventListener("click", function () {
      pesquisarMarcadores(campoPesquisa.value);
    });

    campoPesquisa.addEventListener("keypress", function (e) {
      if (e.key === "Enter") {
        pesquisarMarcadores(campoPesquisa.value);
      }
    });

    function pesquisarMarcadores(termo) {
      console.log("Pesquisando marcadores:", termo);

      // Aqui seria implementada a lógica para filtrar os marcadores
      // Por exemplo, usando uma requisição AJAX ou filtrando os elementos da tabela
    }
  }
});
```

### Abertura e Fechamento do Modal

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const btnIncluirMarcador = document.getElementById("btn-incluir-marcador");
  const btnIncluirMarcadorVazio = document.getElementById(
    "btn-incluir-marcador-vazio"
  );
  const modal = document.getElementById("modal-marcador");
  const btnFecharModal = document.getElementById("btn-fechar-modal");
  const btnCancelarModal = document.getElementById("btn-cancelar-modal");

  // Função para abrir o modal
  function abrirModal() {
    if (modal) {
      modal.style.display = "flex";
      document.getElementById("nome-marcador").focus();
    }
  }

  // Função para fechar o modal
  function fecharModal() {
    if (modal) {
      modal.style.display = "none";
      // Limpar os campos do formulário
      document.getElementById("nome-marcador").value = "";
      document.getElementById("cor-marcador").value = "#1890ff";
      document.getElementById("cor-preview").style.backgroundColor = "#1890ff";
    }
  }

  // Adicionar event listeners
  if (btnIncluirMarcador) {
    btnIncluirMarcador.addEventListener("click", abrirModal);
  }

  if (btnIncluirMarcadorVazio) {
    btnIncluirMarcadorVazio.addEventListener("click", abrirModal);
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

### Seleção de Cor

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Seleção de cor
  const corMarcador = document.getElementById("cor-marcador");
  const corPreview = document.getElementById("cor-preview");

  if (corMarcador && corPreview) {
    corMarcador.addEventListener("input", function () {
      corPreview.style.backgroundColor = this.value;
    });
  }
});
```

### Salvar Marcador

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Salvar marcador
  const btnSalvarMarcador = document.getElementById("btn-salvar-marcador");

  if (btnSalvarMarcador) {
    btnSalvarMarcador.addEventListener("click", function () {
      const nomeMarcador = document.getElementById("nome-marcador").value;
      const corMarcador = document.getElementById("cor-marcador").value;

      // Validação básica
      if (!nomeMarcador) {
        alert("O nome do marcador é obrigatório.");
        return;
      }

      // Criar o objeto com os dados
      const marcador = {
        nome: nomeMarcador,
        cor: corMarcador,
      };

      // Salvar o marcador
      salvarMarcador(marcador);
    });

    function salvarMarcador(marcador) {
      console.log("Salvando marcador:", marcador);

      // Aqui seria implementada a lógica para salvar o marcador no servidor
      // Por exemplo, usando uma requisição AJAX

      // Simula o salvamento bem-sucedido
      setTimeout(() => {
        alert("Marcador salvo com sucesso!");

        // Fechar o modal
        document.getElementById("btn-fechar-modal").click();

        // Recarregar a lista de marcadores
        // Esta parte seria implementada de acordo com a lógica da aplicação
      }, 1000);
    }
  }
});
```

### Editar e Excluir Marcador

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Editar marcador
  const botoesEditar = document.querySelectorAll(".botao-editar");

  botoesEditar.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter os dados do marcador a partir da linha da tabela
      const linha = this.closest("tr");
      const nome = linha.querySelector(".coluna-nome").textContent;
      const cor = getComputedStyle(
        linha.querySelector(".amostra-cor")
      ).backgroundColor;

      // Converter RGB para HEX
      const hexCor = rgbToHex(cor);

      // Preencher o formulário
      document.getElementById("nome-marcador").value = nome;
      document.getElementById("cor-marcador").value = hexCor;
      document.getElementById("cor-preview").style.backgroundColor = hexCor;

      // Alterar o título do modal
      document.querySelector(".modal-titulo").textContent = "Editar marcador";

      // Abrir o modal
      document.getElementById("modal-marcador").style.display = "flex";
    });
  });

  // Excluir marcador
  const botoesExcluir = document.querySelectorAll(".botao-excluir");

  botoesExcluir.forEach(function (botao) {
    botao.addEventListener("click", function () {
      // Obter o nome do marcador a partir da linha da tabela
      const linha = this.closest("tr");
      const nome = linha.querySelector(".coluna-nome").textContent;

      // Confirmar a exclusão
      if (confirm(`Deseja realmente excluir o marcador "${nome}"?`)) {
        // Excluir o marcador
        excluirMarcador(nome);
      }
    });
  });

  function excluirMarcador(nome) {
    console.log("Excluindo marcador:", nome);

    // Aqui seria implementada a lógica para excluir o marcador no servidor
    // Por exemplo, usando uma requisição AJAX

    // Simula a exclusão bem-sucedida
    setTimeout(() => {
      alert("Marcador excluído com sucesso!");

      // Recarregar a lista de marcadores
      // Esta parte seria implementada de acordo com a lógica da aplicação
    }, 1000);
  }

  // Função auxiliar para converter RGB para HEX
  function rgbToHex(rgb) {
    // Extrai os valores R, G e B
    const rgbValues = rgb.match(/\d+/g);

    if (!rgbValues || rgbValues.length !== 3) {
      return "#000000";
    }

    // Converte para HEX
    return (
      "#" +
      rgbValues
        .map((x) => {
          const hex = parseInt(x).toString(16);
          return hex.length === 1 ? "0" + hex : hex;
        })
        .join("")
    );
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

  .tabela-marcadores th,
  .tabela-marcadores td {
    padding: 8px;
  }

  .coluna-nome {
    width: 50%;
  }

  .coluna-cor {
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

  .subtitulo-pagina {
    font-size: 14px;
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

1. **Acesso às Configurações dos Marcadores nos Contratos**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configurações dos marcadores nos contratos"
   - O sistema exibe a tela de configurações dos marcadores

2. **Inclusão de Novo Marcador**:

   - O usuário clica no botão "Incluir marcador"
   - O sistema exibe um modal para preenchimento dos dados
   - O usuário preenche o nome e seleciona a cor do marcador
   - Clica em "Salvar" para confirmar
   - O sistema salva o marcador e atualiza a lista

3. **Edição de Marcador Existente**:

   - O usuário clica no botão de edição de um marcador na lista
   - O sistema exibe um modal com os dados preenchidos
   - O usuário altera os dados conforme necessário
   - Clica em "Salvar" para confirmar
   - O sistema atualiza o marcador e a lista

4. **Exclusão de Marcador**:

   - O usuário clica no botão de exclusão de um marcador na lista
   - O sistema exibe uma confirmação
   - O usuário confirma a exclusão
   - O sistema remove o marcador e atualiza a lista

5. **Pesquisa de Marcadores**:

   - O usuário digita um termo no campo de pesquisa
   - Pressiona Enter ou clica no botão de pesquisa
   - O sistema filtra a lista de marcadores de acordo com o termo

6. **Retorno à Lista de Configurações**:
   - O usuário clica em "Voltar" para retornar à lista de configurações
   - O sistema redireciona para a página de configurações

## Conclusão

O módulo "Configurações dos Marcadores nos Contratos" do ERP Revo apresenta uma interface para gerenciar os marcadores que podem ser utilizados nos contratos. A página permite a inclusão, edição, exclusão e pesquisa de marcadores, com uma interface intuitiva e responsiva.

A interface é bem estruturada, com uma barra de ferramentas contendo um campo de pesquisa e um botão para incluir novos marcadores, e uma área de conteúdo que exibe a lista de marcadores ou uma mensagem indicando que não há itens cadastrados.

O módulo utiliza modais para a inclusão e edição de marcadores, com campos para o nome e a cor do marcador. A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações.

Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma. A responsividade é bem implementada, garantindo uma boa experiência em dispositivos móveis e desktop.
