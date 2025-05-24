# Análise do Módulo Extratos Bancários - ERP Revo

## Estrutura Geral

O módulo "Extratos Bancários" do ERP Revo apresenta uma interface para importação e gerenciamento de extratos bancários. A página inicial exibe um estado vazio quando não há itens cadastrados, com opções para importação de novos extratos e promoção da Conta Digital.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Ações e Filtros

A seção superior contém botões de ação e ferramentas de filtragem:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/financas" class="breadcrumb-item">Finanças</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Extratos Bancários</span>
  </div>

  <div class="acoes-principais">
    <a
      href="/extratos_bancarios/importar"
      class="botao-acao botao-primario"
      id="btn-importar-extrato"
    >
      <span class="icone icone-importar"></span>
      <span class="texto">Importar extrato bancário</span>
    </a>
  </div>

  <div class="banner-promocional">
    <div class="banner-conteudo">
      <div class="banner-icone">
        <img src="/assets/images/icone-conta-digital.png" alt="Conta Digital" />
      </div>
      <div class="banner-texto">
        <h3 class="banner-titulo">
          Deixe de fazer inúmeros uploads de extratos bancários
        </h3>
        <p class="banner-descricao">
          Com <strong>Conta Digital</strong>, você facilita sua rotina com a
          Conciliação Bancária automática, tudo dentro do ERP!
        </p>
      </div>
      <div class="banner-tag">
        <span class="tag-novo">Novo</span>
      </div>
    </div>
    <button class="botao-banner" id="btn-conhecer-conta-digital">
      conhecer conta digital
    </button>
  </div>

  <div class="filtros-container">
    <div class="pesquisa-container">
      <input
        type="text"
        class="campo-pesquisa"
        placeholder="Pesquise por nome"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>

    <div class="filtros-rapidos">
      <a href="#" class="filtro-item">
        <span class="texto">por período</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
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

.acoes-principais {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
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
  background-color: #f5f5f5;
  color: #333333;
  border: 1px solid #d9d9d9;
}

.botao-acao:hover {
  background-color: #e6e6e6;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
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

.banner-promocional {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f0f7ff;
  border-radius: 8px;
  padding: 16px 24px;
  margin-bottom: 16px;
}

.banner-conteudo {
  display: flex;
  align-items: center;
  flex: 1;
}

.banner-icone {
  margin-right: 16px;
}

.banner-icone img {
  width: 48px;
  height: 48px;
}

.banner-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 4px;
}

.banner-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.banner-tag {
  margin-left: 16px;
}

.tag-novo {
  display: inline-block;
  padding: 2px 8px;
  background-color: #f6ffed;
  color: #52c41a;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}

.botao-banner {
  background-color: #1890ff;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 8px 16px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease;
  white-space: nowrap;
  margin-left: 16px;
}

.botao-banner:hover {
  background-color: #40a9ff;
}

.filtros-container {
  margin-bottom: 16px;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
}

.campo-pesquisa {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px 0 0 4px;
  font-size: 14px;
  color: #333333;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 36px;
  background-color: #f5f5f5;
  border: 1px solid #d9d9d9;
  border-left: none;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa:hover {
  background-color: #e6e6e6;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 16px;
  font-size: 14px;
  color: #666666;
  background-color: #f5f5f5;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.filtro-item:hover {
  background-color: #e6e6e6;
}

.filtro-ativo {
  background-color: #e6f7ff;
  color: #1890ff;
}
```

### Conteúdo Vazio

A área principal da página quando não há itens cadastrados:

**Estrutura HTML:**

```html
<div class="conteudo-vazio">
  <div class="conteudo-vazio-container">
    <div class="conteudo-vazio-ilustracao">
      <img
        src="/assets/images/ilustracao-vazio.png"
        alt="Nenhum item cadastrado"
      />
    </div>
    <div class="conteudo-vazio-texto">
      <h2 class="conteudo-vazio-titulo">
        Você não possui nenhum item cadastrado.
      </h2>
      <p class="conteudo-vazio-descricao">
        Para inserir novos registros você pode clicar em importar extrato
        bancário.
      </p>
      <button class="botao-acao botao-primario" id="btn-importar-extrato-vazio">
        <span class="icone icone-importar"></span>
        <span class="texto">importar extrato bancário</span>
      </button>
    </div>
  </div>

  <div class="conteudo-vazio-ajuda">
    <p class="conteudo-vazio-ajuda-texto">Ficou com alguma dúvida?</p>
    <a href="#" class="conteudo-vazio-ajuda-link">Acesse a ajuda do Revo.</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  text-align: center;
}

.conteudo-vazio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 600px;
}

.conteudo-vazio-ilustracao {
  margin-bottom: 24px;
}

.conteudo-vazio-ilustracao img {
  max-width: 200px;
  height: auto;
}

.conteudo-vazio-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.conteudo-vazio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px;
}

.conteudo-vazio-ajuda {
  margin-top: 48px;
}

.conteudo-vazio-ajuda-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 8px;
}

.conteudo-vazio-ajuda-link {
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.conteudo-vazio-ajuda-link:hover {
  text-decoration: underline;
}
```

## Interações JavaScript

### Botões de Importação de Extrato

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botões de importação de extrato
  const botaoImportarExtrato = document.getElementById("btn-importar-extrato");
  const botaoImportarExtratoVazio = document.getElementById(
    "btn-importar-extrato-vazio"
  );

  function abrirFormularioImportacaoExtrato() {
    // Aqui seria implementada a lógica para abrir o formulário de importação de extrato
    window.location.href = "/extratos_bancarios/importar";
  }

  if (botaoImportarExtrato) {
    botaoImportarExtrato.addEventListener("click", function (e) {
      e.preventDefault();
      abrirFormularioImportacaoExtrato();
    });
  }

  if (botaoImportarExtratoVazio) {
    botaoImportarExtratoVazio.addEventListener("click", function (e) {
      e.preventDefault();
      abrirFormularioImportacaoExtrato();
    });
  }
});
```

### Botão Conhecer Conta Digital

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão conhecer conta digital
  const botaoConhecerContaDigital = document.getElementById(
    "btn-conhecer-conta-digital"
  );

  if (botaoConhecerContaDigital) {
    botaoConhecerContaDigital.addEventListener("click", function () {
      // Aqui seria implementada a lógica para redirecionar para a página da Conta Digital
      window.location.href = "/conta_digital";
    });
  }
});
```

### Filtros Rápidos

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Filtros rápidos
  const filtrosRapidos = document.querySelectorAll(".filtro-item");

  filtrosRapidos.forEach((filtro) => {
    filtro.addEventListener("click", function (e) {
      e.preventDefault();

      // Alterna o estado do filtro
      this.classList.toggle("filtro-ativo");

      // Aqui seria implementada a lógica de filtragem
      console.log("Filtro alterado:", this.textContent.trim());
    });
  });
});
```

## Formulário de Importação de Extrato

Embora não esteja visível na tela inicial, o formulário de importação de extrato é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Importar Extrato Bancário</h2>
  </div>

  <form class="formulario" id="form-importar-extrato">
    <div class="formulario-grupo">
      <label class="formulario-label" for="banco">Banco</label>
      <select
        class="formulario-campo formulario-select"
        id="banco"
        name="banco"
        required
      >
        <option value="">Selecione um banco</option>
        <option value="001">001 - Banco do Brasil</option>
        <option value="104">104 - Caixa Econômica Federal</option>
        <option value="237">237 - Bradesco</option>
        <option value="341">341 - Itaú</option>
        <option value="033">033 - Santander</option>
        <!-- Outros bancos -->
      </select>
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="conta">Conta</label>
      <select
        class="formulario-campo formulario-select"
        id="conta"
        name="conta"
        required
      >
        <option value="">Selecione uma conta</option>
        <!-- As opções serão carregadas dinamicamente com base no banco selecionado -->
      </select>
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="arquivo_extrato"
        >Arquivo de Extrato</label
      >
      <input
        type="file"
        class="formulario-campo formulario-arquivo"
        id="arquivo_extrato"
        name="arquivo_extrato"
        required
      />
      <p class="formulario-ajuda">Formatos aceitos: .OFX, .OFC, .QIF, .CSV</p>
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="data_inicial">Data Inicial</label>
      <input
        type="date"
        class="formulario-campo"
        id="data_inicial"
        name="data_inicial"
        required
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="data_final">Data Final</label>
      <input
        type="date"
        class="formulario-campo"
        id="data_final"
        name="data_final"
        required
      />
    </div>

    <div class="formulario-acoes">
      <button type="button" class="botao-acao" id="btn-cancelar">
        Cancelar
      </button>
      <button type="submit" class="botao-acao botao-primario" id="btn-importar">
        Importar
      </button>
    </div>
  </form>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.formulario-cabecalho {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.formulario {
  padding: 24px;
}

.formulario-grupo {
  margin-bottom: 16px;
}

.formulario-label {
  display: block;
  margin-bottom: 8px;
  font-size: 14px;
  color: #666666;
}

.formulario-campo {
  display: block;
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.formulario-campo:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.formulario-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.formulario-arquivo {
  padding: 8px 0;
}

.formulario-ajuda {
  font-size: 12px;
  color: #999999;
  margin: 4px 0 0;
}

.formulario-acoes {
  display: flex;
  justify-content: flex-end;
  margin-top: 24px;
  gap: 8px;
}
```

## Tela de Extratos Importados

Embora não esteja visível na tela inicial, a visualização de extratos importados é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="extratos-container">
  <div class="extratos-cabecalho">
    <h2 class="extratos-titulo">Extratos Bancários</h2>
  </div>

  <div class="extratos-tabela-container">
    <table class="extratos-tabela">
      <thead>
        <tr>
          <th class="coluna-banco">
            <div class="cabecalho-coluna">
              <span class="texto">Banco</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-conta">
            <div class="cabecalho-coluna">
              <span class="texto">Conta</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data-inicial">
            <div class="cabecalho-coluna">
              <span class="texto">Data Inicial</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data-final">
            <div class="cabecalho-coluna">
              <span class="texto">Data Final</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saldo-inicial">
            <div class="cabecalho-coluna">
              <span class="texto">Saldo Inicial</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-saldo-final">
            <div class="cabecalho-coluna">
              <span class="texto">Saldo Final</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data-importacao">
            <div class="cabecalho-coluna">
              <span class="texto">Data Importação</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes">
            <div class="cabecalho-coluna">
              <span class="texto">Ações</span>
            </div>
          </th>
        </tr>
      </thead>
      <tbody>
        (Content truncated due to size limit. Use line ranges to read in chunks)
      </tbody>
    </table>
  </div>
</div>
```
