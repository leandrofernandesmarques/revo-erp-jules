# Análise do Módulo Expedição - ERP Revo

## Estrutura Geral

O módulo "Expedição" do ERP Revo apresenta uma interface para gerenciamento de envios e expedição de mercadorias. A tela principal exibe uma área de pesquisa, filtros, abas de situação e uma lista de expedições quando disponíveis.

## Componentes Principais

### Alerta de Configuração

O módulo exibe um alerta quando os serviços dos correios não estão configurados:

**Estrutura HTML:**

```html
<div class="alerta-configuracao">
  <div class="alerta-mensagem">
    Os serviços dos correios ainda não foram configurados. Para configurar
    acesse as configurações das
    <a href="/configuracoes/formas-envio" class="link-configuracao"
      >Formas de Envio</a
    >.
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-configuracao {
  display: flex;
  align-items: center;
  padding: 12px 24px;
  background-color: #fffbe6;
  border-bottom: 1px solid #faad14;
}

.alerta-mensagem {
  font-size: 14px;
  color: #666666;
}

.link-configuracao {
  color: #1890ff;
  text-decoration: none;
  font-weight: 500;
}

.link-configuracao:hover {
  text-decoration: underline;
}
```

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Expedição</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-integrar-intelipost">
      <span class="icone icone-integrar"></span>
      <span class="texto">Integrar com a Intelipost</span>
    </button>
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <button class="botao botao-primario" id="btn-incluir-expedicao">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir expedição</span>
    </button>
    <div class="dropdown">
      <button class="botao botao-secundario" id="btn-mais-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item">Exportar</a>
        <a href="#" class="dropdown-item">Importar</a>
        <a href="#" class="dropdown-item">Configurações</a>
      </div>
    </div>
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
  border-bottom: 1px solid #f0f0f0;
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
  text-decoration: none;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao .icone {
  margin-right: 8px;
  font-size: 16px;
}

.dropdown {
  position: relative;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 10;
  min-width: 160px;
  padding: 8px 0;
  margin-top: 4px;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: none;
}

.dropdown.ativo .dropdown-menu {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
}
```

### Área de Pesquisa e Filtros

A área de pesquisa e filtros permite buscar e filtrar expedições:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por nº, pedido, nota fiscal ou destinatário"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <div class="filtro-grupo">
      <a href="#" class="filtro-link filtro-agrupamento">
        <span class="icone icone-agrupamento"></span>
        <span class="texto">Agrupamentos</span>
      </a>
      <a href="#" class="filtro-link filtro-forma-envio">
        <span class="texto">por forma de envio</span>
      </a>
    </div>
    <div class="filtro-grupo">
      <a href="#" class="filtro-link filtro-mes-atual">
        <span class="icone icone-calendario"></span>
        <span class="texto">Maio</span>
      </a>
      <a href="#" class="filtro-link filtro-limpar">
        <span class="icone icone-limpar"></span>
        <span class="texto">limpar filtros</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  gap: 8px;
  width: 100%;
}

.campo-pesquisa {
  position: relative;
  flex: 1;
}

.input-pesquisa {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.input-pesquisa:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #999999;
  cursor: pointer;
}

.filtros-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
}

.filtro-grupo {
  display: flex;
  align-items: center;
  gap: 8px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-link:hover {
  background-color: #f0f5ff;
}

.filtro-agrupamento,
.filtro-forma-envio,
.filtro-mes-atual {
  background-color: #f0f5ff;
  border: 1px solid #d6e4ff;
}

.filtro-limpar {
  color: #f5222d;
}

.filtro-link .icone {
  margin-right: 8px;
}
```

### Abas de Situação

As abas de situação permitem filtrar expedições por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">
    <span class="indicador indicador-pendente"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-concluida"></span>
    <span class="texto">Concluídas</span>
  </a>
</div>
```

**Estilos CSS:**

```css
.abas-container {
  display: flex;
  align-items: center;
  padding: 0 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  overflow-x: auto;
}

.aba {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  color: #666666;
  text-decoration: none;
  font-size: 14px;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
  white-space: nowrap;
}

.aba:hover {
  color: #1890ff;
}

.aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.indicador {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-pendente {
  background-color: #faad14;
}

.indicador-concluida {
  background-color: #52c41a;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há expedições ou quando a pesquisa não retorna resultados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <h2 class="titulo-vazio">Sua pesquisa não retornou resultados.</h2>
      <p class="texto-vazio">
        Tente outras opções de pesquisa, situações ou remova os filtros.
      </p>
    </div>

    <div class="ilustracao-vazio">
      <img
        src="/assets/images/ilustracao-sem-resultados.svg"
        alt="Sem resultados"
      />
    </div>

    <div class="acoes-vazio">
      <button class="botao botao-primario" id="btn-alterar-pesquisa">
        <span class="texto">alterar pesquisa</span>
      </button>
      <button class="botao botao-secundario" id="btn-limpar-filtros">
        <span class="texto">limpar filtros</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  flex: 1;
  padding: 24px;
  background-color: #f5f5f5;
  overflow: auto;
}

.conteudo-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 600px;
  margin: 0 auto;
  padding: 32px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.mensagem-vazio {
  text-align: center;
  margin-bottom: 24px;
}

.titulo-vazio {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.texto-vazio {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.ilustracao-vazio {
  margin-bottom: 24px;
}

.ilustracao-vazio img {
  max-width: 100%;
  height: auto;
  max-height: 200px;
}

.acoes-vazio {
  display: flex;
  gap: 12px;
}
```

### Tabela de Expedições

Quando houver expedições, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-expedicoes">
      <thead>
        <tr>
          <th class="coluna-selecao">
            <input type="checkbox" class="checkbox-selecionar-todos" />
          </th>
          <th class="coluna-situacao"></th>
          <th class="coluna-numero">
            <div class="cabecalho-ordenavel">
              <span class="texto">Número</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data">
            <div class="cabecalho-ordenavel">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-pedido">
            <div class="cabecalho-ordenavel">
              <span class="texto">Pedido</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-nota">
            <div class="cabecalho-ordenavel">
              <span class="texto">Nota Fiscal</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-destinatario">
            <div class="cabecalho-ordenavel">
              <span class="texto">Destinatário</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-forma-envio">
            <div class="cabecalho-ordenavel">
              <span class="texto">Forma de Envio</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-rastreamento">
            <div class="cabecalho-ordenavel">
              <span class="texto">Rastreamento</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Expedições serão adicionadas dinamicamente -->
      </tbody>
    </table>

    <div class="paginacao">
      <div class="paginacao-info">
        <span class="texto">Exibindo 0 de 0 registros</span>
      </div>
      <div class="paginacao-controles">
        <button class="botao-paginacao" disabled>
          <span class="icone icone-primeira-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-pagina-anterior"></span>
        </button>
        <span class="paginacao-pagina">Página 1 de 1</span>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-proxima-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-ultima-pagina"></span>
        </button>
      </div>
      <div class="paginacao-por-pagina">
        <span class="texto">Itens por página:</span>
        <select class="select-por-pagina">
          <option value="10">10</option>
          <option value="25">25</option>
          <option value="50">50</option>
          <option value="100">100</option>
        </select>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-tabela {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.tabela-expedicoes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-expedicoes th,
.tabela-expedicoes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-expedicoes th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-expedicoes tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-situacao {
  width: 40px;
  text-align: center;
}

.coluna-numero,
.coluna-data,
.coluna-pedido,
.coluna-nota {
  width: 100px;
}

.coluna-rastreamento {
  width: 150px;
}

.coluna-acoes {
  width: 80px;
  text-align: center;
}

.cabecalho-ordenavel {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-ordenavel .icone {
  margin-left: 4px;
  font-size: 12px;
  opacity: 0.5;
}

.cabecalho-ordenavel:hover .icone {
  opacity: 1;
}

.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
}

.paginacao-info,
.paginacao-pagina {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
  gap: 8px;
}

.botao-paginacao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: white;
  color: #666666;
  cursor: pointer;
}

.botao-paginacao:hover:not(:disabled) {
  background-color: #f5f5f5;
}

.botao-paginacao:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.paginacao-por-pagina {
  display: flex;
  align-items: center;
  gap: 8px;
}

.paginacao-por-pagina .texto {
  font-size: 14px;
  color: #666666;
}

.select-por-pagina {
  padding: 4px 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}
```

## Formulário de Criação/Edição de Expedição

O formulário para criar ou editar expedições é exibido em uma nova página ou modal:

**Estrutura HTML:**

```html
<div class="formulario-expedicao-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Expedição</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-cancelar">
        <span class="icone icone-cancelar"></span>
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao botao-primario" id="btn-salvar">
        <span class="icone icone-salvar"></span>
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <div class="formulario-secao">
      <h2 class="secao-titulo">Informações Gerais</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="data_expedicao" class="formulario-label">Data de Expedição</label>
          <input
(Content truncated due to size limit. Use line ranges to read in chunks)
```
