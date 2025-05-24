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
        <!-- Aqui seriam listados os extratos importados -->
        <tr class="linha-extrato">
          <td class="coluna-banco">Banco do Brasil</td>
          <td class="coluna-conta">12345-6</td>
          <td class="coluna-data-inicial">01/05/2025</td>
          <td class="coluna-data-final">31/05/2025</td>
          <td class="coluna-saldo-inicial">1.500,00</td>
          <td class="coluna-saldo-final">2.300,00</td>
          <td class="coluna-data-importacao">02/06/2025</td>
          <td class="coluna-acoes">
            <button class="botao-acao-tabela" title="Visualizar">
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao-tabela" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

**Estilos CSS:**

```css
.extratos-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.extratos-cabecalho {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.extratos-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.extratos-tabela-container {
  overflow-x: auto;
}

.extratos-tabela {
  width: 100%;
  border-collapse: collapse;
}

.extratos-tabela th,
.extratos-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.extratos-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.cabecalho-coluna {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-coluna .icone-ordenar {
  margin-left: 4px;
  font-size: 12px;
  color: #d9d9d9;
}

.cabecalho-coluna:hover .icone-ordenar {
  color: #1890ff;
}

.linha-extrato {
  transition: background-color 0.2s ease;
}

.linha-extrato:hover {
  background-color: #f5f5f5;
}

.coluna-banco,
.coluna-conta {
  min-width: 120px;
}

.coluna-data-inicial,
.coluna-data-final,
.coluna-data-importacao {
  min-width: 100px;
}

.coluna-saldo-inicial,
.coluna-saldo-final {
  min-width: 100px;
  text-align: right;
}

.coluna-acoes {
  width: 100px;
  text-align: center;
  white-space: nowrap;
}

.botao-acao-tabela {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  background-color: transparent;
  border: none;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-acao-tabela:hover {
  background-color: #f5f5f5;
}

.botao-acao-tabela .icone {
  font-size: 16px;
  color: #666666;
}

.botao-acao-tabela:hover .icone {
  color: #1890ff;
}

.botao-acao-tabela:hover .icone-excluir {
  color: #f5222d;
}
```

## Tela de Detalhes do Extrato

Embora não esteja visível na tela inicial, a visualização detalhada de um extrato é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="detalhes-extrato-container">
  <div class="detalhes-extrato-cabecalho">
    <h2 class="detalhes-extrato-titulo">Detalhes do Extrato</h2>
    <button class="botao-acao" id="btn-voltar">
      <span class="icone icone-voltar"></span>
      <span class="texto">Voltar</span>
    </button>
  </div>

  <div class="detalhes-extrato-info">
    <div class="info-grupo">
      <span class="info-label">Banco:</span>
      <span class="info-valor">Banco do Brasil</span>
    </div>
    <div class="info-grupo">
      <span class="info-label">Conta:</span>
      <span class="info-valor">12345-6</span>
    </div>
    <div class="info-grupo">
      <span class="info-label">Período:</span>
      <span class="info-valor">01/05/2025 a 31/05/2025</span>
    </div>
    <div class="info-grupo">
      <span class="info-label">Saldo Inicial:</span>
      <span class="info-valor">R$ 1.500,00</span>
    </div>
    <div class="info-grupo">
      <span class="info-label">Saldo Final:</span>
      <span class="info-valor">R$ 2.300,00</span>
    </div>
  </div>

  <div class="detalhes-extrato-acoes">
    <button class="botao-acao" id="btn-conciliar">
      <span class="icone icone-conciliar"></span>
      <span class="texto">Conciliar</span>
    </button>
    <button class="botao-acao" id="btn-exportar">
      <span class="icone icone-exportar"></span>
      <span class="texto">Exportar</span>
    </button>
  </div>

  <div class="detalhes-extrato-tabela-container">
    <table class="detalhes-extrato-tabela">
      <thead>
        <tr>
          <th class="coluna-data">
            <div class="cabecalho-coluna">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-descricao">
            <div class="cabecalho-coluna">
              <span class="texto">Descrição</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-documento">
            <div class="cabecalho-coluna">
              <span class="texto">Documento</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-valor">
            <div class="cabecalho-coluna">
              <span class="texto">Valor</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-tipo">
            <div class="cabecalho-coluna">
              <span class="texto">Tipo</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-status">
            <div class="cabecalho-coluna">
              <span class="texto">Status</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr class="linha-transacao">
          <td class="coluna-data">03/05/2025</td>
          <td class="coluna-descricao">Pagamento de Fornecedor XYZ</td>
          <td class="coluna-documento">123456</td>
          <td class="coluna-valor valor-negativo">-500,00</td>
          <td class="coluna-tipo">Débito</td>
          <td class="coluna-status">
            <span class="tag tag-pendente">Pendente</span>
          </td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">10/05/2025</td>
          <td class="coluna-descricao">Recebimento Cliente ABC</td>
          <td class="coluna-documento">789012</td>
          <td class="coluna-valor valor-positivo">1.200,00</td>
          <td class="coluna-tipo">Crédito</td>
          <td class="coluna-status">
            <span class="tag tag-conciliado">Conciliado</span>
          </td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">15/05/2025</td>
          <td class="coluna-descricao">Tarifa Bancária</td>
          <td class="coluna-documento"></td>
          <td class="coluna-valor valor-negativo">-45,00</td>
          <td class="coluna-tipo">Débito</td>
          <td class="coluna-status">
            <span class="tag tag-pendente">Pendente</span>
          </td>
        </tr>
        <tr class="linha-transacao">
          <td class="coluna-data">22/05/2025</td>
          <td class="coluna-descricao">Transferência Recebida</td>
          <td class="coluna-documento">345678</td>
          <td class="coluna-valor valor-positivo">800,00</td>
          <td class="coluna-tipo">Crédito</td>
          <td class="coluna-status">
            <span class="tag tag-ignorado">Ignorado</span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

**Estilos CSS:**

```css
.detalhes-extrato-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.detalhes-extrato-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.detalhes-extrato-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.detalhes-extrato-info {
  display: flex;
  flex-wrap: wrap;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
  gap: 16px;
}

.info-grupo {
  display: flex;
  align-items: center;
  margin-right: 24px;
}

.info-label {
  font-size: 14px;
  color: #666666;
  margin-right: 8px;
}

.info-valor {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.detalhes-extrato-acoes {
  display: flex;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
  gap: 8px;
}

.detalhes-extrato-tabela-container {
  overflow-x: auto;
}

.detalhes-extrato-tabela {
  width: 100%;
  border-collapse: collapse;
}

.detalhes-extrato-tabela th,
.detalhes-extrato-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.detalhes-extrato-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.linha-transacao {
  transition: background-color 0.2s ease;
}

.linha-transacao:hover {
  background-color: #f5f5f5;
}

.coluna-data {
  width: 100px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-documento {
  width: 120px;
}

.coluna-valor {
  width: 100px;
  text-align: right;
}

.coluna-tipo {
  width: 100px;
}

.coluna-status {
  width: 120px;
}

.valor-positivo {
  color: #52c41a;
}

.valor-negativo {
  color: #f5222d;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-pendente {
  background-color: #fffbe6;
  color: #faad14;
}

.tag-conciliado {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-ignorado {
  background-color: #f5f5f5;
  color: #999999;
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .acoes-principais {
    flex-wrap: wrap;
  }

  .banner-promocional {
    flex-direction: column;
  }

  .banner-conteudo {
    margin-bottom: 16px;
  }

  .botao-banner {
    margin-left: 0;
  }

  .detalhes-extrato-info {
    flex-direction: column;
    align-items: flex-start;
  }

  .info-grupo {
    margin-right: 0;
    margin-bottom: 8px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .acoes-principais {
    justify-content: space-between;
  }

  .botao-acao {
    flex: 1;
    justify-content: center;
  }

  .banner-conteudo {
    flex-direction: column;
    text-align: center;
  }

  .banner-icone {
    margin-right: 0;
    margin-bottom: 16px;
  }

  .banner-tag {
    margin-left: 0;
    margin-top: 8px;
  }

  .botao-banner {
    margin-top: 16px;
  }

  .filtros-rapidos {
    overflow-x: auto;
    white-space: nowrap;
    padding-bottom: 8px;
  }

  .filtro-item {
    flex-shrink: 0;
  }

  .conteudo-vazio-ilustracao img {
    max-width: 150px;
  }

  .detalhes-extrato-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .detalhes-extrato-cabecalho .botao-acao {
    margin-top: 16px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .acoes-principais {
    flex-direction: column;
  }

  .botao-acao {
    width: 100%;
    margin-bottom: 8px;
  }

  .banner-titulo {
    font-size: 14px;
  }

  .banner-descricao {
    font-size: 12px;
  }

  .conteudo-vazio-titulo {
    font-size: 16px;
  }

  .conteudo-vazio-descricao {
    font-size: 13px;
  }

  .detalhes-extrato-acoes {
    flex-direction: column;
  }

  .detalhes-extrato-acoes .botao-acao {
    width: 100%;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Verde (sucesso): #52c41a
- Verde secundário: #73d13d
- Verde claro (background): #f6ffed
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
- Amarelo (alerta): #faad14
- Amarelo claro (background): #fffbe6
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
  - Títulos: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

## Fluxos de Navegação

1. **Importação de Extrato Bancário**:

   - O usuário acessa o módulo "Extratos Bancários"
   - Clica no botão "Importar extrato bancário" no topo da página ou no botão central na tela vazia
   - Um formulário é aberto para preenchimento dos dados do extrato
   - O usuário seleciona o banco, a conta, o arquivo de extrato e o período
   - O usuário clica em "Importar"
   - O sistema processa o arquivo e exibe o resultado
   - O extrato importado é adicionado à lista

2. **Visualização de Detalhes do Extrato**:

   - O usuário acessa o módulo "Extratos Bancários"
   - Visualiza a lista de extratos importados
   - Clica no botão de visualização de um extrato específico
   - O sistema exibe os detalhes do extrato, incluindo todas as transações
   - O usuário pode filtrar, ordenar e exportar as transações

3. **Conciliação Bancária**:

   - O usuário acessa os detalhes de um extrato
   - Clica no botão "Conciliar"
   - O sistema exibe uma interface para conciliação das transações com lançamentos financeiros
   - O usuário associa cada transação do extrato com um lançamento correspondente
   - O usuário salva as conciliações realizadas

4. **Conhecer Conta Digital**:
   - O usuário clica no botão "conhecer conta digital" no banner promocional
   - O sistema redireciona para a página da Conta Digital
   - O usuário pode obter mais informações sobre a funcionalidade e ativar a conta

## Conclusão

O módulo "Extratos Bancários" do ERP Revo apresenta uma interface para importação e gerenciamento de extratos bancários. A tela inicial exibe um estado vazio quando não há itens cadastrados, com opções claras para importação de novos extratos e promoção da Conta Digital.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo importar extratos, visualizar detalhes e realizar conciliações bancárias.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento financeiro do negócio, especificamente no que diz respeito ao controle e conciliação de extratos bancários.
