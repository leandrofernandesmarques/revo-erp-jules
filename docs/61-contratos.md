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
  color: #d9d9d9;
}

.cabecalho-coluna:hover .icone-ordenar {
  color: #1890ff;
}

.linha-contrato {
  transition: background-color 0.2s ease;
}

.linha-contrato:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-codigo {
  width: 80px;
}

.coluna-cliente {
  min-width: 150px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-inicio,
.coluna-termino {
  width: 100px;
}

.coluna-valor {
  width: 120px;
  text-align: right;
}

.coluna-situacao {
  width: 120px;
}

.coluna-acoes {
  width: 120px;
  text-align: center;
  white-space: nowrap;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-ativo {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-atraso {
  background-color: #fff2e8;
  color: #fa8c16;
}

.tag-inativo {
  background-color: #f5f5f5;
  color: #999999;
}

.tag-demonstracao {
  background-color: #e6f7ff;
  color: #1890ff;
}

.tag-isento {
  background-color: #f9f0ff;
  color: #722ed1;
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

.paginacao {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.paginacao-info {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
}

.botao-paginacao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 32px;
  height: 32px;
  padding: 0 8px;
  margin: 0 4px;
  border-radius: 4px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease,
    border-color 0.2s ease;
}

.botao-paginacao:hover {
  background-color: #f5f5f5;
}

.botao-paginacao-ativo {
  background-color: #1890ff;
  border-color: #1890ff;
  color: white;
}

.botao-paginacao-ativo:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
}

.botao-paginacao[disabled] {
  background-color: #f5f5f5;
  border-color: #d9d9d9;
  color: #d9d9d9;
  cursor: not-allowed;
}
```

## Formulário de Inclusão/Edição de Contrato

Embora não esteja visível na tela inicial, o formulário de inclusão/edição de contrato é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Incluir Contrato</h2>
    <div class="formulario-acoes">
      <button class="botao-acao botao-secundario" id="btn-cancelar">
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao-acao botao-primario" id="btn-salvar">
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <form class="formulario" id="form-contrato">
      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Informações Gerais</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="codigo">Código</label>
            <input
              type="text"
              class="formulario-campo"
              id="codigo"
              name="codigo"
              placeholder="Automático"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-grande">
            <label class="formulario-label" for="cliente">Cliente *</label>
            <div class="formulario-campo-com-botao">
              <input
                type="text"
                class="formulario-campo"
                id="cliente"
                name="cliente"
                placeholder="Selecione um cliente"
                required
              />
              <button
                type="button"
                class="botao-campo"
                id="btn-selecionar-cliente"
              >
                <span class="icone icone-buscar"></span>
              </button>
            </div>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="descricao">Descrição *</label>
            <input
              type="text"
              class="formulario-campo"
              id="descricao"
              name="descricao"
              placeholder="Descrição do contrato"
              required
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data_inicio"
              >Data de Início *</label
            >
            <input
              type="date"
              class="formulario-campo"
              id="data_inicio"
              name="data_inicio"
              required
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data_termino"
              >Data de Término</label
            >
            <input
              type="date"
              class="formulario-campo"
              id="data_termino"
              name="data_termino"
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="valor">Valor *</label>
            <input
              type="text"
              class="formulario-campo"
              id="valor"
              name="valor"
              placeholder="0,00"
              required
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="situacao">Situação *</label>
            <select
              class="formulario-campo formulario-select"
              id="situacao"
              name="situacao"
              required
            >
              <option value="ativo">Ativo</option>
              <option value="inativo">Inativo</option>
              <option value="demonstracao">Demonstração</option>
              <option value="isento">Isento</option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Detalhes de Faturamento</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="periodicidade"
              >Periodicidade *</label
            >
            <select
              class="formulario-campo formulario-select"
              id="periodicidade"
              name="periodicidade"
              required
            >
              <option value="mensal">Mensal</option>
              <option value="bimestral">Bimestral</option>
              <option value="trimestral">Trimestral</option>
              <option value="semestral">Semestral</option>
              <option value="anual">Anual</option>
              <option value="unico">Pagamento Único</option>
            </select>
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="dia_vencimento"
              >Dia de Vencimento *</label
            >
            <input
              type="number"
              class="formulario-campo"
              id="dia_vencimento"
              name="dia_vencimento"
              min="1"
              max="31"
              placeholder="10"
              required
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="forma_pagamento"
              >Forma de Pagamento *</label
            >
            <select
              class="formulario-campo formulario-select"
              id="forma_pagamento"
              name="forma_pagamento"
              required
            >
              <option value="boleto">Boleto Bancário</option>
              <option value="cartao">Cartão de Crédito</option>
              <option value="pix">PIX</option>
              <option value="transferencia">Transferência Bancária</option>
              <option value="dinheiro">Dinheiro</option>
            </select>
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="conta_bancaria"
              >Conta Bancária</label
            >
            <select
              class="formulario-campo formulario-select"
              id="conta_bancaria"
              name="conta_bancaria"
            >
              <option value="">Selecione uma conta</option>
              <option value="1">
                Banco do Brasil - Ag. 1234-5 C/C 12345-6
              </option>
              <option value="2">Itaú - Ag. 6789-0 C/C 67890-1</option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Serviços Incluídos</h3>

        <div class="formulario-tabela-container">
          <table class="formulario-tabela" id="tabela-servicos">
            <thead>
              <tr>
                <th class="coluna-servico">Serviço</th>
                <th class="coluna-descricao">Descrição</th>
                <th class="coluna-quantidade">Qtde.</th>
                <th class="coluna-valor-unitario">Valor Unit.</th>
                <th class="coluna-valor-total">Valor Total</th>
                <th class="coluna-acoes">Ações</th>
              </tr>
            </thead>
            <tbody>
              <tr class="linha-servico">
                <td class="coluna-servico">
                  <div class="formulario-campo-com-botao">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="Selecione um serviço"
                    />
                    <button
                      type="button"
                      class="botao-campo"
                      id="btn-selecionar-servico"
                    >
                      <span class="icone icone-buscar"></span>
                    </button>
                  </div>
                </td>
                <td class="coluna-descricao">
                  <input
                    type="text"
                    class="formulario-campo"
                    placeholder="Descrição do serviço"
                  />
                </td>
                <td class="coluna-quantidade">
                  <input
                    type="number"
                    class="formulario-campo"
                    value="1"
                    min="1"
                  />
                </td>
                <td class="coluna-valor-unitario">
                  <input
                    type="text"
                    class="formulario-campo"
                    placeholder="0,00"
                  />
                </td>
                <td class="coluna-valor-total">
                  <input
                    type="text"
                    class="formulario-campo"
                    placeholder="0,00"
                    readonly
                  />
                </td>
                <td class="coluna-acoes">
                  <button
                    type="button"
                    class="botao-acao-tabela"
                    title="Remover"
                  >
                    <span class="icone icone-excluir"></span>
                  </button>
                </td>
              </tr>
            </tbody>
            <tfoot>
              <tr>
                <td colspan="6">
                  <button
                    type="button"
                    class="botao-acao botao-secundario"
                    id="btn-adicionar-servico"
                  >
                    <span class="icone icone-adicionar"></span>
                    <span class="texto">Adicionar Serviço</span>
                  </button>
                </td>
              </tr>
            </tfoot>
          </table>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Observações</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <textarea
              class="formulario-campo formulario-textarea"
              id="observacoes"
              name="observacoes"
              placeholder="Observações adicionais sobre o contrato"
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
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.formulario-acoes {
  display: flex;
  gap: 8px;
}

.formulario-conteudo {
  padding: 24px;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.formulario-secao {
  margin-bottom: 24px;
}

.formulario-secao-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 16px;
  padding-bottom: 8px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 16px;
}

.formulario-grupo {
  flex: 1;
  min-width: 200px;
}

.formulario-grupo-pequeno {
  flex: 0 0 120px;
}

.formulario-grupo-medio {
  flex: 0 0 calc(50% - 8px);
}

.formulario-grupo-grande {
  flex: 1;
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

.formulario-campo::placeholder {
  color: #999999;
}

.formulario-campo-com-botao {
  display: flex;
}

.formulario-campo-com-botao .formulario-campo {
  flex: 1;
  border-right: none;
  border-radius: 4px 0 0 4px;
}

.botao-campo {
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

.botao-campo:hover {
  background-color: #f5f5f5;
}

.botao-campo .icone {
  font-size: 16px;
  color: #666666;
}

.formulario-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.formulario-textarea {
  min-height: 100px;
  resize: vertical;
}

.formulario-tabela-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.formulario-tabela {
  width: 100%;
  border-collapse: collapse;
}

.formulario-tabela th,
.formulario-tabela td {
  padding: 12px 8px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.formulario-tabela .coluna-servico {
  width: 200px;
}

.formulario-tabela .coluna-descricao {
  min-width: 200px;
}

.formulario-tabela .coluna-quantidade {
  width: 80px;
}

.formulario-tabela .coluna-valor-unitario,
.formulario-tabela .coluna-valor-total {
  width: 120px;
}

.formulario-tabela .coluna-acoes {
  width: 60px;
  text-align: center;
}

.formulario-tabela tfoot td {
  padding: 16px 8px;
  border-bottom: none;
}
```

## Interações JavaScript

### Dropdown de Mais Ações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Dropdown de mais ações
  const btnMaisAcoes = document.getElementById("btn-mais-acoes");
  const menuMaisAcoes = document.getElementById("menu-mais-acoes");

  if (btnMaisAcoes && menuMaisAcoes) {
    btnMaisAcoes.addEventListener("click", function (e) {
      e.stopPropagation();
      menuMaisAcoes.classList.toggle("show");
    });

    // Fechar dropdown ao clicar fora
    document.addEventListener("click", function (e) {
      if (
        !btnMaisAcoes.contains(e.target) &&
        !menuMaisAcoes.contains(e.target)
      ) {
        menuMaisAcoes.classList.remove("show");
      }
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

      // Remove a classe ativa de todos os filtros
      filtrosRapidos.forEach((f) => f.classList.remove("filtro-ativo"));

      // Adiciona a classe ativa ao filtro clicado
      this.classList.add("filtro-ativo");

      // Atualiza o valor do filtro aplicado
      const filtroAplicadoValor = document.querySelector(
        ".filtro-aplicado-valor"
      );
      if (filtroAplicadoValor) {
        filtroAplicadoValor.textContent =
          this.querySelector(".texto").textContent;
      }

      // Aqui seria implementada a lógica para filtrar os contratos
      const filtroValor = this.getAttribute("data-filtro");
      console.log("Filtro aplicado:", filtroValor);
    });
  });
});
```

### Botões de Limpar Filtros e Alterar Pesquisa

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botões de limpar filtros e alterar pesquisa
  const btnLimparFiltros = document.getElementById("btn-limpar-filtros");
  const btnLimparFiltrosVazio = document.getElementById(
    "btn-limpar-filtros-vazio"
  );
  const btnAlterarPesquisa = document.getElementById("btn-alterar-pesquisa");
  const btnAlterarPesquisaVazio = document.getElementById(
    "btn-alterar-pesquisa-vazio"
  );

  function limparFiltros() {
    // Limpa o campo de pesquisa
    const campoPesquisa = document.getElementById("campo-pesquisa");
    if (campoPesquisa) {
      campoPesquisa.value = "";
    }

    // Ativa o filtro "Todos"
    const filtroTodos = document.querySelector(
      '.filtro-item[data-filtro="todos"]'
    );
    if (filtroTodos) {
      const event = new Event("click");
      filtroTodos.dispatchEvent(event);
    }

    // Aqui seria implementada a lógica para recarregar os contratos sem filtros
    console.log("Filtros limpos");
  }

  function alterarPesquisa() {
    // Foca no campo de pesquisa
    const campoPesquisa = document.getElementById("campo-pesquisa");
    if (campoPesquisa) {
      campoPesquisa.focus();
    }

    // Aqui seria implementada a lógica para abrir filtros avançados
    console.log("Alterar pesquisa");
  }

  if (btnLimparFiltros) {
    btnLimparFiltros.addEventListener("click", limparFiltros);
  }

  if (btnLimparFiltrosVazio) {
    btnLimparFiltrosVazio.addEventListener("click", limparFiltros);
  }

  if (btnAlterarPesquisa) {
    btnAlterarPesquisa.addEventListener("click", alterarPesquisa);
  }

  if (btnAlterarPesquisaVazio) {
    btnAlterarPesquisaVazio.addEventListener("click", alterarPesquisa);
  }
});
```

### Formulário de Contrato

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Formulário de contrato
  const formContrato = document.getElementById("form-contrato");

  if (formContrato) {
    // Botão salvar
    const btnSalvar = document.getElementById("btn-salvar");
    if (btnSalvar) {
      btnSalvar.addEventListener("click", function () {
        if (formContrato.checkValidity()) {
          // Aqui seria implementada a lógica para salvar o contrato
          console.log("Contrato salvo");

          // Redireciona para a lista de contratos
          window.location.href = "/contratos";
        } else {
          // Dispara a validação nativa do navegador
          formContrato.reportValidity();
        }
      });
    }

    // Botão cancelar
    const btnCancelar = document.getElementById("btn-cancelar");
    if (btnCancelar) {
      btnCancelar.addEventListener("click", function () {
        // Redireciona para a lista de contratos
        window.location.href = "/contratos";
      });
    }

    // Botão adicionar serviço
    const btnAdicionarServico = document.getElementById(
      "btn-adicionar-servico"
    );
    if (btnAdicionarServico) {
      btnAdicionarServico.addEventListener("click", function () {
        // Aqui seria implementada a lógica para adicionar uma nova linha de serviço
        const tabelaServicos = document.getElementById("tabela-servicos");
        if (tabelaServicos) {
          const tbody = tabelaServicos.querySelector("tbody");
          const linhaServico = tbody.querySelector(".linha-servico");
          const novaLinha = linhaServico.cloneNode(true);

          // Limpa os valores dos campos
          const campos = novaLinha.querySelectorAll(".formulario-campo");
          campos.forEach((campo) => {
            if (campo.type === "number") {
              campo.value = "1";
            } else {
              campo.value = "";
            }
          });

          // Adiciona a nova linha à tabela
          tbody.appendChild(novaLinha);

          // Adiciona evento para remover a linha
          const btnRemover = novaLinha.querySelector(".botao-acao-tabela");
          if (btnRemover) {
            btnRemover.addEventListener("click", function () {
              tbody.removeChild(novaLinha);
            });
          }
        }
      });
    }

    // Cálculo automático do valor total
    const tabelaServicos = document.getElementById("tabela-servicos");
    if (tabelaServicos) {
      tabelaServicos.addEventListener("input", function (e) {
        const target = e.target;
        if (
          target.classList.contains("formulario-campo") &&
          (target.closest(".coluna-quantidade") ||
            target.closest(".coluna-valor-unitario"))
        ) {
          const linha = target.closest(".linha-servico");
          const quantidade =
            parseFloat(
              linha.querySelector(".coluna-quantidade .formulario-campo").value
            ) || 0;
          const valorUnitario =
            parseFloat(
              linha
                .querySelector(".coluna-valor-unitario .formulario-campo")
                .value.replace(",", ".")
            ) || 0;
          const valorTotal = quantidade * valorUnitario;

          linha.querySelector(".coluna-valor-total .formulario-campo").value =
            valorTotal.toFixed(2).replace(".", ",");
        }
      });
    }
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .cabecalho-acoes {
    flex-wrap: wrap;
  }

  .formulario-grupo-medio {
    flex: 1 0 100%;
  }

  .formulario-tabela .coluna-servico {
    width: 150px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .cabecalho-acoes {
    flex-direction: column;
    align-items: stretch;
  }

  .cabecalho-acoes .botao-acao {
    margin-bottom: 8px;
  }

  .pesquisa-container {
    flex-direction: column;
  }

  .filtros-dropdown {
    margin-left: 0;
    margin-top: 8px;
    width: 100%;
  }

  .botao-filtros {
    width: 100%;
  }

  .filtros-aplicados {
    flex-direction: column;
    align-items: flex-start;
  }

  .filtros-acoes {
    margin-top: 8px;
    width: 100%;
  }

  .filtros-acoes .botao-acao {
    flex: 1;
  }

  .conteudo-vazio-container {
    flex-direction: column;
    text-align: center;
  }

  .conteudo-vazio-ilustracao {
    margin-right: 0;
    margin-bottom: 16px;
  }

  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 16px;
    width: 100%;
  }

  .formulario-acoes .botao-acao {
    flex: 1;
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

  .filtros-rapidos {
    flex-wrap: nowrap;
    overflow-x: auto;
    padding-bottom: 8px;
  }

  .filtro-item {
    flex-shrink: 0;
  }

  .paginacao {
    flex-direction: column;
    align-items: flex-start;
  }

  .paginacao-info {
    margin-bottom: 8px;
  }

  .paginacao-controles {
    width: 100%;
    justify-content: center;
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
- Laranja (alerta): #fa8c16
- Laranja claro (background): #fff2e8
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
- Roxo: #722ed1
- Roxo claro (background): #f9f0ff
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

1. **Listagem de Contratos**:

   - O usuário acessa o módulo "Contratos"
   - Visualiza a lista de contratos cadastrados
   - Pode filtrar os contratos por situação (Todos, Ativos, Ativos c/ contas em atraso, Demonstração, Inativos, Isentos)
   - Pode pesquisar contratos por cliente
   - Pode ordenar a lista por qualquer coluna
   - Pode navegar entre as páginas da lista

2. **Inclusão de Contrato**:

   - O usuário clica no botão "Incluir contrato"
   - Preenche os dados do formulário
   - Adiciona os serviços incluídos no contrato
   - Clica em "Salvar"
   - O sistema valida os dados e salva o contrato
   - O usuário é redirecionado para a lista de contratos

3. **Edição de Contrato**:

   - O usuário clica no botão de edição de um contrato na lista
   - O sistema carrega os dados do contrato no formulário
   - O usuário altera os dados necessários
   - Clica em "Salvar"
   - O sistema valida os dados e atualiza o contrato
   - O usuário é redirecionado para a lista de contratos

4. **Exclusão de Contrato**:

   - O usuário clica no botão de exclusão de um contrato na lista
   - O sistema exibe uma confirmação
   - O usuário confirma a exclusão
   - O sistema exclui o contrato
   - A lista de contratos é atualizada

5. **Impressão de Contratos**:
   - O usuário clica no botão "Imprimir"
   - O sistema gera um relatório com os contratos filtrados
   - O relatório é exibido em uma nova janela para impressão

## Conclusão

O módulo "Contratos" do ERP Revo apresenta uma interface para gerenciamento de contratos de serviços. A página inicial exibe uma lista de contratos com opções de filtragem, pesquisa e ações para gerenciamento.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, incluir, editar e excluir contratos.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações de contratos. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento de contratos de serviços.
