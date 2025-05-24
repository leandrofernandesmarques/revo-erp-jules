# Análise do Módulo Configurações do Envio de Documentos - ERP Revo

## Estrutura Geral

O módulo "Configurações do Envio de Documentos" do ERP Revo apresenta uma interface para configurar os parâmetros relacionados ao envio de documentos por email, como NFSe (Nota Fiscal de Serviço Eletrônica) e Ordens de Serviço. A página permite personalizar os assuntos e mensagens padrão que serão utilizados nos emails enviados pelo sistema.

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
    <span class="breadcrumb-item-atual">Envio de documentos</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Configurações do envio de documentos</h1>
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

### Seção de Configuração da NFSe

Esta seção permite configurar o assunto e a mensagem padrão para o envio da Nota Fiscal de Serviço Eletrônica (NFSe):

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-cabecalho">
    <h2 class="secao-titulo">NFSe</h2>
  </div>

  <div class="secao-conteudo">
    <div class="campo-grupo">
      <label for="assunto-nfse" class="campo-label"
        >Assunto padrão para envio da NFSe</label
      >
      <input
        type="text"
        id="assunto-nfse"
        name="assunto_nfse"
        class="campo-texto"
        value="NFS-e"
      />
    </div>

    <div class="campo-grupo">
      <label for="mensagem-nfse" class="campo-label"
        >Mensagem padrão para envio da NFSe</label
      >
      <textarea
        id="mensagem-nfse"
        name="mensagem_nfse"
        class="campo-textarea"
        rows="8"
      >
[NOME_CLIENTE],

Segue o link para acesso ao RPS online. Qualquer dúvida, entrar em contato.</textarea
      >

      <div class="campo-acoes">
        <a href="#" class="link-acao" id="exibir-variaveis-nfse"
          >Exibir variáveis disponíveis</a
        >
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.secao-configuracao {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.secao-cabecalho {
  margin-bottom: 16px;
}

.secao-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.secao-conteudo {
  margin-bottom: 16px;
}

.campo-grupo {
  margin-bottom: 16px;
}

.campo-label {
  display: block;
  font-size: 14px;
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
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  resize: vertical;
  min-height: 100px;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
  background-color: #fff1f0;
}

.campo-textarea:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-acoes {
  margin-top: 8px;
  display: flex;
  justify-content: flex-end;
}

.link-acao {
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.link-acao:hover {
  text-decoration: underline;
}
```

### Seção de Configuração das Ordens de Serviço

Esta seção permite configurar o assunto e a mensagem padrão para o envio das Ordens de Serviço:

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-cabecalho">
    <h2 class="secao-titulo">Ordens de Serviço</h2>
  </div>

  <div class="secao-conteudo">
    <div class="campo-grupo">
      <label for="assunto-os" class="campo-label"
        >Assunto padrão para envio da ordem de serviço</label
      >
      <input
        type="text"
        id="assunto-os"
        name="assunto_os"
        class="campo-texto"
        value="Ordem de serviço"
      />
    </div>

    <div class="campo-grupo">
      <label for="mensagem-os" class="campo-label"
        >Mensagem padrão para envio da ordem de serviço</label
      >
      <textarea
        id="mensagem-os"
        name="mensagem_os"
        class="campo-textarea"
        rows="8"
      >
[NOME_CLIENTE],

Segue a ordem de serviço. Qualquer dúvida entrar em contato.</textarea
      >
    </div>
  </div>
</div>
```

### Botões de Ação

A seção inferior contém os botões para salvar ou cancelar as alterações:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <div class="acoes-grupo">
    <button type="button" class="botao-acao botao-secundario" id="btn-cancelar">
      <span class="texto">Cancelar</span>
    </button>

    <button type="button" class="botao-acao botao-primario" id="btn-salvar">
      <span class="texto">Salvar</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #f0f0f0;
  position: sticky;
  bottom: 0;
}

.acoes-grupo {
  display: flex;
  justify-content: flex-end;
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
```

## Interações JavaScript

### Exibir Variáveis Disponíveis

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Exibir variáveis disponíveis
  const exibirVariaveisNfse = document.getElementById("exibir-variaveis-nfse");

  if (exibirVariaveisNfse) {
    exibirVariaveisNfse.addEventListener("click", function (e) {
      e.preventDefault();

      // Lista de variáveis disponíveis
      const variaveis = [
        { nome: "[NOME_CLIENTE]", descricao: "Nome do cliente" },
        { nome: "[NUMERO_NOTA]", descricao: "Número da nota fiscal" },
        { nome: "[DATA_EMISSAO]", descricao: "Data de emissão da nota" },
        { nome: "[VALOR_TOTAL]", descricao: "Valor total da nota" },
        { nome: "[LINK_NOTA]", descricao: "Link para visualização da nota" },
      ];

      // Criar modal para exibir as variáveis
      const modal = document.createElement("div");
      modal.className = "modal";

      const modalConteudo = document.createElement("div");
      modalConteudo.className = "modal-conteudo";

      const modalCabecalho = document.createElement("div");
      modalCabecalho.className = "modal-cabecalho";

      const modalTitulo = document.createElement("h3");
      modalTitulo.className = "modal-titulo";
      modalTitulo.textContent = "Variáveis disponíveis";

      const modalFechar = document.createElement("button");
      modalFechar.className = "modal-fechar";
      modalFechar.textContent = "×";
      modalFechar.addEventListener("click", function () {
        document.body.removeChild(modal);
      });

      modalCabecalho.appendChild(modalTitulo);
      modalCabecalho.appendChild(modalFechar);

      const modalCorpo = document.createElement("div");
      modalCorpo.className = "modal-corpo";

      const tabela = document.createElement("table");
      tabela.className = "tabela-variaveis";

      const cabecalhoTabela = document.createElement("thead");
      const linhaCabecalho = document.createElement("tr");

      const colunaNome = document.createElement("th");
      colunaNome.textContent = "Variável";

      const colunaDescricao = document.createElement("th");
      colunaDescricao.textContent = "Descrição";

      linhaCabecalho.appendChild(colunaNome);
      linhaCabecalho.appendChild(colunaDescricao);
      cabecalhoTabela.appendChild(linhaCabecalho);

      const corpoTabela = document.createElement("tbody");

      variaveis.forEach(function (variavel) {
        const linha = document.createElement("tr");

        const celulaNome = document.createElement("td");
        celulaNome.textContent = variavel.nome;

        const celulaDescricao = document.createElement("td");
        celulaDescricao.textContent = variavel.descricao;

        linha.appendChild(celulaNome);
        linha.appendChild(celulaDescricao);

        corpoTabela.appendChild(linha);
      });

      tabela.appendChild(cabecalhoTabela);
      tabela.appendChild(corpoTabela);

      modalCorpo.appendChild(tabela);

      modalConteudo.appendChild(modalCabecalho);
      modalConteudo.appendChild(modalCorpo);

      modal.appendChild(modalConteudo);

      document.body.appendChild(modal);
    });
  }
});
```

### Salvar Configurações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão salvar
  const btnSalvar = document.getElementById("btn-salvar");

  if (btnSalvar) {
    btnSalvar.addEventListener("click", function () {
      // Coleta os valores dos campos
      const assuntoNfse = document.getElementById("assunto-nfse").value;
      const mensagemNfse = document.getElementById("mensagem-nfse").value;
      const assuntoOs = document.getElementById("assunto-os").value;
      const mensagemOs = document.getElementById("mensagem-os").value;

      // Validação básica
      if (!assuntoNfse || !mensagemNfse || !assuntoOs || !mensagemOs) {
        alert("Todos os campos são obrigatórios.");
        return;
      }

      // Cria o objeto com os dados
      const configuracoes = {
        assuntoNfse,
        mensagemNfse,
        assuntoOs,
        mensagemOs,
      };

      // Salva as configurações
      salvarConfiguracoes(configuracoes);
    });

    function salvarConfiguracoes(configuracoes) {
      console.log("Salvando configurações:", configuracoes);

      // Aqui seria implementada a lógica para salvar as configurações no servidor
      // Por exemplo, usando uma requisição AJAX

      // Simula o salvamento bem-sucedido
      setTimeout(() => {
        alert("Configurações salvas com sucesso!");
      }, 1000);
    }
  }
});
```

### Cancelar Alterações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão cancelar
  const btnCancelar = document.getElementById("btn-cancelar");

  if (btnCancelar) {
    btnCancelar.addEventListener("click", function () {
      // Confirma se o usuário deseja cancelar as alterações
      if (
        confirm(
          "Deseja cancelar as alterações? As modificações não salvas serão perdidas."
        )
      ) {
        // Redireciona para a página de configurações
        window.location.href = "/configuracoes";
      }
    });
  }
});
```

## Estilos Adicionais para o Modal de Variáveis

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
  width: 600px;
  max-width: 90%;
  max-height: 90%;
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
  overflow-y: auto;
}

.tabela-variaveis {
  width: 100%;
  border-collapse: collapse;
}

.tabela-variaveis th,
.tabela-variaveis td {
  padding: 8px 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-variaveis th {
  font-weight: 600;
  background-color: #fafafa;
}

.tabela-variaveis tr:last-child td {
  border-bottom: none;
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .cabecalho-acoes {
    flex-wrap: wrap;
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

  .acoes-grupo {
    width: 100%;
  }

  .acoes-grupo .botao-acao {
    flex: 1;
  }

  .modal-conteudo {
    width: 95%;
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

  .secao-titulo {
    font-size: 16px;
  }

  .tabela-variaveis th,
  .tabela-variaveis td {
    padding: 6px 8px;
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

1. **Acesso às Configurações do Envio de Documentos**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configurações do envio de documentos"
   - O sistema exibe a tela de configurações do envio de documentos

2. **Alteração das Configurações**:

   - O usuário edita os campos de assunto e mensagem padrão para NFSe e Ordens de Serviço
   - Clica em "Salvar" para aplicar as alterações
   - O sistema salva as configurações e exibe uma mensagem de sucesso

3. **Visualização das Variáveis Disponíveis**:

   - O usuário clica no link "Exibir variáveis disponíveis"
   - O sistema exibe um modal com a lista de variáveis que podem ser utilizadas nas mensagens
   - O usuário fecha o modal após consultar as variáveis

4. **Cancelamento das Alterações**:

   - O usuário clica em "Cancelar" para descartar as alterações
   - O sistema exibe uma confirmação
   - Se confirmado, o sistema redireciona para a página de configurações sem salvar as alterações

5. **Retorno à Lista de Configurações**:
   - O usuário clica em "Voltar" para retornar à lista de configurações
   - O sistema redireciona para a página de configurações

## Conclusão

O módulo "Configurações do Envio de Documentos" do ERP Revo apresenta uma interface para personalizar os assuntos e mensagens padrão que serão utilizados nos emails enviados pelo sistema, tanto para NFSe quanto para Ordens de Serviço.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo a visualização de variáveis disponíveis e o salvamento das configurações.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar a configuração do envio de documentos.
