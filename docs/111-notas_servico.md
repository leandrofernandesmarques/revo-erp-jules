# Análise do Módulo Notas de Serviço - ERP Revo

## Estrutura Geral

O módulo "Notas de Serviço" do ERP Revo apresenta uma interface para gerenciamento de notas fiscais de serviço. A página exibe uma lista de notas fiscais com opções de filtragem, pesquisa e ações para gerenciamento.

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
    <span class="breadcrumb-item-atual">Notas de Serviço</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Notas de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <button class="botao-acao botao-secundario" id="btn-enviar-pendentes">
      <span class="icone icone-enviar"></span>
      <span class="texto">Enviar pendentes</span>
    </button>

    <a
      href="/notas_servico/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-nota"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
    </a>
  </div>

  <div class="cabecalho-alerta">
    <div class="alerta alerta-info">
      <span class="alerta-icone icone-info"></span>
      <span class="alerta-texto"
        >A nota de serviço ainda não foi configurada. Para configurar
        acesse</span
      >
      <a href="/configuracao_nfse" class="alerta-link"
        >Configuração da Nota Fiscal Eletrônica de Serviços (NFS-e)</a
      >
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

.cabecalho-alerta {
  margin-bottom: 16px;
}

.alerta {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-radius: 4px;
  font-size: 14px;
}

.alerta-info {
  background-color: #e6f7ff;
  border: 1px solid #91d5ff;
}

.alerta-icone {
  margin-right: 8px;
  font-size: 16px;
  color: #1890ff;
}

.alerta-texto {
  color: #333333;
}

.alerta-link {
  color: #1890ff;
  text-decoration: none;
  margin-left: 4px;
}

.alerta-link:hover {
  text-decoration: underline;
}
```

### Área de Pesquisa e Filtros

A seção de pesquisa e filtros permite buscar e filtrar notas fiscais:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente ou número"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-adicionais">
      <a href="#" class="filtro-adicional" id="filtro-periodo">
        <span class="icone icone-calendario"></span>
        <span class="texto">Últimos 30 dias</span>
      </a>

      <a href="#" class="filtro-adicional" id="filtro-limpar">
        <span class="icone icone-limpar"></span>
        <span class="texto">limpar filtros</span>
      </a>
    </div>
  </div>

  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="todas">
      <span class="texto">Todas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="pendentes">
      <span class="icone icone-status icone-status-pendente"></span>
      <span class="texto">Pendentes</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="emitidas">
      <span class="icone icone-status icone-status-emitida"></span>
      <span class="texto">Emitidas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="canceladas">
      <span class="icone icone-status icone-status-cancelada"></span>
      <span class="texto">Canceladas</span>
    </a>
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

.filtros-adicionais {
  display: flex;
  align-items: center;
  margin-left: 16px;
  gap: 8px;
}

.filtro-adicional {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-adicional:hover {
  background-color: #f5f5f5;
}

.filtro-adicional .icone {
  margin-right: 8px;
  font-size: 14px;
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

.icone-status {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 8px;
}

.icone-status-pendente {
  background-color: #fa8c16;
}

.icone-status-emitida {
  background-color: #52c41a;
}

.icone-status-cancelada {
  background-color: #f5222d;
}
```

### Área de Conteúdo (Sem Resultados)

A área de conteúdo exibe uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="sem-resultados">
    <div class="sem-resultados-imagem">
      <img src="/assets/images/sem-resultados.svg" alt="Sem resultados" />
    </div>
    <h2 class="sem-resultados-titulo">Sua pesquisa não retornou resultados.</h2>
    <p class="sem-resultados-texto">
      Tente outras opções de pesquisa, situações ou remova os filtros.
    </p>
    <div class="sem-resultados-acoes">
      <button class="botao-acao botao-secundario" id="btn-alterar-pesquisa">
        <span class="texto">alterar pesquisa</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-limpar-filtros">
        <span class="texto">limpar filtros</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  background-color: #ffffff;
}

.sem-resultados {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  border: 1px solid #f0f0f0;
  border-radius: 4px;
  text-align: center;
}

.sem-resultados-imagem {
  margin-bottom: 24px;
}

.sem-resultados-imagem img {
  max-width: 200px;
}

.sem-resultados-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.sem-resultados-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px;
}

.sem-resultados-acoes {
  display: flex;
  gap: 8px;
}
```

### Lista de Notas Fiscais

Embora não esteja visível na tela atual devido à ausência de resultados, a lista de notas fiscais é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="notas-lista-container">
  <table class="notas-tabela">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-numero">
          <div class="cabecalho-coluna">
            <span class="texto">Número</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data">
          <div class="cabecalho-coluna">
            <span class="texto">Data</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
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
      <!-- Exemplo de linha de nota fiscal -->
      <tr class="linha-nota">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-nota"
            data-id="12345"
          />
        </td>
        <td class="coluna-numero">
          <a href="/notas_servico/visualizar/12345" class="link-numero"
            >12345</a
          >
        </td>
        <td class="coluna-data">16/05/2025</td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-situacao">
          <span class="tag tag-pendente">Pendente</span>
        </td>
        <td class="coluna-acoes">
          <div class="acoes-grupo">
            <button class="botao-acao-tabela" title="Visualizar">
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao-tabela" title="Editar">
              <span class="icone icone-editar"></span>
            </button>
            <button class="botao-acao-tabela" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
            <button class="botao-acao-tabela" title="Enviar">
              <span class="icone icone-enviar"></span>
            </button>
          </div>
        </td>
      </tr>
    </tbody>
  </table>

  <div class="resumo-rodape">
    <div class="resumo-item">
      <span class="resumo-valor">0</span>
      <span class="resumo-label">quantidade</span>
    </div>
    <div class="resumo-item">
      <span class="resumo-valor">R$ 0,00</span>
      <span class="resumo-label">valor total</span>
    </div>
  </div>

  <button class="botao-voltar-topo" id="btn-voltar-topo" title="Voltar ao topo">
    <span class="icone icone-seta-cima"></span>
  </button>
</div>
```

**Estilos CSS:**

```css
.notas-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
  position: relative;
}

.notas-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.notas-tabela th,
.notas-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.notas-tabela th {
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

.linha-nota {
  transition: background-color 0.2s ease;
}

.linha-nota:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-numero {
  width: 80px;
}

.link-numero {
  color: #1890ff;
  text-decoration: none;
}

.link-numero:hover {
  text-decoration: underline;
}

.coluna-data {
  width: 120px;
}

.coluna-cliente {
  min-width: 200px;
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
}

.acoes-grupo {
  display: flex;
  gap: 4px;
}

.botao-acao-tabela {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
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

.botao-acao-tabela:hover .icone-excluir {
  color: #f5222d;
}

.botao-acao-tabela:hover .icone-editar {
  color: #1890ff;
}

.botao-acao-tabela:hover .icone-visualizar {
  color: #1890ff;
}

.botao-acao-tabela:hover .icone-enviar {
  color: #52c41a;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-pendente {
  background-color: #fff7e6;
  color: #fa8c16;
}

.tag-emitida {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-cancelada {
  background-color: #fff1f0;
  color: #f5222d;
}

.resumo-rodape {
  display: flex;
  align-items: center;
  padding: 16px 0;
  border-top: 1px solid #f0f0f0;
}

.resumo-item {
  display: flex;
  flex-direction: column;
  margin-right: 32px;
}

.resumo-valor {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
}

.resumo-label {
  font-size: 12px;
  color: #666666;
}

.botao-voltar-topo {
  position: fixed;
  bottom: 24px;
  right: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-voltar-topo:hover {
  background-color: #f5f5f5;
}

.botao-voltar-topo .icone {
  font-size: 16px;
  color: #666666;
}
```

## Formulário de Inclusão/Edição de Nota Fiscal

Embora não esteja visível na tela atual, o formulário de inclusão/edição de nota fiscal é um componente importante deste módulo. Abaixo está a estrutura esperada:

\*\*Estrutura HT
(Content truncated due to size limit. Use line ranges to read in chunks)
