# Análise do Módulo Contratos - ERP Revo

## Estrutura Geral

O módulo "Contratos" do ERP Revo apresenta uma interface para gerenciamento de contratos de serviços. A página inicial exibe uma lista de contratos (vazia no estado atual) com opções de filtragem, pesquisa e ações para gerenciamento dos contratos.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Ações Principais

A seção superior contém o título da página e botões de ação principais:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Contratos</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Contratos de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <a
      href="/contratos/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-contrato"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir contrato</span>
    </a>

    <div class="dropdown">
      <button
        class="botao-acao botao-secundario dropdown-toggle"
        id="btn-mais-acoes"
      >
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu" id="menu-mais-acoes">
        <a href="#" class="dropdown-item" id="btn-exportar">Exportar</a>
        <a href="#" class="dropdown-item" id="btn-importar">Importar</a>
        <div class="dropdown-divider"></div>
        <a href="#" class="dropdown-item" id="btn-excluir-selecionados"
          >Excluir selecionados</a
        >
      </div>
    </div>
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

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: 1px solid #1890ff;
}

.botao-primario:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
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

.dropdown {
  position: relative;
}

.dropdown-toggle {
  display: inline-flex;
  align-items: center;
}

.dropdown-toggle .icone-seta-baixo {
  margin-left: 8px;
  font-size: 12px;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 1000;
  display: none;
  min-width: 160px;
  padding: 8px 0;
  margin: 4px 0 0;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.dropdown-menu.show {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.dropdown-divider {
  height: 1px;
  margin: 8px 0;
  background-color: #f0f0f0;
}
```

### Área de Pesquisa e Filtros

A seção de pesquisa e filtros permite buscar e filtrar contratos:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-dropdown">
      <button class="botao-filtros" id="btn-filtros">
        <span class="icone icone-filtro"></span>
        <span class="texto">filtros</span>
      </button>
    </div>
  </div>

  <div class="filtros-rapidos">
    <a href="#" class="filtro-item filtro-ativo" data-filtro="todos">
      <span class="texto">Todos</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="ativos">
      <span class="texto">Ativos</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="ativos-atraso">
      <span class="texto">Ativos c/ contas em atraso</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="demonstracao">
      <span class="texto">Demonstração</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="inativos">
      <span class="texto">Inativos</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="isentos">
      <span class="texto">Isentos</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="mais">
      <span class="texto">mais</span>
    </a>
  </div>

  <div class="filtros-aplicados">
    <div class="filtro-aplicado">
      <span class="filtro-aplicado-label">Situação:</span>
      <span class="filtro-aplicado-valor">Todos</span>
    </div>

    <div class="filtros-acoes">
      <button class="botao-acao botao-pequeno" id="btn-alterar-pesquisa">
        <span class="texto">Alterar pesquisa</span>
      </button>
      <button class="botao-acao botao-pequeno" id="btn-limpar-filtros">
        <span class="texto">Limpar filtros</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  padding: 0 24px 16px;
  background-color: #ffffff;
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
  border-right: none;
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
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa:hover {
  background-color: #f5f5f5;
}

.botao-pesquisa .icone {
  font-size: 16px;
  color: #666666;
}

.filtros-dropdown {
  margin-left: 8px;
}

.botao-filtros {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-filtros:hover {
  background-color: #f5f5f5;
}

.botao-filtros .icone {
  margin-right: 8px;
  font-size: 16px;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  overflow-x: auto;
  padding-bottom: 4px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  white-space: nowrap;
  margin-right: 8px;
}

.filtro-item:hover {
  background-color: #f5f5f5;
}

.filtro-ativo {
  background-color: #1890ff;
  color: white;
}

.filtro-ativo:hover {
  background-color: #40a9ff;
  color: white;
}

.filtros-aplicados {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 16px;
}

.filtro-aplicado {
  display: flex;
  align-items: center;
  font-size: 14px;
}

.filtro-aplicado-label {
  color: #666666;
  margin-right: 4px;
}

.filtro-aplicado-valor {
  color: #333333;
  font-weight: 500;
}

.filtros-acoes {
  display: flex;
  align-items: center;
  gap: 8px;
}

.botao-pequeno {
  padding: 4px 12px;
  font-size: 12px;
}
```

### Conteúdo Vazio

A área principal da página quando não há contratos cadastrados ou quando a pesquisa não retorna resultados:

**Estrutura HTML:**

```html
<div class="conteudo-vazio">
  <div class="conteudo-vazio-container">
    <div class="conteudo-vazio-ilustracao">
      <img
        src="/assets/images/ilustracao-vazio.png"
        alt="Nenhum resultado encontrado"
      />
    </div>
    <div class="conteudo-vazio-texto">
      <h2 class="conteudo-vazio-titulo">
        Sua pesquisa não retornou resultados.
      </h2>
      <p class="conteudo-vazio-descricao">
        Tente outras opções de pesquisa, situações ou remova os filtros.
      </p>
      <div class="conteudo-vazio-acoes">
        <button class="botao-acao" id="btn-alterar-pesquisa-vazio">
          <span class="texto">alterar pesquisa</span>
        </button>
        <button class="botao-acao" id="btn-limpar-filtros-vazio">
          <span class="texto">limpar filtros</span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-vazio {
  display: flex;
  justify-content: center;
  padding: 48px 24px;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.conteudo-vazio-container {
  display: flex;
  align-items: center;
  max-width: 600px;
}

.conteudo-vazio-ilustracao {
  margin-right: 24px;
}

.conteudo-vazio-ilustracao img {
  max-width: 150px;
  height: auto;
}

.conteudo-vazio-texto {
  flex: 1;
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
  margin: 0 0 16px;
}

.conteudo-vazio-acoes {
  display: flex;
  gap: 8px;
}
```

### Lista de Contratos

Embora não esteja visível na tela atual, a lista de contratos é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="contratos-lista-container">
  <table class="contratos-tabela">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-codigo">
          <div class="cabecalho-coluna">
            <span class="texto">Código</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-descricao">
          <div class="cabecalho-coluna">
            <span class="texto">Descrição</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-inicio">
          <div class="cabecalho-coluna">
            <span class="texto">Início</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-termino">
          <div class="cabecalho-coluna">
            <span class="texto">Término</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-valor">
          <div class="cabecalho-coluna">
            <span class="texto">Valor</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-situacao">
          <div class="cabecalho-coluna">
            <span class="texto">Situação</span>
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
      <!-- Aqui seriam listados os contratos -->
      <tr class="linha-contrato">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-contrato"
            data-id="1"
          />
        </td>
        <td class="coluna-codigo">001</td>
        <td class="coluna-cliente">Empresa ABC Ltda</td>
        <td class="coluna-descricao">Contrato de Manutenção Mensal</td>
        <td class="coluna-inicio">01/01/2025</td>
        <td class="coluna-termino">31/12/2025</td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-situacao">
          <span class="tag tag-ativo">Ativo</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao-tabela" title="Visualizar">
            <span class="icone icone-visualizar"></span>
          </button>
          <button class="botao-acao-tabela" title="Editar">
            <span class="icone icone-editar"></span>
          </button>
          <button class="botao-acao-tabela" title="Excluir">
            <span class="icone icone-excluir"></span>
          </button>
        </td>
      </tr>
      <tr class="linha-contrato">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-contrato"
            data-id="2"
          />
        </td>
        <td class="coluna-codigo">002</td>
        <td class="coluna-cliente">Empresa XYZ S.A.</td>
        <td class="coluna-descricao">Contrato de Suporte Técnico</td>
        <td class="coluna-inicio">15/02/2025</td>
        <td class="coluna-termino">14/02/2026</td>
        <td class="coluna-valor">R$ 2.800,00</td>
        <td class="coluna-situacao">
          <span class="tag tag-atraso">Ativo c/ atraso</span>
        </td>
        <td class="coluna-acoes">
          <button class="botao-acao-tabela" title="Visualizar">
            <span class="icone icone-visualizar"></span>
          </button>
          <button class="botao-acao-tabela" title="Editar">
            <span class="icone icone-editar"></span>
          </button>
          <button class="botao-acao-tabela" title="Excluir">
            <span class="icone icone-excluir"></span>
          </button>
        </td>
      </tr>
    </tbody>
  </table>

  <div class="paginacao">
    <div class="paginacao-info">
      <span class="texto">Mostrando 1-10 de 25 resultados</span>
    </div>
    <div class="paginacao-controles">
      <button class="botao-paginacao botao-paginacao-anterior" disabled>
        <span class="icone icone-anterior"></span>
      </button>
      <button
        class="botao-paginacao botao-paginacao-pagina botao-paginacao-ativo"
      >
        1
      </button>
      <button class="botao-paginacao botao-paginacao-pagina">2</button>
      <button class="botao-paginacao botao-paginacao-pagina">3</button>
      <button class="botao-paginacao botao-paginacao-proximo">
        <span class="icone icone-proximo"></span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.contratos-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
}

.contratos-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.contratos-tabela th,
.contratos-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.contratos-tabela th {
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
  color:
(Content truncated due to size limit. Use line ranges to read in chunks)
```
