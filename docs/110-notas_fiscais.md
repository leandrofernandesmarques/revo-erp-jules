# Análise do Módulo Notas Fiscais - ERP Revo

## Estrutura Geral

O módulo "Notas Fiscais" do ERP Revo apresenta uma interface para gerenciamento de notas fiscais eletrônicas. A tela principal exibe uma lista de notas fiscais com opções de filtragem, pesquisa e ações para criar, autorizar e imprimir notas fiscais.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção, informações sobre o ambiente e botões de ação principais:

- Título "Notas Fiscais"
- Alerta de ambiente de testes
- Botão "Imprimir DANFEs"
- Botão "Autorizar pendentes"
- Botão "Incluir nota fiscal"
- Botão "Mais ações"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Notas Fiscais</h1>
  </div>

  <div class="alerta-ambiente">
    <div class="alerta-icone">
      <span class="icone icone-alerta"></span>
    </div>
    <div class="alerta-mensagem">
      Você está no ambiente para testes de notas fiscais.
      <a href="#" class="link-alterar-ambiente">alterar ambiente</a>
      para gerar notas com valor fiscal.
    </div>
  </div>

  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir-danfes">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir DANFEs</span>
    </button>
    <button class="botao botao-secundario" id="btn-autorizar-pendentes">
      <span class="icone icone-autorizar"></span>
      <span class="texto">Autorizar pendentes</span>
    </button>
    <a
      href="/notas_fiscais/novo"
      class="botao botao-primario"
      id="btn-incluir-nota"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
    </a>
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
  flex-direction: column;
  gap: 16px;
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

.alerta-ambiente {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  background-color: #fffbe6;
  border-radius: 4px;
  border: 1px solid #faad14;
}

.alerta-icone {
  margin-right: 12px;
  color: #faad14;
  font-size: 18px;
}

.alerta-mensagem {
  font-size: 14px;
  color: #666666;
}

.link-alterar-ambiente {
  color: #1890ff;
  text-decoration: none;
  margin: 0 4px;
}

.link-alterar-ambiente:hover {
  text-decoration: underline;
}

.acoes-container {
  display: flex;
  gap: 8px;
  align-self: flex-end;
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

A área de pesquisa e filtros permite buscar e filtrar notas fiscais:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise pelo nome do cliente"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
    <div class="dropdown-filtro-cliente">
      <button class="botao-filtro-cliente">
        Cliente
        <span class="icone icone-seta-baixo"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link">
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-calendario"></span>
      <span class="texto">data de emissão</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-link filtro-limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  gap: 8px;
  flex: 1;
  max-width: 500px;
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

.dropdown-filtro-cliente {
  position: relative;
}

.botao-filtro-cliente {
  display: flex;
  align-items: center;
  gap: 4px;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  cursor: pointer;
}

.botao-filtro-cliente:hover {
  background-color: #f5f5f5;
}

.filtros-container {
  display: flex;
  gap: 16px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
}

.filtro-link:hover {
  text-decoration: underline;
}

.filtro-link .icone {
  margin-right: 4px;
}

.filtro-limpar {
  color: #f5222d;
}
```

### Abas de Situação

As abas de situação permitem filtrar notas fiscais por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">
    <span class="indicador indicador-pendente"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-emitida"></span>
    <span class="texto">Emitidas</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-cancelada"></span>
    <span class="texto">Canceladas</span>
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

.indicador-emitida {
  background-color: #52c41a;
}

.indicador-cancelada {
  background-color: #f5222d;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há notas fiscais ou quando a pesquisa não retorna resultados:

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

### Tabela de Notas Fiscais

Quando houver notas fiscais, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-notas">
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
          <th class="coluna-serie">
            <div class="cabecalho-ordenavel">
              <span class="texto">Série</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data">
            <div class="cabecalho-ordenavel">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-cliente">
            <div class="cabecalho-ordenavel">
              <span class="texto">Cliente</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-documento">
            <div class="cabecalho-ordenavel">
              <span class="texto">CNPJ / CPF</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-valor">
            <div class="cabecalho-ordenavel">
              <span class="texto">Valor</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-chave">
            <div class="cabecalho-ordenavel">
              <span class="texto">Chave</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Notas fiscais serão adicionadas dinamicamente -->
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

.tabela-notas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-notas th,
.tabela-notas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-notas th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-notas tbody tr:hover {
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
.coluna-serie {
  width: 80px;
}

.coluna-data {
  width: 100px;
}

.coluna-documento {
  width: 150px;
}

.coluna-valor {
  width: 100px;
  text-align: right;
}

.coluna-chave {
  width: 200px;
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

## Formulário de Criação/Edição de Nota Fiscal

O formulário para criar ou editar notas fiscais é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-nota-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Nota Fiscal</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-cancelar">
        <span class="icone icone-cancelar"></span>
        <span class="texto">Cancelar</span>
      </button>
      <button class="bo
(Content truncated due to size limit. Use line ranges to read in chunks)
```
